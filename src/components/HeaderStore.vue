<template>
  <div id="HeaderStore">
    <div class="container">
      <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <!-- logo -->
        <a class="navbar-brand" href="#"><img src="../assets/index.jpg" /></a>
        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        ></button>
        <!-- akhir logo -->
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <div class="col-lg-8">
            <input
              class="form-control mr-sm-2"
              type="search"
              placeholder="Search"
              aria-label="Search"
            />
          </div>
          <div class="col-lg-1">
            <img width="24px" src="../assets/favorit.png" />
          </div>
          <div class="col-lg-1">
            <img width="24px" src="../assets/keranjang.png" />
          </div>
          <div class="col-lg-2">
            <button type="button" class="btn btn-outline-success">
              Success
            </button>
          </div>
          <div class="col-lg-2">
            <button type="button" class="btn btn-success">Success</button>
          </div>
        </div>
      </nav>
    </div>
  </div>
</template>


<script>
export default {
  name: "HeaderStore",
};
</script>

<style>
</style>




