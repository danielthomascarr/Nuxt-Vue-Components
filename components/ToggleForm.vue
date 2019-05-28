<template>
<div class="container">
 <div class="title">Toggle Form</div>
    <template v-if="show">
  
         <div class="field has-addons">
          <p class="control">
            <input class="input" type="text" placeholder="Input title">
          </p>
          <p class="control">
            <a class="button" @click="showForm">
              Close
            </a>
          </p>
        </div>
     
    </template>

    <template v-else>
      <template v-if="isLoading">
        <div class="control is-loading">
          <input class="input" type="text" placeholder="Loading tree..." readonly>
        </div>
      </template>

      <template v-else>
      <div class="field has-addons">
        <p class="control" @click="loading">
          <a href="#">
            <input class="input" type="text" value="This text is readonly" readonly>
          </a>
        </p>
        <p class="control">
          <a class="button" @click="showForm">
            Edit
          </a>
        </p>
      </div>    
    </template>
  </template>
</div>

</template>

<script>
export default {
  data(){
    return {
      show:false,
      isLoading: false
    }
  },
  methods: {
    showForm(){
      this.show = !this.show
    },
    loading(){
      this.isLoading = true
    }
  }
  
}
</script>

<style>

</style>


