<template>
  <section>
    <div class="container">
      <div class="row d-flex justify-content-center">
        <div class="col col-12 col-md-6 col-lg-4 col-xl-3" v-for="car in this.CarsList.data" :key="car">
          <img class="img-fluid py-2 col" :src="car.image">
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "CustomCarsList",

  data(){
    return{
      CarsList: []
    }
  },
  async fetch() {
    this.CarsList = await fetch(
      'https://autowelt.mk/api/vehicles'
    ).then(res => res.json())
  }
};
</script>

<style scoped>

</style>
