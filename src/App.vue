<template>
  <div>
    <app-navbar></app-navbar>
    <app-sidebar></app-sidebar>
    <app-content></app-content>
  </div>
</template>
<script>
  import appContent from "./components/Content"
  import appSidebar from "./components/Sidebar"
  import appNavbar from "./components/Navbar"
export default {
  components : {
    appContent,
    appSidebar,
    appNavbar
  }
}
</script>

<style>

</style>
