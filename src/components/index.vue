<template>
  <div class="all">
    <div class="header">
        <h3 style="padding-top: 2vh;">VIP</h3>
    </div>
    <div class="main">
        <div class="status" v-if="!re">
            <img src="https://images.unsplash.com/photo-1553481187-be93c21490a9?ixid=MXwxMjA3fDB8MHxzZWFyY2h8Mnx8Z2FtZXxlbnwwfHwwfA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60"> 
            <div class="font">
                <i class="fas fa-crown"></i><br>
                <span>普通會員</span>
            </div>
        </div>
          <div class="status" v-if="re">
            <img src="https://images.unsplash.com/photo-1596451190630-186aff535bf2?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MjAwfHxnYW1lfGVufDB8fDB8&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60">
            <div class="font">
                <i class="fas fa-crown"></i><br>
                <span>青銅會員</span>
            </div>
        </div>
        <div class="status1" :class="{'test': isClose,'test1': isOpen}" style="z-index:10" @click="switcher"  v-if="!re" >
            <img src="https://images.unsplash.com/photo-1596451190630-186aff535bf2?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MjAwfHxnYW1lfGVufDB8fDB8&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60">
            <div class="font">
                <span>青銅會員</span>
                <div class="charge">
                    <span>$100</span>
                    <button v-if="isOpen" @click="btnOpenModal" class="btnOpenModal">充值</button>
                </div>
            </div>
        </div>
          <div class="status1 test" style="z-index:10"   v-if="re">
            <img src="https://images.unsplash.com/photo-1553481187-be93c21490a9?ixid=MXwxMjA3fDB8MHxzZWFyY2h8Mnx8Z2FtZXxlbnwwfHwwfA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60"> 
            <div class="font">
                <span>普通會員</span>
            </div>
        </div>
        <div class="status1" style="z-index:9" >
            <img src="https://images.unsplash.com/photo-1561892699-a132d015e9c6?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MTN8fGdhbWV8ZW58MHx8MHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60">
            <div class="font">
            <span>黃金會員</span>
                <div class="charge">
                  <span>$1000</span>
                </div>
            </div>
        </div>
        <div class="status1" style="z-index:8">
            <img src="https://images.unsplash.com/photo-1571811995390-7e0b84c2584e?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MTE2fHxnYW1lfGVufDB8fDB8&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60">
            <div class="font">
                <span>鑽石會員</span>
                <div class="charge">
                  <span>$1500</span>
                </div>
            </div>
        </div>
          <div class="status1" style="z-index:7">
            <img src="https://images.unsplash.com/photo-1611546191222-96fb7afd5af9?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MTc1fHxnYW1lfGVufDB8fDB8&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60">
            <div class="font">
                <span>至尊會員</span>
                <div class="charge">
                  <span>$2000</span>
                </div>
            </div>
        </div>
        <div class="status1" style="z-index:6">
            <img src="https://images.unsplash.com/photo-1522617889820-47708e025180?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MTA4fHxnYW1lfGVufDB8fDB8&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60">
            <div class="font">
                <span>榮耀會員</span>
                <div class="charge">
                  <span>$3000</span>
                </div>
            </div>
        </div>
        <div class="status1">
            <img src="https://images.unsplash.com/photo-1574340091276-e9cba7844793?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MjczfHxnYW1lfGVufDB8fDB8&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60">
            <div class="font">
                <span>尊耀會員</span>
                <div class="charge">
                  <span>$4000</span>
                </div>
            </div>
        </div>
    </div>
    <div id="myModal" class="modal">
        <div class="modal-content" >
          <span class="close" @click="close">&times;</span>
          <p>提示</p>
          <span>花費＄100成為青銅會員嗎</span><br>
          <button @click="corrent">確定</button>
          <button @click="close">取消</button>
        </div>
    </div><br><br>
    <i class="fas fa-microphone-alt"></i>
    <div class="footer">
        <div class="com">
            <div class="icon">
              <i class="fas fa-home" ></i>
              <span style="font-size:3vw;">任務</span>
            </div>
            <div class="icon">
              <i class="fas fa-gamepad"></i>
              <span style="font-size:3vw">任務</span>
            </div>
            <div class="icon" :class="{'active':pt}">
              <i class="fas fa-star"></i>
              <span style="font-size:3vw">VIP</span>
            </div>
            <div class="icon">
              <i class="fas fa-user"></i>
              <span style="font-size:3vw">我的</span>
            </div>
        </div>
        
    </div>
  </div>
</template>

<script>
export default {
  name: 'index',
  data() {
    return {
      sw:false,
      goCharge:false,
      re:false,
      isOpen:false,
      isClose:true,
      pt:true,
    }
  },
  
  methods: {
    switcher(){
        //实现开关切换
        this.isClose = !this.isClose;
        this.isOpen = !this.isOpen;
    },
    btnOpenModal(){
      var modal = document.getElementById("myModal");
      modal.style.display = "block";
    },
    close(){
      var modal = document.getElementById("myModal");
      modal.style.display = "none";
    },
    corrent(){
      var modal = document.getElementById("myModal");
      this.re = true
      modal.style.display = "none";
    }
  },
}
</script>
