<template>
  <div class="col-8">
    <table class="table table-striped table-bordered table-hover table-dark">
      <thead>
        <tr>
          <th>ID</th>
          <th>Brand</th>
          <th>Name</th>
          <th>Price</th>
          <th>Avalible</th>
          <th>Delete</th>
        </tr>
      </thead>
      <tbody>
        <mobile-phone
          @delete-phone="deletePhone"
          @my-brand="showBrandName"
          @my-event="changeAvalible"
          v-for="phone in phones"
          :phone="phone"
          :key="phone.id"
        ></mobile-phone>
      </tbody>
    </table>
  </div>
</template>

<script>
import MobilePhone from "./MobilePhone.vue";
export default {
  props: ["phones"],
  components: { MobilePhone },
  methods: {
    changeAvalible(id) {
      this.$emit("change-phone", id);
    },
    showBrandName(brand) {
      this.$emit("show-brand", brand);
    },
    deletePhone(id) {
      this.$emit("delete-phone", id);
    },
  },
  emits: ["change-phone", "delete-phone"],
};
</script>

<style></style>
