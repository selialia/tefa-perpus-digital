<template>
    <div class="container-fluid">
      <div class="row">
        <div class="col-lg-12">
          <div class="row">
            <div class="col-lg-2">
             <div class="card mb-3">
              <div class="card-body">
            <img src="assets/img/cover1.jpg" class="cover" alt="cover 1">
          </div>
        </div>
      </div>
      <div class="col-lg-10 text">
        <h1>Tukar Takdir</h1><br>
        <p>Pengarang : Valiant Budi</p>
        <P>Penerbit : Gramedia Pustaka Utama</P>
        <p>Tahun Terbit : 2019</p>
        <p>Deskripsi : bercerita mengenai perkara yang kita takuti dan pasti terjadi dalam 12 nasib yang salah satunya mungkin pernah, sedang, atau akan jadi milikmu.</p>
      </div>
    </div>
    <div>
      <nuxt-link to="../"><button type="submit" class="btn btn-lg rounded-5 px-5 bg-success text-white" style="float: right; margin-top: 15px;">KEMBALI</button></nuxt-link>
    </div>
    </div>
    </div>
  </div>
</template>

<style scoped>
.cover{
  height: 300px;
  width: 200px;
}
.card.mb-3 {
  margin-top: 50px;
  margin-left: 20px;
  height: 340px;
  width: 235;
}
h3 {
  margin-top: 50px;
  margin-left: 20px;
  margin-bottom: 1px;
}
p {
  margin-left: 20px;
  margin-bottom: 7px;
}

.text {
  margin-top: 100px;
}
</style>