<template>
  <div>
    <b-card
      title="method"
      style="max-width: 100%;"
      class="mb-2"
    >
      <b-card-text>
        {{salary}} + {{hour}} = {{sum}} <br>
        {{salary + hour}} - {{bonus}} = {{salary + hour - bonus}}
      </b-card-text>
    </b-card>
  </div>
</template>

<script>
export default {
  mounted () {
    // eslint-disable-next-line no-undef
    this.sum = sum(this.salary, this.hour)
  },
  name: 'HelloWorld',
  props: {
    salary: Number,
    hour: Number,
    bonus: Number
  },
  methods: {
    sum (salary, hour) {
      // eslint-disable-next-line no-undef
      sum = salary + hour
      // eslint-disable-next-line no-undef
      return sum
    }
  },
  data () {
    return {
      // eslint-disable-next-line vue/no-dupe-keys
      sum: 0
    }
  }
}
</script>

<style>
</style>
