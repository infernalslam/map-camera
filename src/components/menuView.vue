<template>
  <div>
    <nav class="nav">
        <div class="nav-left nav-menu">
          <a class="nav-item" href="#">
            File
          </a>
          <a class="nav-item" @click="removeImage">
            Delete
          </a>
          <a class="nav-item" href="#">
            Save
          </a>

          <span class="nav-item">
            <a class="button is-primary" href="#">
              <span class="icon">
                <i class="fa fa-download"></i>
              </span>
              <span>
                <input type="file"  @change="fileImport">
              </span>
            </a>
          </span>
        </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'menu',
  data () {
    return {
    }
  },
  props: ['fileImport', 'removeImage']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
