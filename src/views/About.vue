<template>
  <div class="content-wrapper">
    <!-- Displays if myData is not set.
    Options
    speed: Number - How many seconds between pulses of the loader.
    height / width: Number - size of the loader contents.
    primaryColor: String - The color of the elements.
    secondaryColor: String - The color of the pulser.
    animate: Boolean - Whether or not to display the pulser.
    -->
    <div v-if="!myData" class="text-center ">
      <list-loader v-for="n in 3" :key="n" :speed="2" :animate="true"></list-loader>
    </div>
    <div v-else class="my-real-content">
      <!-- Your real loaded data goes in here. -->
      <div class="about">
        <h1>This is an about page</h1>
        <p>{{myData}}</p>
      </div>
      <p></p>
    </div>
  </div>
</template>

<script>
import { ListLoader } from "vue-content-loader";

export default {
  components: {
    ListLoader
  },

  data() {
    return {
      myData: null
    };
  },

  mounted() {
    // Just pretend this is an AJAX call. Use your imagination.
    setTimeout(() => {
      this.myData = "Example Data";
    }, 5000);
  }
};
</script>
