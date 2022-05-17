<template>
  <div class="hello">
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
      <b-form-group id="input-group-2" label="Search:" label-for="input-2">
        <b-form-input id="input-2" v-model="form.searchtext" placeholder="Enter search keyword" required></b-form-input>
      </b-form-group>
      <b-button type="submit" variant="primary">OK</b-button>
      <b-button type="reset" variant="danger">Reset</b-button>
    </b-form>
    <router-link to="/history">History</router-link>
    <div class="alert alert-success" role="alert">
      This is a primary alert—check it out!
    </div>
  </div>
</template>
<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      form: {
        searchtext: ''
      },
      show: true
    }
  },
  methods: {
    onSubmit(event) {
      // AJAX POST to api
      // Display response data on div
      event.preventDefault()
      alert(JSON.stringify(this.form))
    },
    onReset(event) {
      event.preventDefault()
      // Reset our form values
      this.form.searchtext = ''
      this.show = false
      this.$nextTick(() => {
        this.show = true
      })
    }
  }
}

</script>
</style>
