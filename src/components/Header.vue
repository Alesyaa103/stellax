<template>
  <div class="container-fluid d-xl-flex justify-content-xl-between pt-xl-1">
    <b-navbar-brand href="#"><img src="../assets/src_assets_logo.png" style="width:30px" alt="Here is logo"></b-navbar-brand>
    <div class="account d-xl-flex">
        <div class="account__name mr-xl-1">
            Username
        </div>
        <i class="fas fa-3x fa-user-circle "></i>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style scoped>
    .fa-user-circle{
        font-size:24px;
    }
</style>