<template>
  <div class="container-fluid">
    <div class="row my-5">
      <div class="col-lg-6">
        <nuxt-link to="/pengunjung/tambah">
          <div class="card bg-pengunjung rounded-5">
            <div class="card-body">
              <h2>pengunjung</h2>
            </div>
          </div>
        </nuxt-link>
      </div>
      <div class="col-lg-6">
        <nuxt-link to="/buku">
          <div class="card bg-buku rounded-5">
            <div class="card-body">
              <h2>Cari Buku</h2>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
  <h1 class="statistik">STATISTIK</h1>

  <div class="container-fluid">
    <div class="row my-5">
      <div class="col-lg-6">
        <nuxt-link to="/pengunjung">
          <div class="card bg-warning rounded-5">
            <div class="card-body">
              <h4 class="jumlah">{{ jumlahpengunjung }} Pengunjung</h4>
            </div>
          </div>
        </nuxt-link>
      </div>

      <div class="col-lg-6">
        <nuxt-link to="/buku">
          <div class="card bg-success rounded-5">
            <div class="card-body">
              <h5 class="buku">{{ jumlahbuku }} Buku</h5>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>
    <div>
      <Chart />
    </div>
  </div>
</template>

<script setup>
const supabase = useSupabaseClient();
const jumlahpengunjung = ref(0);
const jumlahbuku = ref(0);

async function ambiljumlahpengunjung() {
  const { data, error, count } = await supabase
    .from("pengunjung")
    .select("*", { count: "exact" });
  if (count) jumlahpengunjung.value = count;
}

async function ambiljumlahbuku() {
  const { data, error, count } = await supabase
    .from("buku")
    .select("*", { count: "exact" });
  if (count) jumlahbuku.value = count;
}

onMounted(() => {
  ambiljumlahpengunjung();
  ambiljumlahbuku();
});
</script>

<style scoped>
* {
  text-decoration: none;
}
.card {
  height: 250px;
  box-shadow: 1px 1px 10px #424242;
}
.card.bg-pengunjung {
  margin-top: 5%;
  background-image: url("../assets/img/bg-home-kunjungan.jpeg");
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
  opacity: 70%;
}
.card.bg-buku {
  margin-top: 5%;
  background: url("../assets/img/bg-home-cari-buku.jpg");
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
  opacity: 70%;
}
h2 {
  color: black;
  font: arial;
}
h1 {
  color: white;
}
.card.bg-warning {
  margin-top: 3%;
}
.card.bg-success {
  margin-top: 3%;
}
.statistik {
  color: black;
  margin-left: 50px;
}
h5 {
  text-align: center;
  margin-top: 80px;
  font-size: 300%;
  color: black;
}
h4 {
  text-align: center;
  margin-top: 80px;
  font-size: 300%;
  color: black;
}
</style>
