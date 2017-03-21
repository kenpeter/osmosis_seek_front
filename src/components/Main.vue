<template>
  <div class="main">
    <div class="card" v-for="job in jobs">
      <div class="card-header">

      </div>
      <div class="card-block">
        <h4 class="card-title">{{ job.title }}</h4>
        <p class="card-text">Company: {{ job.advertiser }}</p>
        <p class="card-text">Company: {{ job.description }}</p>
        <p class="card-text">Desc: {{ job.description }}</p>
        <p class="card-text">Type: {{ job.employmentType }}</p>
        <p class="card-text">Posted: {{ job.datePosted }}</p>
        <a :href="job.url" class="btn btn-primary" target="_blank">Go</a>
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
  methods: {
    // ok.... shit.....
    // have a look at data() {}
    // basically data() is shorthand
    loadJob() {
      this.axios.get('http://seekback.shopshop.space/job/list').then((res) => {
        this.jobs = res.data;
        // console.log(res.data);
      },
      (err) => {
        /* eslint no-console: ["error", { allow: ["warn", "error", "log"] }] */
        console.log(err);
      });
    },
  },
  mounted() {
    this.loadJob();
  },
};
</script>

<style scoped>

</style>
