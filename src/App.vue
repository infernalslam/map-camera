<template>
  <div>
    <menu-view :fileImport="fileImport" :removeImage="removeImage"></menu-view>

    <div class="columns">
      <div class="column is-one-quarter">
          <side-bar :addCam18="addCam18"></side-bar>
      </div>
      <div class="column">
        <map-view :image="image" :totalCamera="totalCamera"></map-view>
      </div>
    </div>
  </div>
</template>

<script>
import firebase from 'firebase'
var config = {
   apiKey: 'AIzaSyA5dq5JSmYWpqk5y-ED5jNWOSL2kZDruMM',
   authDomain: 'project-mint.firebaseapp.com',
   databaseURL: 'https://project-mint.firebaseio.com',
   storageBucket: 'project-mint.appspot.com',
   messagingSenderId: '14908805986'
 }
 firebase.initializeApp(config)
 // var Camera = firebase.database().ref('camera')

import menuView from './components/menuView'
import sideBar from './components/sideBar'
import mapView from './components/mapView'
export default {
  name: 'app',
  mounted () {
  },
  components: {
    menuView,
    sideBar,
    mapView
  },
  data () {
    return {
      image: '',
      totalCamera: []
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
    },
    addCam18 () {
      let r = Math.floor(Math.random() * 255)
      let g = Math.floor(Math.random() * 255)
      let b = Math.floor(Math.random() * 255)
      let x = Math.floor(Math.random() * 1000)
      let y = Math.floor(Math.random() * 800)
      let lens18 = {
        id: Date.now(),
        color: `rgb(${r}, ${g}, ${b})`,
        x: x,
        y: y
      }
      this.totalCamera.push(lens18)
      console.log(this.totalCamera)
    }
  }
}
</script>

<style>

</style>
