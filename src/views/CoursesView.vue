<template>
  <div class="course">
    <h3 class="title left-aligned-text">Jelajahi Course</h3>
    <b-row class="left-aligned-text">
      <b-col class="kategori" sm="3" cols="12">
        <h4 class="title-2">Kategori</h4>
        <h6 v-for="(item, index) in items.data" :key="index" :value="index">{{ item.name }}</h6>

        <!-- Elemen select untuk memilih kategori -->
        <b-form-group label="Pilih Kategori" v-slot="{ ariaDescribedby }">
          <b-form-select v-model="selected" :aria-describedby="ariaDescribedby">
            <option v-for="(item, index) in items.data" :key="index" :value="index">{{ item.name }}</option>
          </b-form-select>
        </b-form-group>

      </b-col>

      <b-col class="list" sm="9" cols="12">
        <b-row>
          <b-col cols="8" sm="4" v-for="course in courses" :key="course.slug">
            <div class="card">
              <div class="card-head">
                <img src="course.image" />
              </div>
              <div class="card-body">
                <span class="card-rating">⭐{{ course.rating }}</span>
                <h5 class="card-title">{{ course.name }}</h5>
                <h6 class="card-harga">Rp. {{ course.price }}</h6>
                <hr/>
                <div class="d-flex justify-content-between">
                  <span> </span>
                  <a class="card-view" href="#">View Details</a>
                </div>
              </div>
            </div>
          </b-col>
        </b-row>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      selected: [0],
      items: [],
    };
  },
  mounted() {
    // Data yang akan dikirim dalam permintaan POST
    const postData = {};

    // Header key dan values yang akan dikirimkan dalam permintaan POST
    const headers = {
      signature: "935c150521d1b764d5a9ffb1640c3618",
      Authorization: "Bearer KarismaAcademy-05-08-23",
    };

    // Contoh permintaan POST ke API dengan header key dan values menggunakan Axios
    axios
      .post("https://test.karismaacademy.com/api/course", postData, { headers })
      .then((response) => {
        this.items = response.data;
        console.log("fetch berhasil...");
        // console.log(this.items);
        // console.log("Respon data:", response.data);
      })
      .catch((error) => {
        console.error("Gagal mempost data:", error);
      });
  },
  computed: {
    // Membuat computed property untuk mengakses "courses name" dari data JSON
    courses() {
      const selectedIndex = parseInt(this.selected);
      console.log(selectedIndex);
      if (selectedIndex >= 0 && selectedIndex < this.items.data.length) {
        return this.items.data[selectedIndex].courses;
      } else {
        return []; // Jika indeks tidak valid, return array kosong
      }
    },
  },
};
</script>

<style>
.kategori {
  /* background-color: red; */
}
.list {
  /* background-color: blue; */
}
.card{
  border-radius: 0px 0px 6.871px 6.871px;
  background: #FFF;
}
.card-rating{
  padding: 1.374px 6.871px;
  border-radius: 68.709px;
  background: rgba(0, 0, 0, 0.10);
}
.card-title{
  color: #000;
font-family: Poppins;
font-size: 15.116px;
font-style: normal;
font-weight: 600;
line-height: normal;
}
.card-harga{
  color: #FF5C00;
font-family: Poppins;
font-size: 16.49px;
font-style: normal;
font-weight: 600;
line-height: 20.613px; /* 125% */
}
.card-view{
  color: #000;
font-family: Poppins;
font-size: 9.619px;
font-style: normal;
font-weight: 600;
line-height: 17.864px; /* 185.714% */
}
</style>
