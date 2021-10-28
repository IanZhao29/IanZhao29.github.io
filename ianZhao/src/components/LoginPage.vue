<template>
  <div class="homepage-hero-module">
    <div class="video-container">
      <div class="filter">
        <h2><span>I</span>M<span>POSSIBLE</span></h2>
        <button @click="start" @mouseenter="changeText(1)" @mouseleave="changeText(2)"><span id="btn">{{ btnText }}</span></button>
      </div>
      <video autoplay loop muted class="fillWidth">
        <source src="../assets/backgroundVideo.mp4" type="video/mp4" />
        浏览器不支持video标签，还tm用IE我真是服了
      </video>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LoginPage',

  data() {
    return {
      btnText: 'Get Start!',
    };
  },
  methods: {
    async start() {
      const { date: res } = await this.$http.psot('/api/post', {
        name: 'zs',
        age: 20
      })
      console.log(res)
    },
    changeText(param) {
      if(param === 1) {
        this.btnText = 'Hello Tourist!'
      }else {
        this.btnText = 'Get Start!'
      }
    }
  },
};
</script>

<style lang="less" scoped>
  .homepage-hero-module, .video-container {
    position: relative;
    height: 100vh;
    overflow: hidden;
  }
  .video-container .poster img {
    z-index: 0;
    position: absolute;
  }
  .video-container .filter {
    z-index: 1;
    position: absolute;
    background: rgba(0,0,0,0.4);
    width: 100%;
  }
  .fillWidth {
    width: 100%;
  }
  h2 {
    color: #666;
    margin: 100px;
    text-align: center;
    font-size: 100px;
  }
  h2 span{
    transition: 0.5s;
  }
  h2:hover span:nth-child(1) {
    margin-right: 10px;
  }
  h2:hover span:nth-child(1)::after {
    content: "'";
  }
  h2:hover span:nth-child(2) {
    margin-left: 20px;
  }
  h2:hover span {
    color: white;
    text-shadow: 0 0 10px lightcyan,
     0 0 20px lightcyan; 
  }
  button {
    display: block;
    width: 200px;
    height: 50px;
    position: relative;
    font-size: 25px;
    margin: 200px auto;
    background-color: #444;
    border: none;
    border-radius: 10px;
    color: aliceblue;
    transition: 0.5s;
    box-shadow: 0 0 5px lightcyan,
     0 0 5px lightcyan; 
  }
  button:hover {
    background-color: lightcyan;
    color: #333;
    box-shadow: 0 0 10px lightcyan,
     0 0 20px lightcyan; 
  }
  video {
    object-fit:fill;
    width: 100%;
    height: 100%;
  }
</style>
