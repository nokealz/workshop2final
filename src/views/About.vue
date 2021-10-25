<template>
  <div class="hello">
    {{this.calculator}}
  </div>
</template>

<script>

export default {
  mounted () {
    const queryString = window.location.search
    const urlParams = new URLSearchParams(queryString)
    const firstname = urlParams.get('first_name')
    console.log('first_name', firstname)
    for (const user of this.items) {
      if (user.first_name === firstname) {
        this.calculator.push(user)
      }
    }
  },
  data () {
    return {
      calculator: [],
      items: [
        { age: 40, first_name: 'Dickerson', last_name: 'Macdonald', salary: 123 },
        { age: 21, first_name: 'Larsen', last_name: 'Shaw', salary: 123 },
        { age: 89, first_name: 'Geneva', last_name: 'Wilson', salary: 123 },
        { age: 38, first_name: 'Jami', last_name: 'Carney', salary: 123 }
      ]
    }
  },
  methods: {
  }
}
</script>
