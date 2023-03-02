<template>
  <div class="clock">
    <div class="hour-hand" :style="hourStyle"></div>
    <div class="minute-hand"></div>
    <div class="second-hand" :style="secondStyle"></div>
    <div class="face"></div>
  </div>
</template>

<script>
import { ref } from 'vue'

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
        return this.time.getHours() * 30 /2
      },
      secondDegree: function() {
        return this.time.getSeconds() * 6;
      },
    
      hourStyle() {
        return {
          transform: `rotate(${this.hourDeg}deg)`
        }
      },

      secondStyle() {
        console.log(this.secondDegree)
        return {
          transform: `rotate(${this.secondDegree}deg)`
        }
      }
      // hourStyle() {
      //   console.log(this.hourDeg)
      //   switch(this.hourDeg) {
      //     case 12: 
      //       return {
      //         transform: 'rotate(-90deg)'
      //       }
      //     case 1: 
      //       return {
      //         transform: 'rotate(-60deg)',
      //       }
      //     case 2: 
      //       return {
      //         transform: 'rotate(-30deg)',
      //       }
      //     case 3: 
      //       return {
      //         transform: 'rotate(0deg)',
      //       }
      //     case 4: 
      //       return {
      //         transform: 'rotate(30deg)',
      //       }
      //     case 5: 
      //       return {
      //        transform: 'rotate(60deg)',
      //       }
      //     case 6: 
      //       return {
      //         transform: 'rotate(90deg)',
      //       }
      //     case 7: 
      //       return {
      //         transform: 'rotate(120deg)',
      //       }
      //     case 8: 
      //       return {
      //         transform: 'rotate(150deg)',
      //       }
      //     case 9: 
      //       return {
      //         transform: 'rotate(180deg)',
      //       }
      //     case 10: 
      //       return {
      //         transform: 'rotate(210deg)',
      //       }
      //     case 11: 
      //       return {
      //         transform: 'rotate(240deg)',
      //       }
      //   }
      // }
    }
    

    
  }
  
</script>

