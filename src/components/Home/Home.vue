<template>
  <div class="body" :style="hei">
    <div>
      <div id="header">
        <div class="left_nav">
          <ul>
            <li class="nav_li" id="h_p_p">
              <router-link to="/home">
                <img src="./img/nav_p.png" class="nav_image" /> 首页
              </router-link>
            </li>
            <li class="nav_li" id="c_s">
              <a href="#">
                <img src="./img/nav_c.png" class="nav_image" /> 产生源监测
              </a>
              <ul id="cs">
                <li>
                  <router-link class="a_c" to="/source">
                    <img src="./img/car_mon.png" class="nav_image" /> 产生源地图
                  </router-link>
                </li>
                <li>
                  <router-link to="/source/info" class="menu" id="trace" value="1">
                    <img src="./img/trace.png" class="nav_image" />基本信息
                  </router-link>
                </li>
                <li>
                  <router-link to="/source/statistics">
                    <img src="./img/table.png" class="nav_image" />信息统计
                  </router-link>
                </li>
                <li>
                  <router-link to="/source/info2">
                    <img src="./img/etinfo.png" class="nav_image" />信息维护
                  </router-link>
                </li>
              </ul>
            </li>
            <li class="nav_li" id="m_v">
              <a href="#">
                <img class="nav_image" src="./img/nav_car.png" /> 车辆监控
              </a>
              <ul id="mv">
                <li>
                  <router-link class="a_c" to="/Monitor/MonitorVehicle">
                    <img src="./img/car_mon.png" class="nav_image" /> 实时监控
                  </router-link>
                </li>
                <li>
                  <router-link to="/Monitor/HistoricalTrack" class="menu" id="trace" value="1">
                    <img src="./img/trace.png" class="nav_image" />历史轨迹
                  </router-link>
                </li>
                <li>
                  <router-link to="/Monitor/Graph">
                    <img src="./img/table.png" class="nav_image" />统计分析
                  </router-link>
                </li>
                <li>
                  <router-link to="/Monitor/Info">
                    <img src="./img/etinfo.png" class="nav_image" />信息录入
                  </router-link>
                </li>
              </ul>
            </li>
          </ul>
        </div>
        <div class="header_center">
          <h2 style="color:white">
            <strong>建筑垃圾全过程实时监测与智能管控云平台</strong>
          </h2>
          <p class="color_font" style="color:white">
            <small>Comprehensive service platform for smart tourism</small>
          </p>
        </div>
        <div class="right_nav">
          <ul>
            <li class="nav_li" id="r_f">
              <router-link to="/saftyApp">
                <img class="nav_image" src="./img/nav_z.png" /> 消纳场监测
              </router-link>
            </li>

            <li class="nav_li" id="g_f">
              <a href="#">
                <img class="nav_image" src="./img/nav_x.png" /> 资源场监测
              </a>
              <ul id="gf">
                <li>
                  <router-link class="a_c" to="/mainViewer">
                    <img src="../Home/img/monitor_vehicle/car_mon.png" /> 地理位置
                  </router-link>
                </li>
                <li>
                  <router-link to="/query" class="menu" id="trace" value="1">
                    <img src="../Home/img/monitor_vehicle/trace.png" /> 资源场信息
                  </router-link>
                </li>
                <li>
                  <router-link to="/static">
                    <img src="../Home/img/monitor_vehicle/table.png" />信息统计
                  </router-link>
                </li>
              </ul>
            </li>
            <li class="nav_li" id="c_i">
              <router-link to="/manage">用户管理</router-link>
            </li>

            <img src="../Home/img/nav_10.png" @click="loginout()" />
          </ul>
        </div>
      </div>
    </div>

    <!--内容部分-->
    <div class="con left">
      <!--选择时间-->
      <!-- <div class="select_time">
        <div class="static_top left">
          <i></i>
          <span>总体概况</span>
        </div>
      </div>-->
      <!--数据总概-->
      <div class="con_div">
        <div class="con_div_text left itemDiv">
          <div class="con_div_text01 left itemDiv">
            <!-- <img src="../Home/img/info_1.png" class="left text01_img itemDiv"/> -->
            <div class="left text01_div">
              <p>收纳场数量(个)</p>
              <p>8</p>
            </div>
          </div>
          <div class="con_div_text01 right itemDiv">
            <!-- <img src="../Home/img/info_2.png" class="left text01_img itemDiv"/> -->
            <div class="left text01_div">
              <p>产生源数量(个)</p>
              <p>4</p>
            </div>
          </div>
        </div>
        <div class="con_div_text left itemDiv">
          <div class="con_div_text01 left itemDiv">
            <!-- <img src="img/info_4.png" class="left text01_img"/> -->
            <div class="left text01_div">
              <p>建筑垃圾运输车辆总数(辆)</p>
              <p class="sky">132</p>
            </div>
          </div>
          <div class="con_div_text01 right itemDiv">
            <!-- <img src="img/info_5.png" class="left text01_img"/> -->
            <div class="left text01_div">
              <p>建筑垃圾运输车辆在线数量(辆)</p>
              <p class="sky">78</p>
            </div>
          </div>
        </div>
        <div class="con_div_text left itemDiv">
          <div class="con_div_text01 left itemDiv">
            <!-- <img src="img/info_6.png" class="left text01_img"/> -->
            <div class="left text01_div">
              <p>消纳场总面积(平方米)</p>
              <p class="org">136567</p>
            </div>
          </div>
          <div class="con_div_text01 right itemDiv">
            <!-- <img src="img/info_7.png" class="left text01_img"/> -->
            <div class="left text01_div">
              <p>消纳场已使用面积(平方米)</p>
              <p class="org">13622</p>
            </div>
          </div>
        </div>
        <div class="con_div_text left itemDiv">
          <div class="con_div_text01 left itemDiv">
            <!-- <img src="img/info_6.png" class="left text01_img"/> -->
            <div class="left text01_div">
              <p>资源场每日收纳量(吨)</p>
              <p class="green">1324</p>
            </div>
          </div>
          <div class="con_div_text01 right itemDiv">
            <!-- <img src="img/info_7.png" class="left text01_img"/> -->
            <div class="left text01_div">
              <p>资源场每日出产量(吨)</p>
              <p class="green">876</p>
            </div>
          </div>
        </div>
      </div>
      <!--统计分析图-->
      <div class="div_any">
        <div class="div_any01 itemDiv">
          <div class="div_any_child">
            <div class="div_any_title">
              <img src="../Home/img/title_1.png" />各产生源建筑垃圾总量柱状图
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
              <img src="../Home/img/title_2.png" />产生源建筑垃圾变化折线图
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
              <img src="../Home/img/title_4.png" />各消纳场因子分析折线图
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
              <img src="../Home/img/title_5.png" />资源回收场数量统计
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
        // document.getElementById("mainmap", "macarons")
        document.getElementById("mainpie")
      );
      let option = {
        tooltip: {
          trigger: "axis"
        },
        legend: {
          data: ["因子1", "因子2", "因子3", "因子4", "因子5"],
          textStyle: {
            color: "white"
          }
        },
        toolbox: {
          show: true,
          feature: {
            mark: { show: true },
            dataView: { show: true, readOnly: false },
            magicType: { show: true, type: ["line", "bar"] }
            // magicType : {show: true, type: ['line', 'bar', 'stack', 'tiled']},

            // restore : {show: true},
            // saveAsImage : {show: true}
          },
          x: "right", // 水平安放位置，默认为全图右对齐，可选为：
          // 'center' ¦ 'left' ¦ 'right'
          // ¦ {number}（x坐标，单位px）
          y: "bottom" // 垂直安放位置，默认为全图顶端，可选为：'top' ¦ 'bottom' ¦ 'center'
        },
        calculable: true,
        xAxis: [
          {
            type: "category",
            boundaryGap: false,
            data: ["周一", "周二", "周三", "周四", "周五", "周六", "周日"],
            position: "center",
            axisLabel: {
              textStyle: {
                color: "white"
              }
            }
          }
        ],

        yAxis: [
          {
            type: "value",
            axisLabel: {
              textStyle: {
                color: "white"
              }
            }
          }
        ],
        series: [
          {
            name: "因子1",
            type: "line",
            stack: "总量",
            data: [120, 132, 101, 134, 90, 230, 210]
          },
          {
            name: "因子2",
            type: "line",
            stack: "总量",
            data: [220, 182, 191, 234, 290, 330, 310]
          },
          {
            name: "因子3",
            type: "line",
            stack: "总量",
            data: [150, 232, 201, 154, 190, 330, 410]
          },
          {
            name: "因子4",
            type: "line",
            stack: "总量",
            data: [320, 332, 301, 334, 390, 330, 320]
          },
          {
            name: "因子5",
            type: "line",
            stack: "总量",
            data: [820, 932, 901, 934, 1290, 1330, 1320]
          }
        ]
      };
      myChart.setOption(option);
    },
    initEchart2() {
      let myChart = this.$echarts.init(
        // document.getElementById("mainline", "macarons")
        document.getElementById("mainline")
      );
      let option2 = {
        tooltip: {
          trigger: "axis",
          axisPointer: {
            type: "cross"
          }
        },

        legend: {
          data: [
            "工程渣土",
            "装修垃圾",
            "拆迁垃圾",
            "工程泥浆",
            "淤泥以及弃料"
          ],
          textStyle: {
            color: "white"
          }
        },

        toolbox: {
          feature: {
            saveAsImage: {}
          }
        },
        grid: {
          left: "3%",
          right: "4%",
          bottom: "3%",
          containLabel: true
        },
        calculable: true,
        //x轴数据
        xAxis: [
          {
            type: "category",
            boundaryGap: false,
            data: ["周一", "周二", "周三", "周四", "周五", "周六", "周日"],
            axisLabel: {
              textStyle: {
                color: "white"
              }
            }
          }
        ],
        yAxis: [
          {
            type: "value",
            axisLabel: {
              textStyle: {
                color: "white"
              }
            }
          }
        ],
        series: [
          {
            name: "工程渣土",
            type: "line",
            stack: "总量",
            areaStyle: {},
            data: [120, 132, 101, 134, 90, 230, 210]
          },
          {
            name: "装修垃圾",
            type: "line",
            stack: "总量",
            areaStyle: {},
            data: [220, 182, 191, 234, 290, 330, 310]
          },
          {
            name: "拆迁垃圾",
            type: "line",
            stack: "总量",
            areaStyle: {},
            data: [150, 232, 201, 154, 190, 330, 410]
          },
          {
            name: "工程泥浆",
            type: "line",
            stack: "总量",
            areaStyle: { normal: {} },
            data: [320, 332, 301, 334, 390, 330, 320]
          },
          {
            name: "淤泥以及弃料",
            type: "line",
            stack: "总量",
            label: {
              normal: {
                show: true,
                position: "top"
              }
            },
            areaStyle: { normal: {} },
            data: [820, 932, 901, 934, 1290, 1330, 1320]
          }
        ]
      };
      myChart.setOption(option2);
    },
    initEchart3() {
      let myChart = this.$echarts.init(
        // document.getElementById("mainpie", "macarons")
        document.getElementById("mainmap")
      );
      let option3 = {
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
          ],
          textStyle: {
            color: "white"
          }
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
            ],
            axisLabel: {
              textStyle: {
                color: "white"
              }
            }
          }
        ],
        yAxis: [
          {
            type: "value",
            axisLabel: {
              textStyle: {
                color: "white"
              }
            }
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
        // document.getElementById("mainpop", "macarons")
        document.getElementById("mainpop")
      );
      let option3 = {
        tooltip: {
          trigger: "axis",
          axisPointer: {
            // 坐标轴指示器，坐标轴触发有效
            type: "shadow" // 默认为直线，可选为：'line' | 'shadow'
          }
        },
        legend: {
          data: ["工程渣土", "装修垃圾", "拆迁垃圾", "工程泥浆", "淤泥以及弃料"],
          textStyle: {
            color: "white"
          }
        },
        grid: {
          left: "3%",
          right: "4%",
          bottom: "3%",
          containLabel: true
        },
        xAxis: {
          type: "value",
               axisLabel: {
              textStyle: {
                color: "white"
              }
            }
        },
        yAxis: {
          type: "category",
          data: ["周一", "周二", "周三", "周四", "周五", "周六", "周日"],
               axisLabel: {
              textStyle: {
                color: "white"
              }
            }
        },
        dataset: {
          dimensions: ["周一", "周二", "周三", "周四", "周五", "周六", "周日"],
          // source: this.data
        },
        series: [
          {
            name: "工程渣土",
            type: "bar",
            stack: "总量",
            label: {
              normal: {
                show: true,
                position: "insideRight"
              }
            },
            data: [320, 302, 301, 334, 390, 330, 320]
          },
          {
            name: "装修垃圾",
            type: "bar",
            stack: "总量",
            label: {
              normal: {
                show: true,
                position: "insideRight"
              }
            },
            data: [120, 132, 101, 134, 90, 230, 210]
          },
          {
            name: "拆迁垃圾",
            type: "bar",
            stack: "总量",
            label: {
              normal: {
                show: true,
                position: "insideRight"
              }
            },
            data: [220, 182, 191, 234, 290, 330, 310]
          },
          {
            name: "工程泥浆",
            type: "bar",
            stack: "总量",
            label: {
              normal: {
                show: true,
                position: "insideRight"
              }
            },
            data: [150, 212, 201, 154, 190, 330, 410]
          },
          {
            name: "淤泥以及弃料",
            type: "bar",
            stack: "总量",
            label: {
              normal: {
                show: true,
                position: "insideRight"
              }
            },
            data: [820, 832, 901, 934, 1290, 1330, 1320]
          }
        ]
      };

      myChart.setOption(option3);
    },

    home() {
      this.$router.replace("/home");
    }
    // flyfly() {
    //   setTimeout(() => {
    //     this.viewer.camera.setView({
    //       destination: Cesium.Cartesian3.fromDegrees(117.09, 39, 240000.0),
    //       orientation: {
    //         heading: Cesium.Math.toRadians(0.0), // east, default value is 0.0 (north)
    //         pitch: Cesium.Math.toRadians(-90), // default value (looking down)
    //         roll: 0.0
    //       }
    //     });
    //   }, 5000);
    // }
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
    // this.flyfly();
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
body,
div,
p,
#header ul,
#header li,
dl,
dt,
dd,
h1,
a {
  margin: 0px;
  padding: 0px;
}
#header {
  width: 100%;
  margin: 0 auto; /*水平居中*/
  background: #030829;
  overflow: hidden;
  height: 88px;
}
.left_nav {
  float: left;
  overflow: hidden;
  width: 30%;
  text-align: center;
  margin-top: 22px;
}
.right_nav {
  float: right;
  overflow: hidden;
  width: 30%;
  text-align: center;
  margin-top: 22px;
}
.header_center {
  float: left;
  overflow: hidden;
  text-align: center;
  width: 40%;
  background-image: url("./img/logoBg.png");
  background-size: 100% 100%;
  height: 88px;
  /* background: url('logoBg.png') */
}
.header_center h2 {
  font-size: 18px;
  margin-top: 15px;
}
.color_font {
  margin-top: 10px;
  font-size: 15px;
}
#header a {
  font-size: 16px;
}

