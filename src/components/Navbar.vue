<template>
  <div>
    <nav class="main-header navbar navbar-expand navbar-white navbar-light">
      <!-- Left navbar links -->
      <ul class="navbar-nav">
        <li class="nav-item">
          <a class="nav-link"  @click="sideBarToggle"  v-on:click="sideBar = !sideBar" role="button"><i class="fas fa-bars"></i></a>
        </li>
      </ul>
      <!-- Right navbar links -->
      <ul class="navbar-nav ml-auto">
        <!-- Messages Dropdown Menu -->
        <li class="nav-item dropdown">
          <a class="nav-link" data-toggle="dropdown">
            <i class="far fa-user"> </i>
            Çıkış
          </a>
        </li>
      </ul>
    </nav>
    <div id="sidebar-overlay" @click="overlay"></div>
  </div>
</template>
<script>
export default {

  data () {
    return {
      sideBar : true,
      windowWidth: window.innerWidth

    }
  },
  mounted() {
    window.onresize = () => {
      this.windowWidth = window.innerWidth
      if(this.windowWidth <= 1008){
        document.body.classList.add('sidebar-closed')
        document.body.classList.add('sidebar-collapse')
      }
      else if (this.windowWidth > 1008){
        document.body.classList.remove('sidebar-closed')
        document.body.classList.remove('sidebar-collapse')
        document.body.classList.remove('sidebar-open')
        this.sideBar = true
        console.log(this.sideBar)

      }}
  },
  methods:{
    sideBarToggle(){
      if (this.windowWidth < 992){
        console.log(this.windowWidth)
        console.log(this.sideBar)
        document.body.classList.add('sidebar-open')
        document.body.classList.remove('sidebar-closed')
        document.body.classList.remove('sidebar-collapse')
      }else{
        if(this.sideBar){
          console.log(this.windowWidth)
          console.log(this.sideBar)

          document.body.classList.add('sidebar-collapse')
        }else{
          console.log(this.windowWidth)
          console.log(this.sideBar)

          document.body.classList.remove('sidebar-collapse')
        }
      }
    },
    overlay(){
      document.body.classList.remove('sidebar-open')
      document.body.classList.add('sidebar-closed')
      document.body.classList.add('sidebar-collapse')
    }
  },
}
</script>
<style scoped>

</style>
