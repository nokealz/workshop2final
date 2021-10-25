<template>
  <div>
    <b-card
      title="ยอดรวม"
      style="max-width: 100%;"
      class="mb-2"
    >
      <b-card-text class="text-right">
        {{(parseInt(salary) * parseInt(hour)) + (parseInt(salary) * parseInt(hour)) * (parseInt(bonus)/100)}} บาท
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
