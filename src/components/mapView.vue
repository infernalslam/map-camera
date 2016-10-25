<template lang="html">
  <div class="map">
    <img :src="image" class="image"/>
  </div>
</template>

<script>
export default {
  data () {
    return {}
  },
  computed: {},
  mounted () {},
  methods: {},
  components: {},
  props: ['image']
}
</script>

<style lang="css" scoped>
.map {
  background-color: grey;
  /*position: relative;*/
}
.image {
  position: absolute;
    width: 75%;
    height: auto;
}
</style>
