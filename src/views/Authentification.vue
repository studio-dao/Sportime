<template>
  <div class="about">
    <Connection/>
  </div>
</template>

<script>
import Connection from "../components/Connection.vue";


export default {
  name: "Homepage",

  components: {
   Connection,
  },

  props: {
    msg: String,
  },
  data() {
    return {};
  },
};
</script>

