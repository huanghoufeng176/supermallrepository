<template>
  <div class="nav-bar">
    <slot></slot>
  </div>
</template>

<script>
export default {
  components:{},
  data(){
    return {
    }
  },
  created(){},
  mounted(){},
  watch:{},
  computed:{},
  methods:{},
}
</script>
<style scoped>
  /* .nav-bar{
    background-color: pink;
    height: 39px;
    display: flex;
  } */
  .nav-bar{
    position:fixed;
    left: 0;
    right: 0;
    top: 0;
    z-index: 3;
  }
</style>