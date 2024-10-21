<template>
  <div class="container">
    <div class="row">
      <h1>Phones App</h1>
      <add-phone @new-phone="savePhone"></add-phone>
      <phones-table
        @delete-phone="deletePhone"
        @show-brand="finalName"
        @change-phone="finalChange"
        :phones="phones"
      ></phones-table>
    </div>
  </div>
</template>

<script>
import AddPhone from "./components/AddPhone.vue";
import PhonesTable from "./components/PhonesTable.vue";
export default {
  methods: {
    finalChange(id) {
      let currentPhone = this.phones.find((phone) => phone.id === id);
      currentPhone.available = false;
    },
    finalName(brand) {
      let currentBrand = (this.phones.brand = brand);
      alert(currentBrand);
    },
    savePhone(newPhone) {
      this.phones.push(newPhone);
    },
    deletePhone(id) {
      this.phones = this.phones.filter((phone) => phone.id !== id);
    },
  },
  components: { PhonesTable, AddPhone },
  data() {
    return {
      phones: [
        {
          id: 1,
          brand: "Apple",
          name: "iPhone 14 Pro",
          price: 1200,
          available: true,
        },
        {
          id: 2,
          brand: "Samsung",
          name: "Galaxy S23",
          price: 1100,
          available: true,
        },
        {
          id: 3,
          brand: "Google",
          name: "Pixel 8",
          price: 900,
          available: false,
        },
        {
          id: 4,
          brand: "Xiaomi",
          name: "Mi 12",
          price: 700,
          available: true,
        },
        {
          id: 5,
          brand: "OnePlus",
          name: "OnePlus 11",
          price: 800,
          available: true,
        },
        {
          id: 6,
          brand: "Huawei",
          name: "P50 Pro",
          price: 950,
          available: false,
        },
        {
          id: 7,
          brand: "Sony",
          name: "Xperia 1 V",
          price: 1000,
          available: true,
        },
        {
          id: 8,
          brand: "Nokia",
          name: "G50",
          price: 400,
          available: true,
        },
        {
          id: 9,
          brand: "Oppo",
          name: "Find X5 Pro",
          price: 850,
          available: false,
        },
        {
          id: 10,
          brand: "Motorola",
          name: "Edge 40",
          price: 750,
          available: true,
        },
      ],
    };
  },
};
</script>

<style></style>
