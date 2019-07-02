<template>
  <div class="body" :style="hei">
   <div>
    <div id="header">
		<div class="left_nav">
			<ul>
				<li class="nav_li" id="h_p_p">
         	<router-link  to="/home"><img  src="./img/nav_p.png" class="nav_image"> 首页</router-link> </li>
				<li class="nav_li" id="c_s"><a href="#"><img src="./img/nav_c.png" class="nav_image"/> 产生源监测</a> 
					<ul id="cs" >
						<li><router-link class="a_c" to="/source"><img src="./img/car_mon.png" class="nav_image"/> 产生源地图</router-link></li>
						<li><router-link to="/source/info" class="menu"  id="trace" value = "1"><img  src="./img/trace.png" class="nav_image"/>基本信息</router-link></li>
						<li><router-link to="/source/statistics"> <img  src="./img/table.png" class="nav_image"/>信息统计</router-link></li>
            <li><router-link to="/source/info2"> <img  src="./img/etinfo.png" class="nav_image"/>信息维护</router-link></li>
          </ul>
				</li>
				<li class="nav_li" id="m_v">
				 <a href="#"><img class="nav_image" src="./img/nav_car.png"> 车辆监控</a> 
					<ul id="mv">
						<li><router-link class="a_c" to="/Monitor/MonitorVehicle"><img src="./img/car_mon.png" class="nav_image"/> 实时监控</router-link></li>
						<li><router-link to="/Monitor/HistoricalTrack" class="menu"  id="trace" value = "1"><img  src="./img/trace.png" class="nav_image"/>历史轨迹</router-link></li>
						<li><router-link to="/Monitor/Graph"> <img  src="./img/table.png" class="nav_image"/>统计分析</router-link></li>
            <li><router-link to="/Monitor/Info"> <img  src="./img/etinfo.png" class="nav_image"/>信息录入</router-link></li>
            </ul>
				</li>
			</ul>
		</div>
		<div class="header_center" >
			<h2 style="color:white"><strong>建筑垃圾全过程实时监测与智能管控云平台</strong></h2>
			<p class="color_font" style="color:white"><small>Comprehensive service platform for smart tourism</small></p>
		</div>
		<div class="right_nav">
			<ul>
				<li class="nav_li" id="r_f"><router-link to="/saftyApp"><img class="nav_image" src="./img/nav_z.png"> 消纳场监测</router-link> 
				</li>

				<li class="nav_li" id="g_f"><a href="#"><img class="nav_image" src="./img/nav_x.png"> 资源场监测</a> 
					<ul id="gf" >
						<li><router-link class="a_c" to="/mainViewer"><img  src="../Home/img/monitor_vehicle/car_mon.png" /> 地理位置</router-link></li>
						<li><router-link to="/query" class="menu"  id="trace" value = "1"><img  src="../Home/img/monitor_vehicle/trace.png" /> 资源场信息</router-link></li>
						<li><router-link to="/static"> <img  src="../Home/img/monitor_vehicle/table.png" />信息统计</router-link></li>            
            </ul>
				</li>
				<li class="nav_li" id="c_i"><router-link  to="/manage">用户管理</router-link> </li>
         
        <img  src="../Home/img/nav_10.png" @click="loginout()"/>
         
			</ul>
		</div>
	</div>
</div>

    <!--内容部分-->
    <div class="con left">
      <!--选择时间-->
      <div class="select_time">
        <div class="static_top left">
          <i></i>
          <span>总体概况</span>
        </div>
      </div>
      <!--数据总概-->
      <div class="con_div">
        <div class="con_div_text left itemDiv">
          <div class="con_div_text01 left itemDiv">
            <!-- <img src="../Home/img/info_1.png" class="left text01_img itemDiv"/> -->
            <div class="left text01_div">
              <p>车辆总数(辆)</p>
              <p>12356</p>
            </div>
          </div>
          <div class="con_div_text01 right itemDiv">
            <!-- <img src="../Home/img/info_2.png" class="left text01_img itemDiv"/> -->
            <div class="left text01_div">
              <p>车辆使用数(辆)</p>
              <p>12356</p>
            </div>
          </div>
        </div>
        <div class="con_div_text left itemDiv">
          <div class="con_div_text01 left itemDiv">
            <!-- <img src="img/info_4.png" class="left text01_img"/> -->
            <div class="left text01_div">
              <p>行驶里程总数(km)</p>
              <p class="sky">12356</p>
            </div>
          </div>
          <div class="con_div_text01 right itemDiv">
            <!-- <img src="img/info_5.png" class="left text01_img"/> -->
            <div class="left text01_div">
              <p>行驶里程平均数(km)</p>
              <p class="sky">12356</p>
            </div>
          </div>
        </div>
        <div class="con_div_text left itemDiv">
          <div class="con_div_text01 left itemDiv">
            <!-- <img src="img/info_6.png" class="left text01_img"/> -->
            <div class="left text01_div">
              <p>行驶时长总数(s)</p>
              <p class="org">12356</p>
            </div>
          </div>
          <div class="con_div_text01 right itemDiv">
            <!-- <img src="img/info_7.png" class="left text01_img"/> -->
            <div class="left text01_div">
              <p>行驶ihfj平均数(s)</p>
              <p class="org">12356</p>
            </div>
          </div>
        </div>
        <div class="con_div_text left itemDiv">
          <div class="con_div_text01 left itemDiv">
            <!-- <img src="img/info_6.png" class="left text01_img"/> -->
            <div class="left text01_div">
              <p>行驶时长总数(s)</p>
              <p class="green">12356</p>
            </div>
          </div>
          <div class="con_div_text01 right itemDiv">
            <!-- <img src="img/info_7.png" class="left text01_img"/> -->
            <div class="left text01_div">
              <p>行驶ihfj平均数(s)</p>
              <p class="green">12356</p>
            </div>
          </div>
        </div>
      </div>
      <!--统计分析图-->
      <div class="div_any">
        <div class="div_any01 itemDiv">
          <div class="div_any_child">
            <div class="div_any_title">
              <img src="../Home/img/title_1.png">车辆类型统计
            </div>

            <div class="chart">
              <div
                id="mainmap"
                style="height: 300px; width: 93.9%; border:0px solid #ccc;padding:5%;"
              ></div>
              <div style="height:5px"></div>
              <!-- <div id="mainline" style="height: 400px; width: 97.9%;border:1px solid #ccc;padding:1%;"></div> -->
            </div>
          </div>
          <div class="div_any_child">
            <div class="div_any_title">
              <img src="../Home/img/title_2.png">车辆状态统计
            </div>
            <!-- <p id="char2" class="p_chart"></p> -->
            <div
              id="mainline"
              style="height: 300px; width: 93.9%; border:0px solid #ccc;padding:5%;"
            ></div>
            <div style="height:5px"></div>
          </div>
        </div>
        <!-- <div class="div_any02 left itemDiv"> -->
        <div class="div_any02 itemDiv">
          <div id="cesiumContainer" class="top"></div>
        </div>

        <div class="div_any001 itemDiv">
          <div class="div_any_child">
            <div class="div_any_title">
              <img src="../Home/img/title_4.png">车辆行驶统计
            </div>
            <div
              id="mainpie"
              style="height: 300px; width: 93.9%; border:0px solid #ccc;padding:5%;"
            ></div>
            <div style="height:5px"></div>
            <!-- <p id="char3" class="p_chart"></p> -->
          </div>
          <div class="div_any_child">
            <div class="div_any_title">
              <img src="../Home/img/title_5.png">车辆报警统计
            </div>
            <div
              id="mainpop"
              style="height: 300px; width: 93.9%; border:0px solid #ccc;padding:5%;"
            ></div>
            <div style="height:5px"></div>
            <!-- <p id="char4" class="p_chart"></p> -->
          </div>
        </div>
      </div>

      <!--分析表格-->
    </div>
  </div>
