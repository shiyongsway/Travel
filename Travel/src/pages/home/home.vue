<template>
  <div>
    <HomeHeader></HomeHeader>
  </div>
</template>
<script>
  import HomeHeader from './components/header'

  export default {
      name:'Home',
    components:{
      HomeHeader
    },
      data(){
        name: "home"
      },
      methods:{

      }
    }
</script>
<style scoped>

</style>
