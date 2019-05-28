<template>
  <div class="container">
    <div class="title">Modal</div>
    <button v-on:click="launch" class="button is-small is-primary">Launch modal</button>
   
<div class="modal" v-bind:class="{'is-active':isActive}">
  <div class="modal-background" @click="close"></div>
    <div class="modal-card">
      <section class="modal-card-body">
        <i class="fas fa-times is-pulled-right modalX" aria-label="close" @click="close"></i>
        <div class="title is-4">Optional Modal title</div>
          Some modal content
      </section>
      <footer class="modal-card-foot">
        <div class="field is-grouped">
          <p class="control">
            <i class="far fa-check-circle"></i>
            <i class="far fa-times-circle" @click="close"></i>
          </p>
        </div>
      </footer>
    </div>
</div>

  </div>
</template>

<script>
export default {
   data () {
      return {
        isActive: false
      }
    },
  methods: {
    launch: function() {
      this.isActive = true;
    },
    close: function() {
      this.isActive = false;
    }
  }
}
</script>

<style>
.modal-background {
  background: rgb(255, 255, 255) transparent;
  background: rgba(255, 255, 255, 0.2);
}
.modal-card{
  border: 1px solid #cccccc;
  border-radius: 3px;
  width:auto;
}
.modal-card-body {
  padding: 10px 15px;
}

.modalX{
  margin-left: 15px;
  margin-bottom: 5px
}

.modal-card-foot{
  background-color: #ffffff;
  padding: 10px 15px;
  border-radius: 0;
  border-top: 0;
}

.fa-check-circle, .fa-times-circle{
  font-size: 1.5em;
  cursor:pointer;
}

</style>




