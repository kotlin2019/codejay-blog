<!-- NavBar -->
<template>
  <div class="navbar">
    <ul class="navbar-box"> 
      <li v-for="(item,index) in menu" @click="itemClick(item.path)">
        <i class="iconfont" v-html="item.iconUrl"></i>
        {{item.name}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'NavBar',
  data() {
    return {
      menu:[
        {name:'首页',iconUrl:'&#xe652;',path:'/'},
        {name:'文章列表',iconUrl:'&#xe60e;',path:'/article'},
        {name:'实战案例',iconUrl:'&#xe658;',path:'/demo'},
        {name:'关于博主',iconUrl:'&#xe638;',path:'/about'},
        {name:'素材&工具',iconUrl:'&#xe767;',path:'/tool'},
        {name:'GitHub',iconUrl:'&#xe628;',path:''},
        {name:'登录/注册',iconUrl:'&#xe611;',path:'/login'}
      ]
    }
  },
  computed:{
    
  },
  methods:{
    itemClick(path) {
      if(path){
        this.$router.replace(path);
      }else {
        location.href="https://github.com/Jay-wj";
      }
    }
  }
}

</script>

<style scoped>

  .navbar {
    width: 100%;
    height: 100%;
  }

  .navbar ul {
    list-style: none;
    display: flex;
  }

  ul li {
    font-size: 14px;
    cursor: pointer;
    align-items: center;
    padding: 0 1rem;
    color: #fff;
  }

  li:hover {
    color: #9466ff;
  }
  @media screen and (max-width:930px) {
    .navbar-box {
      display: none !important;
    }
  }
</style>