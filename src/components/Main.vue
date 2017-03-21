<template>
  <div class="main">
    <div class="card">
      <div class="card-header">
        Featured
      </div>
      <div class="card-block">
        <h4 class="card-title">Special title treatment</h4>
        <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
        <a href="#" class="btn btn-primary">Go somewhere</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      jobs: [],
    };
  },
  mounted: () => {
    this.loadJob();
  },
  methods: {
    loadJob: () => {
      this.axios.get('http://seekback.shopshop.space/job/list').then((res) => {
        this.jobs = res.data;
        console.log(res.data);
      },
      (err) => {
        /* eslint no-console: ["error", { allow: ["warn", "error", "log"] }] */
        console.log(err);
      });
    },
  },
};
</script>

<style scoped>

</style>
