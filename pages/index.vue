<template>
  <div class="container-fluid">
    <div class="row my-5">
      <div class="col-lg-6">
        <nuxt-link to="/pengunjung/tambah">
          <div class="card bg-pengunjung rounded-5">
            <div class="card-body">
              <h2 class="text-white">Pengunjung</h2>
            </div>
          </div>
        </nuxt-link>
      </div>
    

  <div class="col-lg-6">
    <nuxt-link to="/Buku/">
      <div class="card bg-buku rounded-5">
        <div class="card-body">
          <h2 class="text-white">Cari Buku</h2>
        </div>
      </div>
    </nuxt-link>
  </div>
  </div>
  </div>
</template>

<style scoped>
.container-fluid {
  background-image:  url(assets/img/zzz.jpg);
  /*height: 100;
  background-position:  center;
  background-repeat: repeat;
  background-size: cover; */
}
.card {
  height:  250px;
  box-shadow: 1px 1px 1px #424242;
}
.card.bg-pengunjung {
  background-image: url("../assets/img/bg-home-kunjungan.jpeg");
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
}
.card.bg-buku {
  background: url("../assets/img/bg-home-cari-buku.jpg") no-repeat center center;
  background-size: cover;
}
</style>