</template>
<script>
import Cesium from "cesium/Source/Cesium.js";
import buildModuleUrl from "cesium/Source/Core/buildModuleUrl";
import "cesium/Source/Widgets/widgets.css";
import "echarts/theme/macarons.js";
export default {
  data() {
    return {
      viewer: "",
      tileset: "",
      hei: {
        weight: ""
      }
    };
  },
  created() {
    this.hh1();
  },
  methods: {
    hh1() {
      this.hei.weight = window.innerWeight + "px";
    },
    loginout() {
      this.$router.replace("/");
    },
    initEchart1() {
      let myChart = this.$echarts.init(
        document.getElementById("mainmap", "macarons")
      );
      let option = {
        tooltip: {
          trigger: "axis",
          axisPointer: {
            type: "cross"
          }
        },
        xAxis: [
          {
            type: "category",
            data: [
              "1月",
              "2月",
              "3月",
              "4月",
              "5月",
              "6月",
              "7月",
              "8月",
              "9月",
              "10月",
              "11月",
              "12月"
            ],
            axisPointer: {
              type: "shadow"
            },
            // #ffffff
            textStyle: {
              color: "#ffffff" //这里用参数代替了
            }
          }
        ],
        yAxis: [
          {
            type: "value",
            name: "总体积",
            min: 0,
            max: 10,
            interval: 1,
            axisLabel: {
              formatter: "{value} m³"
            },
            textStyle: {
              color: "#d0e17d" //这里用参数代替了
            }
          },
          {
            type: "value",
            name: "使用负荷",
            min: 0,
            max: 100,
            interval: 10,
            axisLabel: {
              formatter: "{value} %"
            },
            textStyle: {
              color: "#00000f" //这里用参数代替了
            }
          }
        ],
        series: [
          {
            name: "总体积",
            type: "bar",
            data: [2.0, 4.9, 5.5, 2.2, 4.6, 6.7, 5.6, 6.2, 3.6, 2.0, 6.4, 3.3],
            itemStyle: {
              normal: {
                color: "#d0e17d"
              }
            }
            // label: {
            //   show: true
            // }
          },
          {
            name: "使用负荷",
            type: "line",
            yAxisIndex: 1,
            data: [100, 22, 33, 45, 63, 80, 20, 23, 23, 65, 12, 6.2],
            itemStyle: {
              normal: {
                color: "#898989"
              }
            }
          }
        ]
      };
      myChart.setOption(option);
    },
    initEchart2() {
      let myChart = this.$echarts.init(
        document.getElementById("mainline", "macarons")
      );
      let option2 = {
        title: {
          // text: '过去某段时间内流量情况',
          subtext: "过去某段时间内流量情况",
          x: "center"
        },
        tooltip: {
          trigger: "axis"
        },
        legend: {
          data: ["总流量", "接收流量", "发送流量"],
          x: "left"
        },
        toolbox: {
          show: false,
          feature: {
            mark: { show: true },
            dataZoom: { show: true },
            dataView: { show: true },
            magicType: { show: true, type: ["line", "bar", "stack", "tiled"] },
            restore: { show: true },
            saveAsImage: { show: true }
          }
        },
        calculable: true,
        //x轴数据
        xAxis: [
          {
            type: "category",
            boundaryGap: false,
            data: (function() {
              var list = [];
              for (var i = 1; i <= 30; i++) {
                list.push("2013-03-" + i);
              }
              return list;
            })()
          }
        ],
        //y轴数据
        yAxis: [
          {
            type: "value"
          }
        ],
        series: [
          {
            name: "总流量",
            type: "line",
            data: (function() {
              var list = [];
              for (var i = 1; i <= 30; i++) {
                list.push(Math.round(Math.random() * 30));
              }
              return list;
            })()
          },
          {
            name: "接收流量",
            type: "line",
            data: (function() {
              var list = [];
              for (var i = 1; i <= 30; i++) {
                list.push(Math.round(Math.random() * 14));
              }
              return list;
            })()
          },
          {
            name: "发送流量",
            type: "line",
            data: (function() {
              var list = [];
              for (var i = 1; i <= 30; i++) {
                list.push(Math.round(Math.random() * 16));
              }
              return list;
            })()
          }
        ]
      };
      myChart.setOption(option2);
    },
    initEchart3() {
      let myChart = this.$echarts.init(
        document.getElementById("mainpie", "macarons")
      );
      let option3 = {
        title: {
          // text: '各建筑垃圾产生源的数据',
          subtext: "各建筑垃圾产生源的数据"
        },
        tooltip: {
          trigger: "axis",
          axisPointer: {
            // 坐标轴指示器，坐标轴触发有效
            type: "shadow" // 默认为直线，可选为：'line' | 'shadow'
          }
        },
        legend: {
          data: [
            "土地开挖垃圾",
            "道路开挖垃圾",
            "旧建筑物拆除垃圾",
            "建筑施工垃圾"
          ]
        },
        grid: {
          left: "3%",
          right: "4%",
          bottom: "3%",
          containLabel: true
        },
        xAxis: [
          {
            type: "category",
            data: [
              "01号产生源",
              "02号产生源",
              "03号产生源",
              "04号产生源",
              "05号产生源",
              "06号产生源",
              "07号产生源"
            ]
          }
        ],
        yAxis: [
          {
            type: "value"
          }
        ],
        series: [
          {
            name: "土地开挖垃圾",
            type: "bar",
            stack: "建筑垃圾",
            data: [120, 132, 101, 134, 90, 230, 210]
          },
          {
            name: "道路开挖垃圾",
            type: "bar",
            stack: "建筑垃圾",
            data: [220, 182, 191, 234, 290, 330, 310]
          },
          {
            name: "旧建筑物拆除垃圾",
            type: "bar",
            stack: "建筑垃圾",
            data: [150, 232, 201, 154, 190, 330, 410]
          },
          {
            name: "建筑施工垃圾",
            type: "bar",
            stack: "建筑垃圾",
            data: [140, 254, 231, 190, 260, 130, 190]
          }
        ]
      };
      myChart.setOption(option3);
    },
    initEchart4() {
      let myChart = this.$echarts.init(
        document.getElementById("mainpop", "macarons")
      );
      let option3 = {
        title: {
          text: "男性女性身高体重分布",
          subtext: "抽样调查来自: Heinz  2003"
        },
        tooltip: {
          trigger: "axis",
          showDelay: 0,
          formatter: function(params) {
            if (params.value.length > 1) {
              return (
                params.seriesName +
                " :<br/>" +
                params.value[0] +
                "cm " +
                params.value[1] +
                "kg "
              );
            } else {
              return (
                params.seriesName +
                " :<br/>" +
                params.name +
                " : " +
                params.value +
                "kg "
              );
            }
          },
          axisPointer: {
            show: true,
            type: "cross",
            lineStyle: {
              type: "dashed",
              width: 1
            }
          }
        },
        legend: {
          data: ["女性", "男性"]
        },
        toolbox: {
          show: true,
          feature: {
            mark: { show: true },
            dataZoom: { show: true },
            dataView: { show: true, readOnly: false },
            restore: { show: true },
            saveAsImage: { show: true }
          }
        },
        xAxis: [
          {
            type: "value",
            scale: true,
            axisLabel: {
              formatter: "{value} cm"
            }
          }
        ],
        yAxis: [
          {
            type: "value",
            scale: true,
            axisLabel: {
              formatter: "{value} kg"
            }
          }
        ],
        series: [
          {
            name: "女性",
            type: "scatter",
            data: [
              [161.2, 51.6],
              [167.5, 59.0],
              [159.5, 49.2],
              [157.0, 63.0],
              [155.8, 53.6],
              [170.0, 59.0],
              [159.1, 47.6],
              [166.0, 69.8],
              [176.2, 66.8],
              [160.2, 75.2],
              [172.5, 55.2],
              [170.9, 54.2],
              [172.9, 62.5],
              [153.4, 42.0],
              [160.0, 50.0],
              [147.2, 49.8],
              [168.2, 49.2],
              [175.0, 73.2],
              [157.0, 47.8],
              [167.6, 68.8],
              [159.5, 50.6],
              [175.0, 82.5],
              [166.8, 57.2],
              [176.5, 87.8],
              [170.2, 72.8],
              [174.0, 54.5],
              [173.0, 59.8],
              [179.9, 67.3],
              [170.5, 67.8],
              [160.0, 47.0],
              [154.4, 46.2],
              [162.0, 55.0],
              [176.5, 83.0],
              [160.0, 54.4],
              [152.0, 45.8],
              [162.1, 53.6],
              [170.0, 73.2],
              [160.2, 52.1],
              [161.3, 67.9],
              [166.4, 56.6],
              [168.9, 62.3],
              [163.8, 58.5],
              [167.6, 54.5],
              [160.0, 50.2],
              [161.3, 60.3],
              [167.6, 58.3],
              [165.1, 56.2],
              [160.0, 50.2],
              [170.0, 72.9],
              [157.5, 59.8],
              [167.6, 61.0],
              [160.7, 69.1],
              [163.2, 55.9],
              [152.4, 46.5],
              [157.5, 54.3],
              [168.3, 54.8],
              [180.3, 60.7],
              [165.5, 60.0],
              [165.0, 62.0],
              [164.5, 60.3],
              [156.0, 52.7],
              [160.0, 74.3],
              [163.0, 62.0],
              [165.7, 73.1],
              [161.0, 80.0],
              [162.0, 54.7],
              [166.0, 53.2],
              [174.0, 75.7],
              [172.7, 61.1],
              [167.6, 55.7],
              [151.1, 48.7],
              [164.5, 52.3],
              [163.5, 50.0],
              [152.0, 59.3],
              [169.0, 62.5],
              [164.0, 55.7],
              [161.2, 54.8],
              [155.0, 45.9],
              [170.0, 70.6],
              [176.2, 67.2],
              [170.0, 69.4],
              [162.5, 58.2],
              [170.3, 64.8],
              [164.1, 71.6],
              [169.5, 52.8],
              [163.2, 59.8],
              [154.5, 49.0],
              [159.8, 50.0],
              [173.2, 69.2],
              [170.0, 55.9],
              [161.4, 63.4],
              [169.0, 58.2],
              [166.2, 58.6],
              [159.4, 45.7],
              [162.5, 52.2],
              [159.0, 48.6],
              [162.8, 57.8],
              [159.0, 55.6],
              [179.8, 66.8],
              [162.9, 59.4],
              [161.0, 53.6],
              [151.1, 73.2],
              [168.2, 53.4],
              [168.9, 69.0],
              [173.2, 58.4],
              [171.8, 56.2],
              [178.0, 70.6],
              [164.3, 59.8],
              [163.0, 72.0],
              [168.5, 65.2],
              [166.8, 56.6],
              [172.7, 105.2],
              [163.5, 51.8],
              [169.4, 63.4],
              [167.8, 59.0],
              [159.5, 47.6],
              [167.6, 63.0],
              [161.2, 55.2],
              [160.0, 45.0],
              [163.2, 54.0],
              [162.2, 50.2],
              [161.3, 60.2],
              [149.5, 44.8],
              [157.5, 58.8],
              [163.2, 56.4],
              [172.7, 62.0],
              [155.0, 49.2],
              [156.5, 67.2],
              [164.0, 53.8],
              [160.9, 54.4],
              [162.8, 58.0],
              [167.0, 59.8],
              [160.0, 54.8],
              [160.0, 43.2],
              [168.9, 60.5],
              [158.2, 46.4],
              [156.0, 64.4],
              [160.0, 48.8],
              [167.1, 62.2],
              [158.0, 55.5],
              [167.6, 57.8],
              [156.0, 54.6],
              [162.1, 59.2],
              [173.4, 52.7],
              [159.8, 53.2],
              [170.5, 64.5],
              [159.2, 51.8],
              [157.5, 56.0],
              [161.3, 63.6],
              [162.6, 63.2],
              [160.0, 59.5],
              [168.9, 56.8],
              [165.1, 64.1],
              [162.6, 50.0],
              [165.1, 72.3],
              [166.4, 55.0],
              [160.0, 55.9],
              [152.4, 60.4],
              [170.2, 69.1],
              [162.6, 84.5],
              [170.2, 55.9],
              [158.8, 55.5],
              [172.7, 69.5],
              [167.6, 76.4],
              [162.6, 61.4],
              [167.6, 65.9],
              [156.2, 58.6],
              [175.2, 66.8],
              [172.1, 56.6],
              [162.6, 58.6],
              [160.0, 55.9],
              [165.1, 59.1],
              [182.9, 81.8],
              [166.4, 70.7],
              [165.1, 56.8],
              [177.8, 60.0],
              [165.1, 58.2],
              [175.3, 72.7],
              [154.9, 54.1],
              [158.8, 49.1],
              [172.7, 75.9],
              [168.9, 55.0],
              [161.3, 57.3],
              [167.6, 55.0],
              [165.1, 65.5],
              [175.3, 65.5],
              [157.5, 48.6],
              [163.8, 58.6],
              [167.6, 63.6],
              [165.1, 55.2],
              [165.1, 62.7],
              [168.9, 56.6],
              [162.6, 53.9],
              [164.5, 63.2],
              [176.5, 73.6],
              [168.9, 62.0],
              [175.3, 63.6],
              [159.4, 53.2],
              [160.0, 53.4],
              [170.2, 55.0],
              [162.6, 70.5],
              [167.6, 54.5],
              [162.6, 54.5],
              [160.7, 55.9],
              [160.0, 59.0],
              [157.5, 63.6],
              [162.6, 54.5],
              [152.4, 47.3],
              [170.2, 67.7],
              [165.1, 80.9],
              [172.7, 70.5],
              [165.1, 60.9],
              [170.2, 63.6],
              [170.2, 54.5],
              [170.2, 59.1],
              [161.3, 70.5],
              [167.6, 52.7],
              [167.6, 62.7],
              [165.1, 86.3],
              [162.6, 66.4],
              [152.4, 67.3],
              [168.9, 63.0],
              [170.2, 73.6],
              [175.2, 62.3],
              [175.2, 57.7],
              [160.0, 55.4],
              [165.1, 104.1],
              [174.0, 55.5],
              [170.2, 77.3],
              [160.0, 80.5],
              [167.6, 64.5],
              [167.6, 72.3],
              [167.6, 61.4],
              [154.9, 58.2],
              [162.6, 81.8],
              [175.3, 63.6],
              [171.4, 53.4],
              [157.5, 54.5],
              [165.1, 53.6],
              [160.0, 60.0],
              [174.0, 73.6],
              [162.6, 61.4],
              [174.0, 55.5],
              [162.6, 63.6],
              [161.3, 60.9],
              [156.2, 60.0],
              [149.9, 46.8],
              [169.5, 57.3],
              [160.0, 64.1],
              [175.3, 63.6],
              [169.5, 67.3],
              [160.0, 75.5],
              [172.7, 68.2],
              [162.6, 61.4],
              [157.5, 76.8],
              [176.5, 71.8],
              [164.4, 55.5],
              [160.7, 48.6],
              [174.0, 66.4],
              [163.8, 67.3]
            ],
            markPoint: {
              data: [
                { type: "max", name: "最大值" },
                { type: "min", name: "最小值" }
              ]
            },
            markLine: {
              data: [{ type: "average", name: "平均值" }]
            }
          },
          {
            name: "男性",
            type: "scatter",
            data: [
              [174.0, 65.6],
              [175.3, 71.8],
              [193.5, 80.7],
              [186.5, 72.6],
              [187.2, 78.8],
              [181.5, 74.8],
              [184.0, 86.4],
              [184.5, 78.4],
              [175.0, 62.0],
              [184.0, 81.6],
              [180.0, 76.6],
              [177.8, 83.6],
              [192.0, 90.0],
              [176.0, 74.6],
              [174.0, 71.0],
              [184.0, 79.6],
              [192.7, 93.8],
              [171.5, 70.0],
              [173.0, 72.4],
              [176.0, 85.9],
              [176.0, 78.8],
              [180.5, 77.8],
              [172.7, 66.2],
              [176.0, 86.4],
              [173.5, 81.8],
              [178.0, 89.6],
              [180.3, 82.8],
              [180.3, 76.4],
              [164.5, 63.2],
              [173.0, 60.9],
              [183.5, 74.8],
              [175.5, 70.0],
              [188.0, 72.4],
              [189.2, 84.1],
              [172.8, 69.1],
              [170.0, 59.5],
              [182.0, 67.2],
              [170.0, 61.3],
              [177.8, 68.6],
              [184.2, 80.1],
              [186.7, 87.8],
              [171.4, 84.7],
              [172.7, 73.4],
              [175.3, 72.1],
              [180.3, 82.6],
              [182.9, 88.7],
              [188.0, 84.1],
              [177.2, 94.1],
              [172.1, 74.9],
              [167.0, 59.1],
              [169.5, 75.6],
              [174.0, 86.2],
              [172.7, 75.3],
              [182.2, 87.1],
              [164.1, 55.2],
              [163.0, 57.0],
              [171.5, 61.4],
              [184.2, 76.8],
              [174.0, 86.8],
              [174.0, 72.2],
              [177.0, 71.6],
              [186.0, 84.8],
              [167.0, 68.2],
              [171.8, 66.1],
              [182.0, 72.0],
              [167.0, 64.6],
              [177.8, 74.8],
              [164.5, 70.0],
              [192.0, 101.6],
              [175.5, 63.2],
              [171.2, 79.1],
              [181.6, 78.9],
              [167.4, 67.7],
              [181.1, 66.0],
              [177.0, 68.2],
              [174.5, 63.9],
              [177.5, 72.0],
              [170.5, 56.8],
              [182.4, 74.5],
              [197.1, 90.9],
              [180.1, 93.0],
              [175.5, 80.9],
              [180.6, 72.7],
              [184.4, 68.0],
              [175.5, 70.9],
              [180.6, 72.5],
              [177.0, 72.5],
              [177.1, 83.4],
              [181.6, 75.5],
              [176.5, 73.0],
              [175.0, 70.2],
              [174.0, 73.4],
              [165.1, 70.5],
              [177.0, 68.9],
              [192.0, 102.3],
              [176.5, 68.4],
              [169.4, 65.9],
              [182.1, 75.7],
              [179.8, 84.5],
              [175.3, 87.7],
              [184.9, 86.4],
              [177.3, 73.2],
              [167.4, 53.9],
              [178.1, 72.0],
              [168.9, 55.5],
              [157.2, 58.4],
              [180.3, 83.2],
              [170.2, 72.7],
              [177.8, 64.1],
              [172.7, 72.3],
              [165.1, 65.0],
              [186.7, 86.4],
              [165.1, 65.0],
              [174.0, 88.6],
              [175.3, 84.1],
              [185.4, 66.8],
              [177.8, 75.5],
              [180.3, 93.2],
              [180.3, 82.7],
              [177.8, 58.0],
              [177.8, 79.5],
              [177.8, 78.6],
              [177.8, 71.8],
              [177.8, 116.4],
              [163.8, 72.2],
              [188.0, 83.6],
              [198.1, 85.5],
              [175.3, 90.9],
              [166.4, 85.9],
              [190.5, 89.1],
              [166.4, 75.0],
              [177.8, 77.7],
              [179.7, 86.4],
              [172.7, 90.9],
              [190.5, 73.6],
              [185.4, 76.4],
              [168.9, 69.1],
              [167.6, 84.5],
              [175.3, 64.5],
              [170.2, 69.1],
              [190.5, 108.6],
              [177.8, 86.4],
              [190.5, 80.9],
              [177.8, 87.7],
              [184.2, 94.5],
              [176.5, 80.2],
              [177.8, 72.0],
              [180.3, 71.4],
              [171.4, 72.7],
              [172.7, 84.1],
              [172.7, 76.8],
              [177.8, 63.6],
              [177.8, 80.9],
              [182.9, 80.9],
              [170.2, 85.5],
              [167.6, 68.6],
              [175.3, 67.7],
              [165.1, 66.4],
              [185.4, 102.3],
              [181.6, 70.5],
              [172.7, 95.9],
              [190.5, 84.1],
              [179.1, 87.3],
              [175.3, 71.8],
              [170.2, 65.9],
              [193.0, 95.9],
              [171.4, 91.4],
              [177.8, 81.8],
              [177.8, 96.8],
              [167.6, 69.1],
              [167.6, 82.7],
              [180.3, 75.5],
              [182.9, 79.5],
              [176.5, 73.6],
              [186.7, 91.8],
              [188.0, 84.1],
              [188.0, 85.9],
              [177.8, 81.8],
              [174.0, 82.5],
              [177.8, 80.5],
              [171.4, 70.0],
              [185.4, 81.8],
              [185.4, 84.1],
              [188.0, 90.5],
              [188.0, 91.4],
              [182.9, 89.1],
              [176.5, 85.0],
              [175.3, 69.1],
              [175.3, 73.6],
              [188.0, 80.5],
              [188.0, 82.7],
              [175.3, 86.4],
              [170.5, 67.7],
              [179.1, 92.7],
              [177.8, 93.6],
              [175.3, 70.9],
              [182.9, 75.0],
              [170.8, 93.2],
              [188.0, 93.2],
              [180.3, 77.7],
              [177.8, 61.4],
              [185.4, 94.1],
              [168.9, 75.0],
              [185.4, 83.6],
              [180.3, 85.5],
              [174.0, 73.9],
              [167.6, 66.8],
              [182.9, 87.3],
              [160.0, 72.3],
              [180.3, 88.6],
              [167.6, 75.5],
              [186.7, 101.4],
              [175.3, 91.1],
              [175.3, 67.3],
              [175.9, 77.7],
              [175.3, 81.8],
              [179.1, 75.5],
              [181.6, 84.5],
              [177.8, 76.6],
              [182.9, 85.0],
              [177.8, 102.5],
              [184.2, 77.3],
              [179.1, 71.8],
              [176.5, 87.9],
              [188.0, 94.3],
              [174.0, 70.9],
              [167.6, 64.5],
              [170.2, 77.3],
              [167.6, 72.3],
              [188.0, 87.3],
              [174.0, 80.0],
              [176.5, 82.3],
              [180.3, 73.6],
              [167.6, 74.1],
              [188.0, 85.9],
              [180.3, 73.2],
              [167.6, 76.3],
              [183.0, 65.9],
              [183.0, 90.9],
              [179.1, 89.1],
              [170.2, 62.3],
              [177.8, 82.7],
              [179.1, 79.1],
              [190.5, 98.2],
              [177.8, 84.1],
              [180.3, 83.2],
              [180.3, 83.2]
            ],
            markPoint: {
              data: [
                { type: "max", name: "最大值" },
                { type: "min", name: "最小值" }
              ]
            },
            markLine: {
              data: [{ type: "average", name: "平均值" }]
            }
          }
        ]
      };

      myChart.setOption(option3);
    },

    home() {
      this.$router.replace("/home");
    },
    flyfly() {
      setTimeout(() => {
        this.viewer.camera.setView({
          destination: Cesium.Cartesian3.fromDegrees(117.09, 39, 240000.0),
          orientation: {
            heading: Cesium.Math.toRadians(0.0), // east, default value is 0.0 (north)
            pitch: Cesium.Math.toRadians(-90), // default value (looking down)
            roll: 0.0
          }
        });
      }, 5000);
    }
  },
  mounted() {
    // 设置静态资源目录
    // buildModuleUrl.setBaseUrl("../static/Cesium");
    this.initEchart1();
    this.initEchart2();
    this.initEchart3();
    this.initEchart4();

    buildModuleUrl.setBaseUrl("../static/Cesium/");
    // // 创建viewer实例

    this.viewer = new Cesium.Viewer("cesiumContainer", {
      // 需要进行可视化的数据源的集合
      animation: false, // 是否显示动画控件
      shouldAnimate: true,
      homeButton: true, // 是否显示Home按钮
      fullscreenButton: false, // 是否显示全屏按钮
      baseLayerPicker: false, // 是否显示图层选择控件
      geocoder: true, // 是否显示地名查找控件
      timeline: false, // 是否显示时间线控件
      sceneModePicker: false, // 是否显示投影方式控件
      navigationHelpButton: false, // 是否显示帮助信息控件
      selectionIndicator: true,
      infoBox: true, // 是否显示点击要素之后显示的信息
      requestRenderMode: true, // 启用请求渲染模式
      scene3DOnly: false, // 每个几何实例将只能以3D渲染以节省GPU内存
      sceneMode: 3, // 初始场景模式 1 2D模式 2 2D循环模式 3 3D模式  Cesium.SceneMode
      fullscreenElement: document.body // 全屏时渲染的HTML元素 暂时没发现用处
    });

    // 去除版权信息
    this.viewer._cesiumWidget._creditContainer.style.display = "none";
    this.viewer.cesiumWidget.screenSpaceEventHandler.removeInputAction(
      Cesium.ScreenSpaceEventType.LEFT_DOUBLE_CLICK
    );
    this.flyfly();
    this.viewer.scene.camera.moveEnd.addEventListener(() => {
      //获取当前相机高度
      var height = Math.ceil(this.viewer.camera.positionCartographic.height);
      // && Menu.myentiys.length!=0
      // && Menu.myentiys.length!=0
      if (height > 260000) {
        this.viewer.entities.show = false;
        // console.log(this.$store.state.token);
      }
      if (height < 260000) {
        this.viewer.entities.show = true;
      }
    });
    //收纳场
    var url = "/api/intakePlantInfo/hello";
    var value = "";
    // this.$axios({
    //   method: 'get',
    //   url,
    //   headers:{
    //     'token' : this.$store.state.token
    //   }
    // }).then((res)=>{
    //   if (res) {
    //           value = res.data;
    //         }
    //         console.log(res.data)
    // }).catch((res)=>{
    //   console.log(res)
    // })
    $.ajax({
      // token: this.$store.state.token,
      headers: {
        token: this.$store.state.token
      },
      url,
      type: "GET",
      dataType: "json",
      async: false,
      cache: false,
      success: function(res) {
        // console.log(res);

        if (res) {
          value = res;
        }
      },
      error: function(res) {
        console.log(res);
      }
    });
    var result = value;
    var leng = result.length;
    console.log(result);
    console.log(result[leng - 2].IPI);
    console.log(result[leng - 1].SI);

    // console.log(result.length);
    //受纳场写循环
    var IPI = result[leng - 2].IPI;
    var SI = result[leng - 1].SI;
    for (var kk = 0; kk < IPI; kk++) {
      //获取经纬度
      var lat = result[kk].INTAKE_PLANT_LAT;
      var lon = result[kk].INTAKE_PLANT_LONG;

      //受纳场名字
      var Intake_name = result[kk].INTAKE_PLANT_NAME;
      //受纳场id
      var Intake_id = result[kk].INTAKE_PLANT_ID;

      var wyoming = this.viewer.entities.add({
        id: Intake_id,
        name: Intake_name,
        position: Cesium.Cartesian3.fromDegrees(lon, lat),
        //点样式
        point: {
          pixelSize: 5,
          color: Cesium.Color.RED,
          outlineColor: Cesium.Color.WHITE,
          outlineWidth: 1
        },
        //立广告牌
        billboard: {
          image: "../static/img/111.jpg",
          show: true, // default
          width: 25, // default: undefined
          height: 25 // default: undefined
        },
        //字体标签样式
        label: {
          text: Intake_name,
          font: "50pt",
          color: Cesium.Color.RED,
          style: Cesium.LabelStyle.FILL_AND_OUTLINE,
          outlineWidth: 1,
          //垂直位置
          //verticalOrigin : Cesium.VerticalOrigin.BUTTON,
          //中心位置
          pixelOffset: new Cesium.Cartesian2(0, 20)
        }
      });

      var km1 = 0;
      for (var km = 0; km <= IPI; km++) {
        var Intake_info_id = result[km + IPI].INTAKE_PLANT_ID;
        //Intake_id
        //result[kk].INTAKE_PLANT_ID
        if (Intake_info_id == result[kk].INTAKE_PLANT_ID) {
          km1 = km;
          break;
        }
      }
      var km2 = km1 + IPI;
      //建筑垃圾堆填位置
      var Intake_info_pos = result[km2].CONSTRUCTION_WASTE_POSITION;
      //建筑垃圾类型
      var Intake_info_type = result[km2].CONSTRUCTION_WASTE_TYPE;
      //建筑垃圾体量
      var Intake_info_size = result[km2].CONSTRUCTION_WASTE_SIZE;
      //现场图像数据
      var Intake_info_Data1 = result[km2].SECURITY_PARA_DATA1;
      //监测成果数据
      var Intake_info_Data2 = result[km2].SECURITY_PARA_DATA2;
      //录入时间

      var descript = '<table border="1">';
      descript += "<tr> <td>消纳场序号：</td> <td>" + Intake_id + "</td></tr>";
      descript +=
        "<tr><td>消纳场经纬度：</td><td>(" + lon + "," + lat + ")</td></tr>";
      descript +=
        "<tr><td>建筑垃圾堆填位置：</td><td>" + Intake_info_pos + "</td></tr>";
      descript +=
        "<tr><td>建筑垃圾类型：</td><td>" + Intake_info_type + "</td></tr>";
      descript +=
        "<tr><td>建筑垃圾体量：</td><td>" + Intake_info_size + "</td></tr>";
      descript +=
        "<tr><td>现场图像数据：</td> <td>" +
        '<a href = "' +
        Intake_info_Data1 +
        ' "target="_blank" >' +
        Intake_info_Data1 +
        "</a>" +
        "</td></tr>";
      // "<tr><td>现场图像数据：</td> <td>" + '<a href = "www.baidu.com" target="_blank" >'+Intake_info_Data1 +'</a>'+ "</td></tr>";
      descript +=
        "<tr><td>监测成果数据：</td> <td>" +
        '<a href = "' +
        Intake_info_Data2 +
        ' " target="_blank" >' +
        Intake_info_Data2 +
        "</a>" +
        "</td></tr>";

      wyoming.description = descript;
    }
    //产生源的循环
    for (var ki = 0; ki < SI; ki++) {
      //获取经纬度
      var mm = ki + 2 * IPI;
      var lat_s = result[mm].SOURCE_LAT;
      var lon_s = result[mm].SOURCE_LONG;
      //产生源地址
      var SOURCE_add = result[mm].SOURCE_ADDRESS;
      //产生源id
      var Source_id = result[mm].SOURCE_ID;
      var Source_company = result[mm].SOURCE_COMPANY;
      var Source_unit = result[mm].WASTE_UNIT;
      var Source_total = result[mm].WASTE_TOTAL;
      var Source_type = result[mm].SOURCE_TYPE;
      var Source_name = result[mm].INPUT_NAME;
      var Source_component = result[mm].WASTE_COMPONENT;
      var wyoming1 = this.viewer.entities.add({
        id: Source_id,
        name: SOURCE_add,
        position: Cesium.Cartesian3.fromDegrees(lon_s, lat_s),
        //点样式
        point: {
          pixelSize: 5,
          color: Cesium.Color.blue,
          outlineColor: Cesium.Color.WHITE,
          outlineWidth: 1
        },
        //立广告牌
        billboard: {
          image: "../static/img/222.jpg",
          show: true, // default
          width: 25, // default: undefined
          height: 25 // default: undefined
        },
        //字体标签样式
        label: {
          text: SOURCE_add,
          font: "50pt",
          color: Cesium.Color.blue,
          style: Cesium.LabelStyle.FILL_AND_OUTLINE,
          outlineWidth: 1,
          pixelOffset: new Cesium.Cartesian2(0, 20)
        }
      });

      var descript = '<table border="1">';
      descript += "<tr> <td>产生源序号：</td> <td>" + Source_id + "</td></tr>";
      descript +=
        "<tr><td>产生源经纬度：</td><td>(" +
        lon_s +
        "," +
        lat_s +
        ")</td></tr>";
      descript += "<tr><td>产生源地址：</td><td>" + SOURCE_add + "</td></tr>";
      descript += "<tr><td>责任单位：</td><td>" + Source_company + "</td></tr>";
      descript += "<tr><td>垃圾类型：</td><td>" + Source_type + "</td></tr>";
      descript +=
        "<tr><td>垃圾总量：</td><td>" +
        Source_total +
        Source_unit +
        "</td></tr>";
      descript += "<tr><td>录入人姓名：</td><td>" + Source_name + "</td></tr>";
      descript +=
        "<tr><td>垃圾成分分析：</td><td>" + Source_component + "</td></tr>";

      wyoming1.description = descript;
    }
  }
};
</script>

