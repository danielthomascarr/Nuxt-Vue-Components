<template>
  <div class="container">
    <div class="title">Filter users</div>
    <div class="buttons">
  <button v-on:click="userFilterKey = 'all'" class="button" :class="{ 'is-active': userFilterKey == 'all' }">Team</button>
  <button v-on:click="userFilterKey = 'mine'" class="button" :class="{ 'is-active': userFilterKey == 'mine'}">Mine</button>

    </div>

    <table class="table is-bordered">
      <thead>
        <tr>
          <th>Title</th>
          <th>Owner</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in userFilter" :key="user.Owner">
          <td>
           {{user.Title}}
          </td>
           <td>
           {{user.Owner}}
          </td>
        </tr>
      </tbody>
    </table>

  </div>
</template>

<script>
export default {
  data () {
    return {
    userFilterKey: 'all',
    user: 'daniel',

     ideas: [
       {
         Title: 'One',
         Owner: 'daniel',
       },
       {
         Title: 'Two',
         Owner: 'daniel',
       },
       {
         Title: 'Three',
         Owner: 'user 1',
       },
       {
         Title: 'Four',
         Owner: 'user 2',
       } 
     ]
    }
  },
    computed: {
  	userFilter() {
    	return this[this.userFilterKey]
    },
    all() {
      return this.ideas
    },
    mine() {
      return this.ideas.filter((user) => user.Owner == this.user)
    }
  }


}
</script>

<style>

</style>

