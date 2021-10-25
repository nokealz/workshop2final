<template>
  <div>
    <b-card
      title="method"
      style="max-width: 100%;"
      class="mb-2"
    >
      <b-card-text>
        {{salary}} + {{hour}} = {{salary + hour}} <br>
        {{salary + hour}} - {{bonus}} = {{salary + hour - bonus}}
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
  }

}
</script>

<style>
</style>