<style>
body,div,p,#header ul,#header li,dl,dt,dd,h1,a{
	margin: 0px;
	padding: 0px;
	
}
#header{
	width: 100%;
	margin: 0 auto; /*水平居中*/
	background: #030829;
	overflow: hidden;
	height: 88px;
}
.left_nav{
	
	float: left;
	overflow: hidden;
	width: 30%;
	text-align: center;
	margin-top: 22px;
}
.right_nav{
	
	float:right;
	overflow: hidden;
	width: 30%;
	text-align: center;
	margin-top: 22px;
}
.header_center{
	float: left;
	overflow: hidden;
	text-align: center;
	width: 40%;
	background-image: url("./img/logoBg.png");
	background-size:100% 100%;
	height: 88px;
	/* background: url('logoBg.png') */
}
.header_center h2{
	font-size: 18px;
	margin-top: 15px;
}
.color_font{
	margin-top: 10px;
	font-size:15px;
}
#header a{
	font-size: 16px 
}


.left_nav .nav_li{

	list-style: none;
	height: 40px;
	text-align: center;
	display:inline-block;
	/* margin:0 50px; */
	width: 110px;

}
.right_nav .nav_li{
	list-style: none;
	height: 40px;
	text-align: center;
	display:inline-block;
	margin:0 10px;
	width: 110px;
}
#header a{
	color: white;
	line-height:40px;
	text-decoration: none;
}
#header .nav_image{
	vertical-align:middle;
}
#header li:hover{
	/* color:#111111; */
	/* background: linear-gradient(to bottom,#EEEEEE,#555555); */
	/* border:2px solid aqua; */
	box-shadow: -10px 0px 15px #034c6a inset, 
    0px -10px 15px #034c6a inset, 
    10px 0px 15px #034c6a inset, 
    0px 10px 15px #034c6a inset;
	border-radius:5px;
}
#h_p_p{
	box-shadow: -10px 0px 15px #034c6a inset, 
    0px -10px 15px #034c6a inset, 
    10px 0px 15px #034c6a inset, 
    0px 10px 15px #034c6a inset;
	border-bottom: 4px solid #4b8df8;
	border-radius:5px;
} 
/* 车辆监控 */
/* #m_v{
	box-shadow: -10px 0px 15px #034c6a inset, 
    0px -10px 15px #034c6a inset, 
    10px 0px 15px #034c6a inset, 
    0px 10px 15px #034c6a inset;
	border-bottom: 4px solid #4b8df8;
	border-radius:5px;
} */

