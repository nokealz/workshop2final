<template>
  <div>
    <b-card
      title="Total"
      style="max-width: 100%;"
      class="mb-2"
    >
      <b-card-text class="text-right">
        {{salary + hour - bonus}}
      </b-card-text>
    </b-card>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    salary: Number,
    hour: Number,
    bonus: Number
  },
  data () {
    return {
    }
  }
}
</script>

<style>
</style>
