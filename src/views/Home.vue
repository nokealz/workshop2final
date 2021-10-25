<template>
  <div class="hello">
    <b-table striped hover :items="items" :fields="fields">
      <template #cell(actions)="row">
        <b-button @click="info(row.item)">
          calculator
        </b-button>
      </template>
    </b-table>
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data () {
    return {
      // Note `isActive` is left out and will not appear in the rendered table
      fields: [
        {
          key: 'first_name'
        },
        {
          key: 'last_name'
        },
        {
          key: 'salary'
        },
        {
          key: 'actions'
        }
      ],
      items: [
        { age: 40, first_name: 'Dickerson', last_name: 'Macdonald', salary: 123 },
        { age: 21, first_name: 'Larsen', last_name: 'Shaw', salary: 123 },
        { age: 89, first_name: 'Geneva', last_name: 'Wilson', salary: 123 },
        { age: 38, first_name: 'Jami', last_name: 'Carney', salary: 123 }
      ]
    }
  },
  methods: {
    info (v) {
      window.location.href = `http://192.168.100.3:8080/about?first_name=${v.first_name}`
      console.log(v)
    }
  }
}
</script>