#mv{
	position: absolute;
	display: none;
	background: #030829;
	margin-top:-2px;
	margin-left: 0px;
	/* padding: 4px; */
	z-index: 100;

}

#m_v:hover #mv{
	display: block;
}
#mv li{
	list-style: none;	
	text-align: center;

}
#mv li:hover{
	box-shadow: -10px 0px 15px #034c6a inset, 
    0px -10px 15px #034c6a inset, 
    10px 0px 15px #034c6a inset, 
    0px 10px 15px #034c6a inset;

}
#mv li a input{
	vertical-align: middle;
	
}
/* 产生源 */

#cs{
	position: absolute;
	display: none;
	background: #030829;
	margin-top:-2px;
	margin-left: 0px;
	/* padding: 4px; */
	z-index: 100;

}

#c_s:hover #cs{
	display: block;
}
#cs li{
	list-style: none;	
	text-align: center;

}
#cs li:hover{
	box-shadow: -10px 0px 15px #034c6a inset, 
    0px -10px 15px #034c6a inset, 
    10px 0px 15px #034c6a inset, 
    0px 10px 15px #034c6a inset;

}
#cs li a input{
	vertical-align: middle;
	
}
/* 资源场 */
 #rf{
	position: absolute;
	display: none;
	background: #030829;
	margin-top:-2px;
	margin-left: 0px;
	/* padding: 4px; */
	z-index: 100;

}

