<template>
  <div class="hello">
    <b-container class="bv-example-row mb-3">
      <b-row cols="1">
        <b-col>
           <b-card class="text-center">
    <div class="bg-secondary text-light">
    ชื่อจริง : {{calculator[0].first_name}}  {{calculator[0].last_name}}
    </div>
  </b-card>
        </b-col>
        <b-col>
          <p class="text-left my-2">เงินที่ได้ต่อชั่วโมง</p>
          <b-form-input type="number" v-model="calculator[0].salary" oninput="this.value = this.value.replace(/[ก-๏\s]/g, '').replace(/[+,*,/]/g, '').replace(/(\..*?)\..*/g, '$1');"></b-form-input>
        </b-col>
        <b-col>
          <p class="text-left my-2">จำนวนชั่วโมงที่ทำงาน</p>
          <b-form-input type="number" @change="summm" v-model="hour" placeholder="ใส่จำนวนชั่วโมงที่ทำงาน" oninput="this.value = this.value.replace(/[ก-๏\s]/g, '').replace(/[+,*,/]/g, '').replace(/(\..*?)\..*/g, '$1');"></b-form-input>
        </b-col>
        <b-col>
          <p class="text-left my-2">โบนัส</p>
          <b-form-input type="number" v-model="bonus" placeholder="%โบนัสที่ได้" oninput="this.value = this.value.replace(/[ก-๏\s]/g, '').replace(/[+,*,/]/g, '').replace(/(\..*?)\..*/g, '$1');"></b-form-input>
        </b-col>
        <b-col>
          <b-button variant="dark" class="my-4" @click="callcal">calculator</b-button>
          <b-button variant="dark" class="my-4 ml-2" @click="why">clear</b-button>
        </b-col>
        <b-col cols="6" >
          <HelloWorld
            :salary="calculator[0].salary"
            :hour="hour"
            :bonus="bonus"
            :sum="sum"
          />
        </b-col>
        <b-col cols="6" >
          <Chart
            :salary="calculator[0].salary"
            :hour="hour"
            :bonus="bonus"
            :sum="sum"
          />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>

import HelloWorld from '@/components/HelloWorld.vue'
import Chart from '@/components/chart.vue'

export default {
  components: {
    HelloWorld,
    Chart
  },
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
      cal: 'hidden',
      pa: '',
      hour: 0,
      bonus: 0,
      sum: 0,
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
    // callcal () {
    //   this.cal = ''
    //   this.pa = ''
    // },
    // why () {
    //   this.hee = 0
    //   this.text = 0
    //   this.num = 0
    //   this.cal = 'hidden'
    //   this.pa = 'hidden'
    // }
  }
}
</script>
