<template>
  <view-page>
    <!-- 左按钮区 -->
    <template slot="left-field">
      <el-button type="danger" icon="el-icon-circle-plus-outline" @click="addTodo">添加</el-button>
    </template>
    <!-- 搜索框 -->
    <template slot="search-field">
      <el-input v-model="searchStr" suffix-icon="el-icon-search" placeholder="请输入搜索内容"></el-input>
    </template>

    <!-- 右按钮区 -->

    <!-- 对话框 -->
    <edit-dialog :show="editShow" title="用户注册" @close="closeEditDialog" @save="saveTodo">
      <el-form :model="currentTodo" ref="todoEditForm">
        <el-form-item label="id" prop="userId" required>
          <el-input v-model="currentTodo.userId"></el-input>
        </el-form-item>
        <el-form-item label="用户名" prop="userName" required>
          <el-input v-model="currentTodo.userName" type="textarea"></el-input>
        </el-form-item>
        <el-form-item label="密码" prop="password" required>
          <el-input v-model="currentTodo.password" type="textarea"></el-input>
        </el-form-item>
        <el-form-item label="权限" prop="role" required>
          <el-input v-model="currentTodo.role" type="textarea"></el-input>
        </el-form-item>
      </el-form>
    </edit-dialog>

    <!-- 表格区 -->
    <el-table :data="pagedData">
      <!-- <el-table :data= "filtedData"> -->
      <el-table-column label="id" prop="id">
        <template slot-scope="scope">{{scope.row.userId}}</template>
      </el-table-column>
      <el-table-column label="用户名">
        <template slot-scope="scope">{{scope.row.userName}}</template>
      </el-table-column>
      <el-table-column label="密码">
        <template slot-scope="scope">{{scope.row.password}}</template>
      </el-table-column>
      <el-table-column label="权限">
        <template slot-scope="scope">{{scope.row.role}}</template>
      </el-table-column>
<!-- scope.row.role -->
      <el-table-column label="操作">
        <template slot-scope="scope">
          <!-- <el-button size="small" type="warning" icon="el-icon-edit" @click="editTodo(scope.row)"></el-button> -->
          <el-button
            size="small"
            type="danger"
            icon="el-icon-delete"
            @click="removeTodoAjax(scope.row)"
          ></el-button>
        </template>
      </el-table-column>
    </el-table>
    <el-pagination
      :total="total"
      :current-page="currentPage"
      :page-size="currentPageSize"
      :page-sizes="[5, 7]"
      layout="total, sizes, prev, pager, next, jumper"
      @size-change="pageSizeChange"
      @current-change="pageChange"
    ></el-pagination>
  </view-page>
</template>

<script>
import ViewPage from "./ViewPage";
import EditDialog from "./EditDialog";
export default {
  components: {
    ViewPage,
    EditDialog
  },
  data() {
    return {
      data: [],
      filterType: "",
      searchStr: "",
      currentPage: 1,
      currentPageSize: 5,
      editShow: false,
      currentTodo: {}
    };
  },
  mounted() {
    this.update();
  },
  computed: {
    filtedData() {
      return this.data
        .filter(item => {
          var reg = new RegExp(this.searchStr, "i");
          return (
            !this.searchStr || reg.test(item.userName) || reg.test(item.userId)
          );
        })
        .filter(item => {
          return this.filterType === "" || item.status === this.filterType;
        });
    },
    total() {
      return this.filtedData.length;
    },
    pagedData() {
      return this.filtedData.slice(
        (this.currentPage - 1) * this.currentPageSize,
        this.currentPage * this.currentPageSize
      );
    }
  },
  methods: {
    pageSizeChange(size) {
      this.currentPageSize = size;
    },
    pageChange(page) {
      this.currentPage = page;
    },
    update() {
       if(this.$store.state.usern=="customer"){
        var URM="/api/user/sel"
         this.$axios({
        headers: {
          token: this.$store.state.token
        },
        method: "get",
        url:URM,
        params: {
          username: this.$store.state.namen
        }
      })
        .then(res => {
          console.log(res.data.data);
          this.data.push({
             userId: 0,
              id: res.data.data.id,
              userName: res.data.data.username,
              password: res.data.data.password,
              role: "customer"
          })
          // this.userna = res.data.data.username;
          // this.userpass = res.data.data.password;
          // console.log(userna);
        })
        .catch(err => {
          console.log(err);
          alert("err");
        });
      }
      else{

        this.$axios
        .get("/api/user/surc", {
          headers: {
            token: this.$store.state.token
          }
        })
        .then(response => {
          this.initData = response.data;
          var num='';
          var res =response.data.data;
          num=response.data.data.length;
          console.log(response.data.data)
          console.log(num/4)

          for(var s=0;s<num/4;s++){
               this.data.push({
              userId: s,
              id: res[0+4*s],
              userName: res[1+4*s],
              password: res[2+4*s],
              role: res[3+4*s]
            });
            this.data1=res;
          
          
          }
         
        }).catch(error => console.log(error));
      }
      
        
        
        
      
      
    },
    addTodo() {
      if(this.$store.state.usern=="customer"){
        alert("你没有权限！");
      }else{
      this.currentTodo = {};
      this.editShow = true;
      }
    },
    saveTodo() {
      //   this.closeEditDialog()
      this.$refs.todoEditForm.validate(valid => {
        if (valid) {
          alert(JSON.stringify(this.currentTodo));

          // var data_new = JSON.stringify(this.currentTodo);
          var data_new = this.currentTodo;
         
          var ur = "/api/user/add";
         this.$axios({
          headers: {
            token: this.$store.state.token
          },
          method: "get",
          url: ur,
          params: {
                  userId: this.currentTodo.userId,
                  userName: this.currentTodo.userName,
                  password: this.currentTodo.password,
                  role: this.currentTodo.role
                }
          
        }).then(res => {
           console.log(res);
          })
           .catch(err => {
             console.log(err);
           });         
        }
      });
    },
    closeEditDialog() {
      this.currentTodo = {};
      this.$refs.todoEditForm.resetFields();
      this.editShow = false;
    },
    addAjax() {
      console.log("sasa");
      console.log(this.currentTodo);
      console.log("sasasa");
    },
    editAjax() {
      console.log("kikikiho");
    },
    editTodo(row) {
      this.currentTodo = JSON.parse(JSON.stringify(row));
        // console.log("KLKLK(*");
        // console.log(this.currentTodo);
        // console.log("KLKLK(*");

      this.editShow = true;
    },
    removeTodoAjax(row) {
      // var urr = "/api/user/delete";
      if (this.$store.state.usern === "customer") {
        alert("当前用户组别没有权限");
      } else {
        console.log(row.userId);
        console.log(this.data);
        console.log(this.data[row.userId]);
        if (this.data[row.userId].role == "admin") {
          alert("您不能删除管理员账号");
        } else {
          console.log(this.data[row.userId].userName);
          var userName = this.data[row.userId].userName;
          alert(userName);
          var urr = "/api/user/del";
          this.$confirm("确定要删除?")
            .then(() => {
              this.$axios({
                headers: {
                  token: this.$store.state.token
                },
                method: "get",
                url: urr,
                params: {
                  username: userName
                }
              })
                .then(res => {
                  console.log(res);
                  location.reload();
                })
                .catch(err => {
                  console.log(err);
                  alert("出错");
                });
            })
            .catch(function(error) {
              console.log(error); // 失败
              console.log("KKK");
              alert("chucuo");
            });
        }
      }
    }
  }
};
</script>

<style>
</style>
