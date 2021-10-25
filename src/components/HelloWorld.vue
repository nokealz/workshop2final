<template>
  <div>
    <b-card
      title="method"
      style="max-width: 100%;"
      class="mb-2"
    >
      <b-card-text>
        {{salary}} + {{hour}} = {{ parseInt(salary) + parseInt(hour)}} <br>
        {{salary + hour}} - {{bonus}} = {{ parseInt(salary) + parseInt(hour) - parseInt(bonus)}}
      </b-card-text>
    </b-card>
  </div>
</template>

<script>
export default {
  mounted () {
  },
  name: 'HelloWorld',
  props: {
    salary: Number,
    hour: Number,
    bonus: Number
  },
  methods: {
  },
  data () {
    return {
    }
  }
}
</script>

<style>
</style>
