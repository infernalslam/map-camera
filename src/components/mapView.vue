<template lang="html">
  <div class="map">
    <div v-for="camera in totalCamera" :style="{'background': camera.color, 'top': camera.y + 'px', 'left': camera.x + 'px', 'position': 'absolute', 'width': '30px', 'height': '30px'}">
    </div>
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
  props: ['image', 'totalCamera']
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
