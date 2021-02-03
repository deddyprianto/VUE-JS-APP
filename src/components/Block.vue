<template>
  <div class="block" v-if="jalankan">
    <h1>haii</h1>
  </div>
  <button @click="stopMain">Stoped</button>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      jalankan: false,
      waktuini: null,
      reactionTimer: 0,
    };
  },
  mounted() {
    console.log(`component mounted`);
    setTimeout(() => {
      this.jalankan = true;
      this.mulaimain();
    }, this.delay);
  },
  methods: {
    mulaimain() {
      this.waktuini = setInterval(() => {
        this.reactionTimer += 10;
      }, 10);
    },
    stopMain() {
      clearInterval(this.waktuini);
      this.$emit("end", this.reactionTimer);
    },
  },
};
</script>

<style>
.block {
  width: 400px;
  border-radius: 20px;
  background-color: #0faf87;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>
