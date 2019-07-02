<template>
    <div>
        <div id="allmap" v-if='reset' :style="mapStyle"></div>
    </div>
</template>

<script type="text/javascript">
// import modal1 from './View'
import axios from 'axios'
export default{
    data(){
        return{
            reset:true,
            data_info:[],
            mapStyle:{
                width:'100%',
                height:window.innerHeight-88+'px'
            }
        }
    },

    mounted(){
        this.ready()
    },
    methods:{
        ready:function(){
               // 百度地图API功能  
            var map = new BMap.Map("allmap");    // 创建Map实例
            map.centerAndZoom(new BMap.Point(116.4, 39.9), 13);  // 初始化地图,设置中心点坐标和地图级别
            //添加地图类型控件
            map.addControl(new BMap.MapTypeControl({
                mapTypes:[
                    BMAP_NORMAL_MAP,//地图
                    BMAP_SATELLITE_MAP,//卫星地图
                    BMAP_HYBRID_MAP//混合地图
                ]}));
            
            // 设置地图风格
            // var  mapStyle ={ 
            //         features: ["road", "building","water","land"],//隐藏地图上的poi
            //                 style : "dark"  //设置地图风格为高端黑
            //                 }
            // map.setMapStyle(mapStyle);
            // 左上角，添加比例尺
            var top_left_control = new BMap.ScaleControl({anchor: BMAP_ANCHOR_TOP_LEFT});
            map.addControl(top_left_control);
            //左上角添加缩放平移控件
            var top_left_navigation = new BMap.NavigationControl();
            map.addControl(top_left_navigation);

            //添加城市列表的控件
            var size = new BMap.Size(10, 20);
            map.addControl(new BMap.CityListControl({
            anchor: BMAP_ANCHOR_BOTTOM_RIGHT,
            offset: size,
            }));

      

            var opts = {
                        width : 150,     // 信息窗口宽度
                        height: 200,     // 信息窗口高度
                        /* title : "<h3 style='margin:0'>建筑垃圾产生源</h3>" , // 信息窗口标题 */
                        enableMessage:true//设置允许信息窗发送短息
                    };
            
            
            axios({
                headers: {
                  token: this.$store.state.token
                },
                method: "get",
                url:'/api/sourceInfo/si'
                })
                .then(response => {
                    for(var i=0;i<response.data.length;i++){
                        this.data_info.push([response.data[i]['sourceLong'],response.data[i]['sourceLat'],"<h4>产生源位置："+response.data[i]['sourceAddress']
                        +"<br><br></h4><table border='5'><tr><td>责任单位</td><td>"+response.data[i]['sourceCompany']
                        +'</td></tr><tr><td>上报时间</td><td>'+response.data[i]['startDate']
                        +'</td></tr><tr><td>经度</td><td>'+response.data[i]['sourceLong']
                        +'</td></tr><tr><td>纬度</td><td>'+response.data[i]['sourceLat']
                        +'</td></tr><tr><td>成分分析</td><td>'+response.data[i]['wasteComponent']
                        +'</td></tr><tr><td>建议</td><td>'+response.data[i]['suggestion']
                        +'</td></tr><tr><td>备注</td><td>'+response.data[i]['content']
                        +'</td></tr></table>'])
                    }
                    // this.$nextTick(()=>{
                        for(var i=0;i<this.data_info.length;i++){
                            var marker = new BMap.Marker(new BMap.Point(this.data_info[i][0],this.data_info[i][1]));  // 创建标注
                            var content = this.data_info[i][2];
                            map.addOverlay(marker);               // 将标注添加到地图中
                            addClickHandler(content,marker);
                            marker.setAnimation(BMAP_ANIMATION_BOUNCE); //跳动的动画
                        }
                       
                        function addClickHandler(content,marker){
                            marker.addEventListener("click",function(e){
                                openInfo(content,e)}
                            );
                        }
                        function openInfo(content,e){
                            var p = e.target;
                            var point = new BMap.Point(p.getPosition().lng, p.getPosition().lat);
                            var infoWindow = new BMap.InfoWindow(content,opts);  // 创建信息窗口对象 
                            map.openInfoWindow(infoWindow,point); //开启信息窗口
                        }


                    // })
            })
            .catch(error => console.log(error))
            

            map.setCurrentCity("北京");          // 设置地图显示的城市 此项是必须设置的
            map.enableScrollWheelZoom(true);     //开启鼠标滚轮缩放
            map.enableInertialDragging();       //启用地图惯性拖拽
            map.enableContinuousZoom();         //开启连续缩放效果
        }
    }
}
</script>

<style>
#allmap{
    width:100%;
}
/* 隐藏百度地图图标和文字 */
.BMap_cpyCtrl
{
display:none; 
}
.anchorBL{
display:none; }
</style>
