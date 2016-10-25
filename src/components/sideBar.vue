<template lang="html">
  <div>
    <aside class="menu">
  <p class="menu-label">
    Tool
  </p>
  <ul class="menu-list">
    <li><a href="#">Upload</a></li>
    <li><a href="#">Edit</a></li>
  </ul>
  <p class="menu-label">
    Camera
  </p>
  <ul class="menu-list">
    <li><a @click="addCam18()">camera 18</a></li>
    <li><a href="#">camera 30</a></li>
    <li><a href="#">camera 40</a></li>
  </ul>
</aside>
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
  props: ['addCam18']
}
</script>

<style lang="css">
/*is-active*/
</style>
