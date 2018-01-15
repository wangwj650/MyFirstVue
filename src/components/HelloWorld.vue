<template>
  <div class="hello">
    <Vmarked></Vmarked>
    <Vheader></Vheader>
    <h1>{{ msg }}</h1>
    <span @click='show'>点击呀</span>
    <ul>
      <li v-for='item in citys'>{{item}}</li>
    </ul>
    <img :src='logo'/>
    <h2>Essential Links</h2>
    <ul>
      <li>
        <a
          href="https://vuejs.org"
          target="_blank"
        >
          Core Docs
        </a>
      </li>
      <li>
        <a
          href="https://forum.vuejs.org"
          target="_blank"
        >
          Forum
        </a>
      </li>
      <li>
        <a
          href="https://chat.vuejs.org"
          target="_blank"
        >
          Community Chat
        </a>
      </li>
      <li>
        <a
          href="https://twitter.com/vuejs"
          target="_blank"
        >
          Twitter
        </a>
      </li>
      <br>
      <li>
        <a
          href="http://vuejs-templates.github.io/webpack/"
          target="_blank"
        >
          Docs for This Template
        </a>
      </li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li>
        <a
          href="http://router.vuejs.org/"
          target="_blank"
        >
          vue-router
        </a>
      </li>
      <li>
        <a
          href="http://vuex.vuejs.org/"
          target="_blank"
        >
          vuex
        </a>
      </li>
      <li>
        <a
          href="http://vue-loader.vuejs.org/"
          target="_blank"
        >
          vue-loader
        </a>
      </li>
      <li>
        <a
          href="https://github.com/vuejs/awesome-vue"
          target="_blank"
        >
          awesome-vue
        </a>
      </li>
    </ul>
    <Vfooter @cityclick='footerclick' :citys='citys'></Vfooter>
  </div>
</template>

<script>
import logo from '../assets/logo.png'
//使用子组件第1步，先引入;第2步,挂载到父组件
import Vheader from '../Vheader.vue'
import Vfooter from '../Vfooter.vue'
import Vmarked from '../Vmarked.vue'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      citys:['北京', '广州', '上海', '深圳'],
      logo:logo
    }
  },
  methods:{
    show: function() {
      console.log('Show 被点击了');
      this.citys.push('东京');
    },
    footerclick: function(data) {
      //console.log('触发了');
      this.citys.push(data);
    }
  },
  components: {
    //需要挂载到父组件 多个加逗号分隔开
    Vheader,Vfooter,Vmarked
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
