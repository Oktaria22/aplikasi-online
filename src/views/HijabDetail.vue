<template>
  <div class="hijab-detail">
    <Navbar />
    <div class="container">
      <div class="row mt-4">
        <div class="col">
          <nav aria-label="breadcrumb">
            <ol class="breadcrumb">
              <li class="breadcrumb-item">
                  <router-link to="/" class="text-dark">Home</router-link>
                </li>
                 <li class="breadcrumb-item">
                  <router-link to="/Hijab" class="text-dark">Hijab</router-link>
                </li>
              <li class="breadcrumb-item active" aria-current="page">Hijab Order</li>
            </ol>
          </nav>
        </div>
      </div>

    <div class="row mt-4">
      <div class="col-md-6">
          <img :src=" '../assets/images/' + product.gambar " class="img-fluid shadow" />
      </div>
        <div class="col-md-6">
            <h2><strong>{{ product.nama }}</strong></h2>
            <hr>
            <h4>Harga : <strong>Rp. {{ product.harga }} </strong></h4>

            <form class="mt-4" v-on:submit.prevent>
              <div class="form-group">
                <label for="jumlah_pemesanan">Jumlah Pesan</label>
                <input type="number" class="form-control"  v-model="pesan.jumlah_pesanan"/>
              </div>
                <div class="form-group">
                  <label for="keterangan">Keterangan</label>
                  <textarea 
                  v-model="pesan.keterangan"
                  
                  class="form-control" placeholder="Keterangan spt : Warna Sesuai Dengan Yang Di Klik/Order"></textarea>
                </div>
                <button type="submit" class="btn btn-success" @click="pemesanan">
                  <b-icon-cart>
                  </b-icon-cart>Order</button>
            </form>
        </div>
    </div>

    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import axios from 'axios';



export default {
  name: "HijabDetail",
  components: {
    Navbar,
  },
data() {
    return {
        product: {},
        pesan: {}
    };
},
methods: {
    setProduct(data) {
        this.product = data
    },
    pemesanan() {
        this.pesan.products = this.product;
      axios
        .post("http://localhost:3000/keranjang", this.pesan)
        .then(() => {
          this.$toast.success("Sukses Masuk Keranjang.", {
             type: 'success',
             position: 'top-right',
             duration: 3000,
             dismissible: true
          });
        })
        .catch((err) => console.log (err));

        
//         }else {
//              this.$toast.error("Jumlah Pesanan Harus Diisi.", {
//             type: 'error',
//             position: 'top-right',
//             duration: 5000,
//             dismissible: true
//           });
//         }
        
     },
 },
    mounted() {
         axios
      .get("http://localhost:3000/products/"+this.$route.params.id)
      .then((response) => this.setProduct(response.data))
      .catch((error) => console.log(error));
    }


};
</script>

<style>
</style>