#r_f:hover #rf{
	display: block;
}
#rf li{
	list-style: none;	
	text-align: center;

}
#rf li:hover{
	box-shadow: -10px 0px 15px #034c6a inset, 
    0px -10px 15px #034c6a inset, 
    10px 0px 15px #034c6a inset, 
    0px 10px 15px #034c6a inset;

}
#rf li a input{
	vertical-align: middle;
	
}
/* 消纳场 */
 #gf{
	position: absolute;
	display: none;
	background: #030829;
	margin-top:-2px;
	margin-left: 0px;
	/* padding: 4px; */
	z-index: 100;

}

#g_f:hover #gf{
	display: block;
}
#gf li{
	list-style: none;	
	text-align: center;

}
#gf li:hover{
	box-shadow: -10px 0px 15px #034c6a inset, 
    0px -10px 15px #034c6a inset, 
    10px 0px 15px #034c6a inset, 
    0px 10px 15px #034c6a inset;

}
#gf li a input{
	vertical-align: middle;
	
}


.con {
  width: 100%;
  background-color: #081832;
  padding-top: 20px;
  padding-bottom: 20px;
}

.con1 {
  width: 100%;
  background-color: #081832cc;
  /*padding-bottom: 4px;*/
  box-sizing: border-box;
  overflow: auto;
}

