<template>
  <!-- <HelloWorld /> -->
  <v-app-bar :elevation="1" rounded>
    <!-- <template v-slot:prepend>
    <v-app-bar-nav-icon></v-app-bar-nav-icon>
  </template> -->

    <v-app-bar-title>Piutang Unit</v-app-bar-title>
  </v-app-bar>
  <v-breadcrumbs :items="items">
    <template v-slot:divider>
      <v-icon icon="mdi-chevron-right"></v-icon>
    </template>
  </v-breadcrumbs>
  <div class="d-flex justify-end mr-2">
    <v-btn color="blue" class="my-2 mr-2" @click="refresh"> Refresh </v-btn>
    <v-btn color="blue" class="my-2" @click="bayar"> Bayar </v-btn>
  </div>

  <v-card flat>
    <v-card-title class="d-flex align-center pe-2">
      Tabel Piutang

      <v-spacer></v-spacer>

      <v-text-field
        v-model="search"
        prepend-inner-icon="mdi-magnify"
        density="compact"
        label="Search"
        single-line
        flat
        hide-details
        variant="solo-filled"
      ></v-text-field>
    </v-card-title>

    <v-divider></v-divider>
    <v-data-table
      v-model:search="search"
      v-model="selected"
      :headers="headers"
      :items="datas"
      items-per-page="5"
      item-value="id"
      return-object
      show-select
      select-strategy="single"
    ></v-data-table>
  </v-card>

  <!-- <pre>{{ selected }}</pre> -->
</template>

<script lang="ts" setup>
//
import { ref, reactive } from "vue";
const selected = ref([]);
const search = ref("");
const items = [
  {
    title: "Home",
    disabled: false,
    href: "/",
  },
  {
    title: "Daftar Piutang Unit",
    disabled: false,
    href: "/",
  },
];

const headers = [
  {
    title: "No Kewajiban",
    align: "start",
    key: "id",
  },
  { title: "Nomor Polisi", align: "end", key: "nopol" },
  { title: "Pemilik", align: "end", key: "owner" },
  { title: "Peserta", align: "end", key: "participant" },
  { title: "Nomor VA", align: "end", key: "va" },
  { title: "Harga Terbentuk (Rp)", align: "end", key: "ht" },
  { title: "Biaya Admin ex PPN (Rp)", align: "end", key: "admin" },
  { title: "PPN (Rp)", align: "end", key: "ppn" },
  { title: "Total (Rp)", align: "end", key: "total" },
  { title: "Tanggal Lelang", align: "end", key: "auction_date" },
  { title: "Tanggal Jatuh Tempo", align: "end", key: "tempo_date" },
  { title: "Tanggal Lunas", align: "end", key: "completed_date" },
  { title: "Status", align: "end", key: "status" },
];

