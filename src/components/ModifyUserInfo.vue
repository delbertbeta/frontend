<template>
    <div class="wrapper">
        <div class="mask" @click="close"></div>
        <div class="content">
            <div class="box1">
                <img src="../assets/photo.png" style="height:200px;width:200px;margin-left:8%;margin-top:5%;"/>
                <div class="text1">修改头像</div>
            </div>   
            <div class="box2">
                <div class="text2">账号：001</div>
                <div class="text2">昵称：用户A</div>
                <div class="text2">密码：
                  <input placeholder="请输入新密码..." style="width:200px;height:35px;margin-left:-2%;">
                </div>
                <div class="text2">账户余额：RMB 1000.00</div>
            </div>  
            <div class="box3">
                <div class="confirm_modify">确认修改</div>
            </div>
        </div>
      
    </div>
</template>



<script>
export default {
  name: "OrderDetailPanel",
  props: ["goods_id"],
  data() {
    return {
    };
  },
  methods: {   
    close() {
      this.$emit('close1')
    }
  }
};
</script>



<style scoped>
.wrapper {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100vw;
  overflow: hidden;
}
.wrapper > .mask {
  height: 100vh;
  width: 100vw;
  background-color: rgba(0, 0, 0, 0.5);
  animation: fadeIn 0.5s ease 1 backwards;
}
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@keyframes slideIn {
  from {
    transform: translateX(100%)
  }
  to {
    transform: translateX(0%)
  }
}
.content {
  position: absolute;
  overflow-y: auto;
  right: 0px;
  top: 0px;
  width: 30vw;
  height: 100vh;
  background-color: white;
  animation: slideIn 0.5s ease 1 backwards;
}
.box1{
    background-color: #e5e5e5;
    width: 93%;
    margin-left: 7%;
    margin-top: 8%;
    text-align: left;
    padding-top: 1%;
    height:35vh;
    display: flex;
}
.box2{
    background-color: #e5e5e5;
    width: 93%;
    margin-left: 7%;
    margin-top: 8%;
    text-align: left;
    padding-top: 2%;
    height:45vh;
}
.text1{
    font-size: 28px;
    font-weight:bold;
    color: #505050;
    margin-top:40%;
    margin-left: 5%;
}
.text1:hover{
  color: rgba(255, 141, 26, 1);
  transition-duration:0.5s;
  text-decoration: underline;
  cursor: pointer;
}
.text2{
    font-size: 30px;
    font-weight:bold;
    color: #505050;
    margin-top: 5%;
    margin-left: 5%;
}
.box3{
  height: 250px;
  width: 100%;
}
.confirm_modify{
  width: 200px;
  height: 70px;
  background-color: #ffc300;
  margin-top: 10%;
  margin-left: auto;
  margin-right: auto;
  font-size:25px;
  color:black;
  font-weight:600;
  line-height: 70px;
}
.confirm_modify:hover{
  background-color: black;
  color: white;
  transition-duration:0.8s;
  cursor: pointer;
}
</style>