.find_expend {
  display: none;
}
.con1::before {
  content: "";
  display: block;
  clear: both;
  visibility: hidden;
  height: 0;
}
.select_time {
  width: 140px;
  height: 36px;

  margin-bottom: 25px;
  margin-left: 2%;
  padding-left: 20px;
}
.select_time img {
  height: 18px;
  margin-top: 9px;
}
.select_time input {
  border: none;
  background-color: transparent;
  width: 80px;
  height: 20px;
  top: -5px;
  margin-left: 10px;
  position: relative;
  text-indent: 1em;
  outline: none;
}
.con_div {
  height: 110px;
  width: 98%;
  margin-left: 3%;
  margin-bottom: 25px;
}
.con_div_text {
  height: 100%;
  background-color: #034c6a;
  width: 400px;
  margin-right: 8.3%;
}
.con_div_text01 {
  width: 200px;
  height: 100%;
}
.text01_img {
  width: 40px;
  height: 40px;
  margin-left: 5%;
  margin-top: 35px;
}
.text01_div {
  margin-top: 15px;
  margin-left: 5%;
  text-align: center;
}
.text01_div p {
  line-height: 35px;
}
.text01_div p:nth-child(1) {
  font-size: 13px;
  color: #ffffff;
}
.text01_div p:nth-child(2) {
  font-size: 28px;
  color: #ffff43;
  font-weight: 600;
}
.red {
  color: red !important;
}
.sky {
  color: #25f3e6 !important;
}
.org {
  color: #ff4e4e !important;
}
.green {
  color: #4eff92 !important;
}
.div_any {
  width: 98%;
  margin-left: 2%;
  margin-bottom: 25px;
  height: 700px;
}
.div_any01 {
  width: 30%;
  margin-right: 2%;
  /* height: 400px; */
}
.div_any001 {
  width: 30%;
  margin-left: 8%;
  /* height: 400px; */
}
.div_any02 {
  width: 800px;
  /* height: 22%; */
  margin-right: 25px;
}
.div_any03 {
  width: 98%;
  margin: 20px auto;
}

