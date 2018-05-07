<template>
  <div class="hello">
  <input type="text" v-model="namaDepan">
    <h1>Nama saya {{ namaDepan }}</h1>
    <h2>Dan <span v-html="namaBelakang"></span></h2>
    <h3>Umur saya {{umur + 1}} tahun</h3>
    <h3>Status Saya {{status? 'jomblo' : 'single'}}</h3>
    <h3>Saya 
    <span v-if="umur < 10"> Masih unyu unyu</span>
    <span v-else-if="umur > 10 && umur < 25">Masih Remaja</span>
    </h3>
    <a v-bind:href=link>facebook</a>
    <ul>
      <li v-for="mantan in daftarMantan">
         <p>Nama : {{mantan.nama}}</p>
         <p>Umur : {{mantan.umur}}</p>
      </li>
      <button @click="sapa(namaDepan)">Klik disini</button>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      link: "https://www.facebook.com",
      msg: "Welcome to Your Vue.js App",
      namaDepan: "Hazar",
      namaBelakang: "<b>Ganteng</b>",
      umur: 21,
      status: false,
      daftarMantan: [
        { nama: "Jend", umur: 27 },
        { nama: "Bend", umur: 30 },
        { nama: "Gond", umur: 35 }
      ]
    };
  },
  methods: {
    sapa: function(text) {
      alert("hallo " + text);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