.left_nav .nav_li {
  list-style: none;
  height: 40px;
  text-align: center;
  display: inline-block;
  /* margin:0 50px; */
  width: 110px;
}
.right_nav .nav_li {
  list-style: none;
  height: 40px;
  text-align: center;
  display: inline-block;
  margin: 0 10px;
  width: 110px;
}
#header a {
  color: white;
  line-height: 40px;
  text-decoration: none;
}
#header .nav_image {
  vertical-align: middle;
}
#header li:hover {
  /* color:#111111; */
  /* background: linear-gradient(to bottom,#EEEEEE,#555555); */
  /* border:2px solid aqua; */
  box-shadow: -10px 0px 15px #034c6a inset, 0px -10px 15px #034c6a inset,
    10px 0px 15px #034c6a inset, 0px 10px 15px #034c6a inset;
  border-radius: 5px;
}
#h_p_p {
  box-shadow: -10px 0px 15px #034c6a inset, 0px -10px 15px #034c6a inset,
    10px 0px 15px #034c6a inset, 0px 10px 15px #034c6a inset;
  border-bottom: 4px solid #4b8df8;
  border-radius: 5px;
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

#mv {
  position: absolute;
  display: none;
  background: #030829;
  margin-top: -2px;
  margin-left: 0px;
  /* padding: 4px; */
  z-index: 100;
}

