<template>
  <div class="clock">
    <div class="hour-hand" :style="hourStyle"></div>
    <div class="minute-hand" :style="minuteStyle"></div>
    <div class="second-hand" :style="secondStyle"></div>
    <div class="face"></div>
    <span id="twelve">12</span>
    <span id="one">1</span>
    <span id="two"> 2</span>
    <span id="three">3</span>
    <span id="four">4</span>
    <span id="five">5</span>
    <span id="six">6</span>
    <span id="seven">7</span>
    <span id="eight">8</span>
    <span id="nine">9</span>
    <span id="ten">10</span>
    <span id="eleven">11</span>
  </div>
</template>

<script>

  export default {
    data () {
      return {
        time: new Date()
      }
      
    },
    mounted: function() {
      setInterval(() => {
        this.time = new Date()
      }, 1000)
    },
    computed: {
      hourDeg: function() {
        return this.time.getHours() * 30 + (this.time.getMinutes() / 2)
      },
      secondDeg: function() {
        return this.time.getSeconds() * 6;
      },
      minuteDeg: function() {
        return this.time.getMinutes() * 6
      },
    
      hourStyle() {
        console.log('This is hour: ', this.hourDeg)
        return {
          transform: `rotate(${this.hourDeg}deg)`
        }
      },

      secondStyle() {
        console.log('This is seconds: ', this.secondDeg)
        return {
          transform: `rotate(${this.secondDeg}deg)`
        }
      },

      minuteStyle() {
        return {
          transform: `rotate(${this.minuteDeg}deg)`
        }
      }
    }
  }
  
</script>