.div_any_child {
  width: 90%;
  /* 更改宽度设置 */
  height: 310px;
  box-shadow: -10px 0px 15px #034c6a inset,
    /*å·¦è¾¹é˜´å½±*/ 0px -10px 15px #034c6a inset,
    /*ä¸Šè¾¹é˜´å½±*/ 10px 0px 15px #034c6a inset,
    /*å³è¾¹é˜´å½±*/ 0px 10px 15px #034c6a inset;
  border: 1px solid #034c6a;
  box-sizing: border-box;
  position: relative;
  /* position: absolute; */
  margin-top: 25px;
}
/* test */
.div_any_child01 {
  width: 48%;
  /* height: 80%; */
  box-shadow: -10px 0px 15px #034c6a inset,
    /*å·¦è¾¹é˜´å½±*/ 0px -10px 15px #034c6a inset,
    /*ä¸Šè¾¹é˜´å½±*/ 10px 0px 15px #034c6a inset,
    /*å³è¾¹é˜´å½±*/ 0px 10px 15px #034c6a inset;
  border: 1px solid #034c6a;
  box-sizing: border-box;
  position: relative;
  margin-right: 2%;
}
.div_any_child01_wh {
  width: 98% !important;
}
.div_height01 {
  height: auto !important;
  padding: 5px;
}
.char_table {
  height: 200px;
}
.p_chart {
  height: 250px;

  padding: 5px 10px;

  margin-top: 15px;
}
#map_div {
  width: 96%;
  height: 94%;

  margin: 4% auto;
}
.div_height {
  /* height: 310px !important; */
  /* 584px */
  height: auto;
}
.div_any_title {
  background-color: #034c6a;
  border-radius: 18px;
  position: absolute;
  height: 35px;
  width: 60%;
  top: -15px;
  color: #ffffff;
  font-weight: bold;
  font-size: 16px;
  left: 20%;
  line-height: 35px;
  text-align: center;
}
.div_any_title img {
  width: 18px;
  height: 18px;
  position: relative;
  top: 2px;
  margin-right: 5px;
}
.any_title_width {
  width: 30% !important;
  left: 35% !important;
}
.div_table {
  width: 98%;
  margin-left: 1%;
  margin-bottom: 25px;
  height: 280px;
}
.div_table_box {
  width: 23%;
  margin-right: 2%;
}