let datas = reactive([
  {
    id: "B20116005069",
    nopol: "KT 3090 BJS",
    owner: "PT OLX",
    participant: "SUJONO",
    va: "",
    ht: 93850000,
    admin: 0,
    ppn: 0,
    total: 93850000,
    auction_date: "2020-11-11",
    tempo_date: "2020-11-17",
    completed_date: "",
    status: "Konfirmasi Pembayaran",
  },
  {
    id: "B20116005070",
    nopol: "KT 3090 BJS",
    owner: "PT OLX",
    participant: "SUJONO",
    va: "",
    ht: 13950000,
    admin: 0,
    ppn: 0,
    total: 13950000,
    auction_date: "2020-11-10",
    tempo_date: "2020-11-16",
    completed_date: "2020-11-14",
    status: "Lunas",
  },
  {
    id: "B20116005071",
    nopol: "KT 3090 BJS",
    owner: "PT OLX",
    participant: "SUJONO",
    va: "",
    ht: 93850000,
    admin: 0,
    ppn: 0,
    total: 93850000,
    auction_date: "2020-11-11",
    tempo_date: "2020-11-17",
    completed_date: "",
    status: "Konfirmasi Pembayaran",
  },
  {
    id: "B20116005072",
    nopol: "KT 3090 BJS",
    owner: "PT OLX",
    participant: "SUJONO",
    va: "",
    ht: 93850000,
    admin: 0,
    ppn: 0,
    total: 93850000,
    auction_date: "2020-11-11",
    tempo_date: "2020-11-17",
    completed_date: "",
    status: "Konfirmasi Pembayaran",
  },
  {
    id: "B20116005073",
    nopol: "KT 3090 BJS",
    owner: "PT OLX",
    participant: "SUJONO",
    va: "",
    ht: 13950000,
    admin: 0,
    ppn: 0,
    total: 13950000,
    auction_date: "2020-11-10",
    tempo_date: "2020-11-16",
    completed_date: "2020-11-14",
    status: "Lunas",
  },
  {
    id: "B20116005074",
    nopol: "KT 3090 BJS",
    owner: "PT OLX",
    participant: "SUJONO",
    va: "",
    ht: 93850000,
    admin: 0,
    ppn: 0,
    total: 93850000,
    auction_date: "2020-11-11",
    tempo_date: "2020-11-17",
    completed_date: "",
    status: "Konfirmasi Pembayaran",
  },
  {
    id: "B20116005075",
    nopol: "KT 3090 BJS",
    owner: "PT OLX",
    participant: "SUJONO",
    va: "",
    ht: 93850000,
    admin: 0,
    ppn: 0,
    total: 93850000,
    auction_date: "2020-11-11",
    tempo_date: "2020-11-17",
    completed_date: "",
    status: "Konfirmasi Pembayaran",
  },
  {
    id: "B20116005076",
    nopol: "KT 3090 BJS",
    owner: "PT OLX",
    participant: "SUJONO",
    va: "",
    ht: 13950000,
    admin: 0,
    ppn: 0,
    total: 13950000,
    auction_date: "2020-11-10",
    tempo_date: "2020-11-16",
    completed_date: "2020-11-14",
    status: "Lunas",
  },
  {
    id: "B20116005077",
    nopol: "KT 3090 BJS",
    owner: "PT OLX",
    participant: "SUJONO",
    va: "",
    ht: 93850000,
    admin: 0,
    ppn: 0,
    total: 93850000,
    auction_date: "2020-11-11",
    tempo_date: "2020-11-17",
    completed_date: "",
    status: "Konfirmasi Pembayaran",
  },
  {
    id: "B20116005078",
    nopol: "KT 3090 BJS",
    owner: "PT OLX",
    participant: "SUJONO",
    va: "",
    ht: 93850000,
    admin: 0,
    ppn: 0,
    total: 93850000,
    auction_date: "2020-11-11",
    tempo_date: "2020-11-17",
    completed_date: "",
    status: "Konfirmasi Pembayaran",
  },
  {
    id: "B20116005079",
    nopol: "KT 3090 BJS",
    owner: "PT OLX",
    participant: "SUJONO",
    va: "",
    ht: 13950000,
    admin: 0,
    ppn: 0,
    total: 13950000,
    auction_date: "2020-11-10",
    tempo_date: "2020-11-16",
    completed_date: "2020-11-14",
    status: "Lunas",
  },
  {
    id: "B20116005080",
    nopol: "KT 3090 BJS",
    owner: "PT OLX",
    participant: "SUJONO",
    va: "",
    ht: 93850000,
    admin: 0,
    ppn: 0,
    total: 93850000,
    auction_date: "2020-11-11",
    tempo_date: "2020-11-17",
    completed_date: "",
    status: "Konfirmasi Pembayaran",
  },
  {
    id: "B20116005081",
    nopol: "KT 3090 BJS",
    owner: "PT OLX",
    participant: "SUJONO",
    va: "",
    ht: 93850000,
    admin: 0,
    ppn: 0,
    total: 93850000,
    auction_date: "2020-11-11",
    tempo_date: "2020-11-17",
    completed_date: "",
    status: "Konfirmasi Pembayaran",
  },
  {
    id: "B20116005082",
    nopol: "KT 3090 BJS",
    owner: "PT OLX",
    participant: "SUJONO",
    va: "",
    ht: 13950000,
    admin: 0,
    ppn: 0,
    total: 13950000,
    auction_date: "2020-11-10",
    tempo_date: "2020-11-16",
    completed_date: "2020-11-14",
    status: "Lunas",
  },
  {
    id: "B20116005083",
    nopol: "KT 3090 BJS",
    owner: "PT OLX",
    participant: "SUJONO",
    va: "",
    ht: 93850000,
    admin: 0,
    ppn: 0,
    total: 93850000,
    auction_date: "2020-11-11",
    tempo_date: "2020-11-17",
    completed_date: "",
    status: "Konfirmasi Pembayaran",
  },
]);
let tempDatas = [];
const saveTemp = () => {
  tempDatas = datas;
};

// saveTemp();
const bayar = () => {
  console.log(selected.value[0].id);
  const selectedId = selected.value[0].id;
  const filter = datas.map((item) => {
    if (item.id === selectedId) {
      item.status = "Lunas";
    }
    return { ...item };
  });
  // console.log(filter);
  datas = filter;
};

const refresh = () => {
  // console.log(selected.value[0].id);
  // const selectedId = selected.value[0].id;
  // const filter = datas.map((item) => {
  //   if (item.id === selectedId) {
  //     item.status = "Lunas";
  //   }
  //   return { ...item };
  // });
  // console.log(filter);
  datas = tempDatas;
};
</script>
