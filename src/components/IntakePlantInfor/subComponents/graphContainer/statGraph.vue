<template>
<!-- :class="className" :id="id" :style="{height:height,width:width}" -->
  <!-- height:300px;
  width:300px;
  z-index:6;
  /* position: fixed;
  bottom: 0px; */ -->
<!-- background-color: rgb(255, 255, 255) -->

<div class="divgraph">

    <div style="height:30px;width:100%;"></div>
    <h1 >基本信息统计>></h1>
    <h2>各影响因子占比饼图:</h2>
    <div style="height:300px;width:500px;z-index:6  ;margin-top: 40px;margin-left:32%" ref="myEchart2" ></div> 
    <h2>各消纳场因子分析折线图:</h2>
    <div  style="height:300px;width:500px;z-index:6  ;margin-top: 40px;margin-left:32%" ref="myEchart">
    </div>

</div>




</template>
<script>
import echarts from 'echarts'
export default {
  name:"statGraph",
  // name:'statGraph',
  // props: {
  //   className: {
  //     type: String,
  //     default: 'yourClassName'
  //   },
  //   id: {
  //     type: String,
  //     default: 'yourID'
  //   },
  //   width: {
  //     type: String,
  //     default: '500px'
  //   },
  //   height: {
  //     type: String,
  //     default: '500px'
  //   }
  // },
  data() {
    return {
      chart: null,
      chart2:null
    }
  },
  mounted() {
    this.initChart();
  },
  beforeDestroy() {
    if (!this.chart) {
      return
    }
    if (!this.chart2) {
      return
    }
    this.chart.dispose();
    this.chart = null;
    this.chart2.dispose();
    this.chart2 = null;
  },
  methods: {
  initChart() {
    this.chart = echarts.init(this.$refs.myEchart);
      // 把配置和数据放这里
      this.chart.setOption({

          // color: ['#3398DB'],
          // title:{
          //     text: '各消纳场因子分析折线图',
          //     subtext: '实验数据'
          // },
      		tooltip : {
						trigger: 'axis'
					},
					legend: {
            data:['因子1','因子2','因子3','因子4','因子5'],
            textStyle:{
                  color: 'white'
              }  
          
					},
					toolbox: {
						show : true,
						feature : {
							mark : {show: true},
							dataView : {show: true, readOnly: false},
              magicType : {show: true, type: ['line', 'bar']},
              // magicType : {show: true, type: ['line', 'bar', 'stack', 'tiled']},

							// restore : {show: true},
							// saveAsImage : {show: true}
            },
            x: 'right',                // 水平安放位置，默认为全图右对齐，可选为：
                                  // 'center' ¦ 'left' ¦ 'right'
                                  // ¦ {number}（x坐标，单位px）
            y: 'bottom',                  // 垂直安放位置，默认为全图顶端，可选为：'top' ¦ 'bottom' ¦ 'center'
                 
					},
					calculable : true,
					xAxis : [
						{
							type : 'category',
							boundaryGap : false,
              data : ['周一','周二','周三','周四','周五','周六','周日'],
              position:"center",
              axisLabel:{
                textStyle:{
                    color: 'white'
                }     

              },
            
           
            },
           
  
          ],
        
        
					yAxis : [
						{
              type : 'value',
              axisLabel:{
              textStyle:{
                  color: 'white'
              }     

              },
						}
					],
					series : [
						{
							name:'因子1',
							type:'line',
							stack: '总量',
							data:[120, 132, 101, 134, 90, 230, 210]
						},
						{
							name:'因子2',
							type:'line',
							stack: '总量',
							data:[220, 182, 191, 234, 290, 330, 310]
						},
						{
							name:'因子3',
							type:'line',
							stack: '总量',
							data:[150, 232, 201, 154, 190, 330, 410]
						},
						{
							name:'因子4',
							type:'line',
							stack: '总量',
							data:[320, 332, 301, 334, 390, 330, 320]
						},
						{
							name:'因子5',
							type:'line',
							stack: '总量',
							data:[820, 932, 901, 934, 1290, 1330, 1320]
						}
					]     
     }),
  
        
    this.chart2= echarts.init(this.$refs.myEchart2);
        this.chart2.setOption({
        angleAxis: {
            axisLabel:{
                textStyle:{
                    color: 'white'
                }     
            },
    

        },
        radiusAxis: {
            type: 'category',
            axisLabel:{
            textStyle:{
                color: 'red'
            }     
            },
            data: ['周一', '周二', '周三', '周四'],
            z: 10,
            
            
        },
        polar: {
            
        },
        series: [{
            type: 'bar',
            data: [1, 2, 3, 4],
            coordinateSystem: 'polar',
            name: 'A',
            stack: 'a'
        }, {
            type: 'bar',
            data: [2, 4, 6, 8],
            coordinateSystem: 'polar',
            name: 'B',
            stack: 'a'
        }, {
            type: 'bar',
            data: [1, 2, 3, 4],
            coordinateSystem: 'polar',
            name: 'C',
            stack: 'a'
        }],
        legend: {
            show: true,
            data: ['A', 'B', 'C']
        }
        });
    
    
    
    }
  }
}
</script>
<style>
.divgraph{
  height:100%;
  width:100%;
  z-index:5;
  /* position: fixed;
  bottom: 0px; */
  position: fixed;
  background-color:black;
  margin-top: 0px;
  overflow: auto;


}
.divgraph h1{
  color: white;
  margin-left:20%;

}
.divgraph h2{
  color: white;
  margin-left:30%
  
}
</style>