/*统计分析界面样式*/
.static_top {
  width: 140px;
  height: 36px;
  line-height: 36px;
  background-color: #04425f;
  margin-bottom: 25px;
  margin-left: 1%;
  padding-left: 20px;
  border-radius: 1px;
  box-shadow: 0px 3px 3px #61d2f7;
}
.static_top i {
  width: 16px;
  height: 16px;
  display: inline-block;
  position: relative;
  background-image: url("../Home/img/nav_7.png");
  background-repeat: no-repeat;
  margin-right: 6px;
  top: 1px;
}
.static_top span {
  color: #25f3e6;
}
.stiatic_top_con {
  background-color: #034c6a;
  width: 96%;
  margin-left: 1%;
  margin-bottom: 25px;
  padding: 10px 1%;
  border-radius: 5px;
}
.stiatic_top_con table {
  width: 100%;
  border-collapse: collapse;
}
.stiatic_top_con table td {
  color: #ffffff;
  padding: 5px;
  font-size: 13px;
  border: 1px solid #485f849c;
}
.stiatic_top_con table .labe_td {
  color: #61d2f7;
  font-size: 14px;
  width: 120px;
  text-align: right;
}
.layui-layer-title {
  /*box-shadow: -8px 0px 10px #034c6a inset,*/
  /*8px 0px 10px #034c6a inset;*/
  background-color: #081832d4 !important;
  color: #ffffff !important;
  border-bottom: 3px solid #4b8df8 !important;
  box-sizing: border-box;
}
.itemDiv {
  display: table-cell;
}
.top {
  width: 108%;
  float: right;
  /* height: 89%; */
  height: 650px;
  /* line-height: 100px; 
  border-bottom: 1px solid #b0cdff; */
}
</style>