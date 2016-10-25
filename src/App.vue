<template>
  <div>
    <menu-view :fileImport="fileImport" :removeImage="removeImage"></menu-view>

    <div class="columns">
      <div class="column is-one-quarter">
          <side-bar></side-bar>
      </div>
      <div class="column">
        <map-view :image="image"></map-view>
      </div>
    </div>
  </div>
</template>

<script>
import menuView from './components/menuView'
import sideBar from './components/sideBar'
import mapView from './components/mapView'
export default {
  name: 'app',
  components: {
    menuView,
    sideBar,
    mapView
  },
  data () {
    return {
      image: ''
    }
  },
  methods: {
    fileImport (e) {
      let files = e.target.files || e.dataTransfer.files
      if (!files.length) return
      this.createImage(files[0])
      console.log(files[0])
    },
    createImage (files) {
      let image = new Image()
      let reader = new FileReader()
      let vm = this
      reader.onload = (e) => { vm.image = e.target.result }
      reader.readAsDataURL (files)
    },
    removeImage () {
      this.image = ''
    }
  }
}
</script>

<style>

</style>
