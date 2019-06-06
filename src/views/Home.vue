<template>
<section>



<SideNav></SideNav>


  <HelloWorld class=""></HelloWorld>





</section>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import SideNav from '@/components/SideNav.vue'
export default {
  name: 'home',
  components: {
    HelloWorld,SideNav
  }
}
</script>

<style>
.home{
}
</style>
