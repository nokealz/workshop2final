<template>
  <div>
    <b-card
      title="ขั้นตอนการคิด"
      style="max-width: 100%;"
      class="mb-2"
    >
      <b-card-text>
        เงินไม่รวมโบนัส {{salary}} x {{hour}} = {{ parseInt(salary) * parseInt(hour)}} บาท <br>
        เงินรวมโบนัส {{ parseInt(salary) * parseInt(hour)}} + {{bonus}}% = {{(parseInt(salary) * parseInt(hour)) + (parseInt(salary) * parseInt(hour)) * (parseInt(bonus)/100)}} บาท
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
