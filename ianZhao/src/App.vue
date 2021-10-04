<template>
  <div>
    <h2><span>I</span>M<span>POSSIBLE</span></h2>
  </div>
</template>

<script>
export default {
  name: 'Ianzhao29GithubIoApp',

  data() {
    return {
      
    };
  },

  mounted() {
    
  },

  methods: {
    
  },
};
</script>

<style lang="css" scoped>
  body {
    margin: 0;
    padding: 0;
    background-color: #303033;
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
</style>
