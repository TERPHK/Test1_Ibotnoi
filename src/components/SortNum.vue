<template>
  <div>
    <label for="number">Input </label>
    <input type="number" v-model.number="number" id="number" />
    <button @click="countDown">Submit</button>
    <ul>
      <li v-for="(n, index) in countList" :key="'countList-' + index">{{ '*'.repeat(n) }}</li>
      <li v-for="(n, index) in countdownList" :key="'countdownList-' + index">{{ '*'.repeat(n) }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number: null,
      countList: [],
      countdownList: [],
    };
  },
  methods: {
    countDown() {
      this.countdownList = [];
      this.countList = [];
      const num = Number(this.number); // แปลงค่าที่ป้อนเป็นตัวเลข

      if (num > 0) {
        for (let i = num; i > 0; i--) {
          this.countdownList.push(i);
        }
        for (let i = 1; i < num; ++i) {
          this.countList.push(i);
        }
      }
      
      console.log('Number:', num);
      console.log('Count List:', this.countList);
      console.log('Countdown List:', this.countdownList);
    }
  }
};
</script>
