<template>
    <div id="app">
		<Vew></Vew>
		<div id="clear">
		</div>
		<div id="content" >
			<div id="left_content">
				
			</div>
			<div id="right" class="container">
                <bar></bar>
               <br>
                <pie></pie>
				<br>
				<lineare></lineare>
                <!-- <stbar></stbar> -->
			</div>
			
			

			
			

		</div>
		<div id="footer">
			<p>
				<a href="#">关于</a>
				<a href="#">广告</a>
				<a href="#">联系</a>
				<a href="#">合作</a>
				<a href="#">版权</a>
			</p>
			<p>
				<!-- <a href="#">京ICP备 0000001号</a> -->
				All right(C) 2008-2010 resved.
			</p>
		</div>

		
    </div>
</template>


<script type="text/javascript">
import bar from './bar'
import pie from './pie'
import stbar from './stackedbar'
import lineare from './line'
import Vew from './View.vue'

export default{
    components: {
        bar,
        pie,
        stbar,
		lineare,
		Vew
  }

}
</script>

<style scoped>
body,div,p,dl,dt,dd,h1,a{
	margin: 0px;
	padding: 0px;
	
}

#left_content{
	float: left;
	width: 0px;
	height: 800px;
	background: #ffffff;
	margin-top: 65px;
	text-align: center;

	/* background: #FF0000; */
}

#content{
	
	overflow: hidden;
	z-index: 1;
	/* margin-top: 58px; */
}
/* #clear{
	clear: both;
} */
#footer{
	text-align: center;
	background:#030829;
}
#footer a{
	text-decoration: none;
	color: white;
}
#nav1 li{
	padding: 15px;
	font-size: 15px;
	text-align: center;
	
/* 	height: 32px; */
}

#nav1 li a{
	height: 32px;
	text-decoration: none;
	/* border-radius:15px; */
	/* border:2px solid aqua; */
	color: #666666;
	text-align: center;
	
	
}
#nav1 li a input{
	vertical-align: middle;
	
}

#right, #right_car{
	height: 800px;
	margin-top: 65px;
	/* width：calc（100%-235px）； */
	width: 100% ;
	float: right;
	overflow: hidden;
	overflow: auto;
}



#nav1 li:hover{
	background:  #66cc66;
/* 	color: #FFFFFF; */
}
#img1{
	margin-top: 18px;
	margin-left: 60px;
	float: left;
}

/* 表格 */
[v-cloak] {
            display: none
}
table {
	border: 1px solid #ccc;
	padding: 0;
	border-collapse: collapse;
	table-layout: fixed;
	margin-top: 10px;
	width: 100%;
}
table td,
table th {
	height: 30px;
	border: 1px solid #ccc;
	background: #fff;
	font-size: 15px;
	padding: 3px 3px 3px 8px;
}
table th:first-child {
	width: 30px;
}
.container,
.st {
	width: 1000px;
	margin: 10px auto 0;
	font-size: 13px;
	font-family: 'Microsoft YaHei'
}
.container .search {
	font-size: 15px;
	padding: 4px;
}
.container .add {
	padding: 5px 15px;
}
.overlay {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	z-index: 6;
	background: rgba(0, 0, 0, 0.7);
}
.overlay td:first-child {
	width: 66px;
}
.overlay .con {
	position: absolute;
	width: 420px;
	min-height: 300px;
	background: #fff;
	left: 50%;
	top: 50%;
	-webkit-transform: translate3d(-50%, -50%, 0);
	transform: translate3d(-50%, -50%, 0);
	/*margin-top: -150px;*/
	padding: 20px;
}
</style>