#m_v:hover #mv {
  display: block;
}
#mv li {
  list-style: none;
  text-align: center;
}
#mv li:hover {
  box-shadow: -10px 0px 15px #034c6a inset, 0px -10px 15px #034c6a inset,
    10px 0px 15px #034c6a inset, 0px 10px 15px #034c6a inset;
}
#mv li a input {
  vertical-align: middle;
}
/* 产生源 */

#cs {
  position: absolute;
  display: none;
  background: #030829;
  margin-top: -2px;
  margin-left: 0px;
  /* padding: 4px; */
  z-index: 100;
}

#c_s:hover #cs {
  display: block;
}
#cs li {
  list-style: none;
  text-align: center;
}
#cs li:hover {
  box-shadow: -10px 0px 15px #034c6a inset, 0px -10px 15px #034c6a inset,
    10px 0px 15px #034c6a inset, 0px 10px 15px #034c6a inset;
}
#cs li a input {
  vertical-align: middle;
}
/* 资源场 */
#rf {
  position: absolute;
  display: none;
  background: #030829;
  margin-top: -2px;
  margin-left: 0px;
  /* padding: 4px; */
  z-index: 100;
}

#r_f:hover #rf {
  display: block;
}
#rf li {
  list-style: none;
  text-align: center;
}
#rf li:hover {
  box-shadow: -10px 0px 15px #034c6a inset, 0px -10px 15px #034c6a inset,
    10px 0px 15px #034c6a inset, 0px 10px 15px #034c6a inset;
}
#rf li a input {
  vertical-align: middle;
}
/* 消纳场 */
#gf {
  position: absolute;
  display: none;
  background: #030829;
  margin-top: -2px;
  margin-left: 0px;
  /* padding: 4px; */
  z-index: 100;
}

#g_f:hover #gf {
  display: block;
}
#gf li {
  list-style: none;
  text-align: center;
}
#gf li:hover {
  box-shadow: -10px 0px 15px #034c6a inset, 0px -10px 15px #034c6a inset,
    10px 0px 15px #034c6a inset, 0px 10px 15px #034c6a inset;
}
#gf li a input {
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
  height: 780px;
  /* height: auto; */
}
.div_any01 {
  width: 30%;
  margin-right: 2%;
  height: 400px;
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
  /* height: 70%; */
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