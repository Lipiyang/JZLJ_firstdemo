<template>
<div>    
 <div class="header left">
    <div class="left nav itemDiv">
        <ul>
            <li><i class="nav_1"></i><router-link to="/">首页</router-link></li>
            <li>
                <Dropdown @on-click="info">
                    <i class="nav_2"></i>
                    产生源监测
                    <Dropdown-menu slot="list">
                        <Dropdown-item><router-link to="/source">产生源地图</router-link></Dropdown-item>
                        <Dropdown-item name="2"><router-link to="/source/info">基本信息</router-link></Dropdown-item>
                        <Dropdown-item><router-link to="/source/statistics">信息统计</router-link></Dropdown-item>
                        <Dropdown-item name="4"><router-link to="/source/info2">信息维护</router-link></Dropdown-item>
                    </Dropdown-menu>
                </Dropdown>
            </li>
            <li><i class="nav_3"></i>电子联单 </li>
        </ul>
    </div>
    <div class="header_center left itemDiv">
        <h2><strong>建筑垃圾全过程实时监测与智能管控云平台</strong></h2>
        <p class="color_font"><small>Comprehensive service platform for smart tourism</small></p>
    </div>
    <div class="right nav text_right itemDiv">
        <ul> <li><i class="nav_7"></i>查询统计 </li>
            <li><i class="nav_8"></i>信息录入 </li>
            <li><i class="nav_4"></i>表格界面 </li>
        </ul>
    </div>
    </div>
    <router-view/>
</div>
</template>
<script>

import axios from 'axios'
export default {
    data () {
        return {
            theme: 'dark',
            data:[]
        }
    },

    created () {
        axios
            .get('/api/sourceInfo/si')
            .then(response => (this.data = response.data.data))
            .catch(error => console.log(error))
    },

}
</script>

<style>
.header{
    width: 100%;
    height: 50px;
    background-color: #030829;
    display: table;
    table-layout: fixed;
    /* background-size: 100% 100%; */
    
}
.itemDiv{
    display:table-cell;
  
}
/* ../src/assets/img/logoBg.png */
.header_center{
    width: 30%;
    margin: 0px auto;
    color: #FFFFff;
    text-align: center;
    height: 50px;
    background-image: url("../SourcePlantInfo/img/logoBg.png");
    background-size: 100% 100%;
    font-family: "微软雅黑";
    /* padding:5px; */
}

.header_center h2{
   margin-top: 10px ;
    margin-bottom: 10px;
    font-size: 18px ;
}

.color_font{
    color: #e8f7fe; 
    font-size: 12px ;
}

.header_logo{
    margin-left: 1%;
    margin-top: 12px;

}

.header_logo img{
    height: 56px;
}

.nav{

    width: 35%;
   
}
.nav>ul{

} 
.nav>ul>li{
    display: inline-block;
    width: 120px;
    text-align: center;
    height: 50px;
    position: relative;
    line-height: 50px;
    margin-top: 15px;
    box-sizing: border-box;
    /* border-radius: 5px; */
 color: #e8f7fe; 
}
/* 選擇框 */
.nav>ul>li:hover{
    box-shadow: -10px 0px 15px #034c6a inset, 
    0px -10px 15px #034c6a inset,
    10px 0px 15px #034c6a inset, 
    0px 10px 15px #034c6a inset;

    box-sizing: border-box;
}
.nav>ul>li i{
    width: 16px;
    height: 16px;
    display: inline-block;
    position: relative;
    top:3px;
    margin-right: 5px;
}
.nav>ul>li>a{
    color: #ffffff;
    /* display: inline-block;
    padding: 0 15px 0 5px; */
    font-size: 14px;
}

.li_ul{
    position: absolute;
    background-color: #030829;
    width: 100%;
    border-top:4px solid #4b8df8;
    display: none;
    z-index: 999;

}
.li_ul li{
    line-height: 40px;
}
.li_ul li:hover{
    background-color: #4b8df8;
}
.li_ul li a{
    color: #ffffff;
    font-size: 13px;
}

.nav_1{
     background-image: url("../SourcePlantInfo/img/nav_1.png");
 }

 .nav_2{
     background-image: url("../SourcePlantInfo/img/nav_2.png");
 }

 .nav_3{
     background-image: url("../SourcePlantInfo/img/nav_3.png");
 }

 .nav_4{
     background-image: url("../SourcePlantInfo/img/nav_4.png");
 }

 .nav_5{
     background-image: url("../SourcePlantInfo/img/nav_5.png");
 }

 .nav_6{
     background-image: url("../SourcePlantInfo/img/nav_6.png");
 }

 .nav_7{
     background-image: url("../SourcePlantInfo/img/nav_7.png");
 }

 .nav_8{
     background-image: url("../SourcePlantInfo/img/nav_9.png");
 }

.nav_active{
    border-bottom: 4px solid #4b8df8;
    box-shadow: -10px 0px 15px #034c6a inset, 
    0px -10px 15px #034c6a inset, 
    10px 0px 15px #034c6a inset, 
    0px 10px 15px #034c6a inset;

    box-sizing: border-box;
}
</style>
