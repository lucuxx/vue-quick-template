<template>
  <div class="about">
    <h1>在这里添加更多内容吧！{{data}}</h1>
    <h1>newData:{{newData}}</h1>
    <input type="button" @click="btn" value="click" />
  </div>
</template>
<script>
export default {
  data() {
    return {
      data:''
    }
  },
  watch:{
    data:{
      handler(newVal,oldVal){
        console.log('watch')
      },
      immediate:true
    }
  },
  computed:{
    newData({data}){
      console.log('computed')
      return  data+'data+computed'
    }
  },
  created(){
    console.log('creted')
    this.data='craetedChangData'
  },
  mounted(){
 
  },
  methods: {
    btn() {

      // setTimeout(function() {
      //   loading.close()
      // }, 2000)
    },
  },
}
</script>
