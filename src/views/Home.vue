<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="欢迎使用vue-cool-cli创建应用" />
    <h3>基础模板已经搭建完成，直接使用即可</h3>
    <div style="height:3000px;"></div>
    <button @click="download">下载</button>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HelloWorld,
  },
  methods:{
    download(){
      axios.get('http://127.0.0.1:3000/load').then(res => {

        this.funDownload(res.data,'test.docx')
      })
    },
    funDownload (content, filename) {
    // 创建隐藏的可下载链接
    var eleLink = document.createElement('a');
    eleLink.download = filename;
    eleLink.style.display = 'none';
    // 字符内容转变成blob地址
    var blob = new Blob([content]);
    eleLink.href = URL.createObjectURL(blob);
    // 触发点击
    document.body.appendChild(eleLink);
    eleLink.click();
    // 然后移除
    document.body.removeChild(eleLink);
}
  }
}
</script>
