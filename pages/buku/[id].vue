<template>
  <div class="bg">
    <div class="row">
      <div class="col-lg-12">
        <div class="icon mt-4">
          <NuxtLink to="/buku/"> </NuxtLink>
          <h2 class="text-start text-dark my-4 text-center"> {{ buku.judul }}</h2>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-4 text-dark d-flex flex-column justify-content-center">
        <h4>detail buku:</h4>
        <h5>penulis: {{ buku.penulis }}</h5>
        <h5>tahun terbit: {{ buku.tahun_terbit }}</h5>
        <h5>penerbit: {{ buku.penerbit }}</h5>
      </div>
      <div class="col-4 d-flex flex-column justify-content-center align-items">
        <div class="mb-5">
          <div class="card-body">
            <img :src="buku.cover" class="ukuran center" />
          </div>
        </div>
      </div>
    </div>
    <div class="row text-dark">
      <div class="col">
        <h4 class="text-dark">Deskripsi</h4>
        <h5>{{ buku.deskripsi }}</h5>
      </div>
    </div>
    <NuxtLink to="/buku/">
        <button type="submit" class="btn btn-dark btn-lg rounded-5 px-5">kembali</button>
    </NuxtLink>
  </div>
</template>

<script setup>
const supabase = useSupabaseClient();

const route = useRoute();

const buku = ref([]);

const getBooksById = async () => {
  const { data, error } = await supabase.from("buku").select(`*, kategori(*)`).eq("id", route.params.id);
  if (data) buku.value = data[0];
};

onMounted(() => {
  getBooksById();
});
</script>

<style scoped>
.bg {
  background-image: url(assets/img/zzz.webp);
}
.ukuran {
  width: 180px;
  display: flex;
}
</style>




