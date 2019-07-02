/* 表格信息 */
<template>
  <div>
    <viw></viw>
    <!-- <div  style='width:260px' class="row mb-5"> -->
      <div   class="row"  style="background-color: #081832;">
     
        <!--导航-->
      <el-col :span="4">
      <el-menu id="kk" :default-active="$route.path" class="el-menu-vertical-demo" 
               theme="dark"
               router>
        <el-menu-item index="/static/C1" style="background-color: #04425f">资源厂收纳垃圾量统计</el-menu-item>
        <el-menu-item index="/static/C2" style="background-color: #04425f">收纳垃圾类型统计</el-menu-item>
        <el-menu-item index="/static/C3" style="background-color: #04425f">最近三天各资源场收纳垃圾数量统计</el-menu-item>
      </el-menu>
    </el-col>
      
      <div class="col-8">
        <!--导航所对应的内容-->
        <!-- 二级导航菜单 -->
        <router-view/> 
      </div>
      
    </div>
  </div>
</template>

<script>
import viw from '../View'
export default {
  name: 'Chart',
  components:{
    viw
  }
}
</script>

<style>
/* .router-link-active .tab-link{
  color: red;
  background:pink;
}
canvas{
  color:azure;
} */
#kk{
  z-index: 10;
}
.el-menu-item{
  color: blanchedalmond;
  background-color: #04425f;
}
.el-menu-item.is-active{
  color: blanchedalmond;
  background-color: #04425f;
}
.row{
  height:800px
}
.el-menu-item:hover{
  background-color: rgba(50, 104, 205, 0.801);
}
</style>
