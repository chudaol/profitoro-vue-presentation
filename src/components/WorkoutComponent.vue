<template>
  <div class="modal fade" id="workoutModal" tabindex="-1" role="dialog" aria-hidden="true">
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title">{{ name }}</h5>
        </div>
        <div class="modal-body">
          <div class="text-center">
            <img :src="pictures && pictures.length && pictures[0]" class="img-fluid rounded" :alt="name">
          </div>
          <p>{{ description }}</p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    data () {
      return {
        name: 'Pushups',
        description: 'Do at least 10 pushups',
        pictures: [require('../assets/images/pushups.png')]
      }
    }
  }
</script>
<style scoped lang="scss">
  h5 {
    margin-top: 10px;
    margin-left: auto;
    margin-right: auto;
    color: gray;
  }
  p {
    margin-left: auto;
    margin-right: auto;
    text-align: center;
    font-size: 0.8em;
    color: darkgray;
  }
</style>