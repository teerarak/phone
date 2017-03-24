<template>
  <div class="">
    <h1>{{ output }}</h1>
    <h1>tmp: {{ tmp }}</h1>
    <input :value="output" @keyup="changeInput($event)">
  </div>

</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      output: '',
      tmp: ''
    }
  },
  methods: {
    changeInput (event) {
      var value = event.target.value
      var tmp = value.split('-').join('')
      this.tmp = tmp
      var tmp2 = tmp.split('')
      if (tmp.length > 3) {
        tmp2.splice(3, 0, '-')
      }
      if (tmp.length > 6) {
        tmp2.splice(7, 0, '-')
      }
      this.output = tmp2.join('')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
