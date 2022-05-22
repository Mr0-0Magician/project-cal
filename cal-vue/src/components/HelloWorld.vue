<template>
  <div>

    <table id="cal" dir="ltr">
        <tr>
          <td colspan="5" >
            <input 
              v-model="screen"
              style="padding:5px ; text-align: right; "
              type="int , float"
              id="output"
              dir="ltr"
            >
          </td>
        </tr>
        <tr>
          <td><button @click="digit(7)" class="digit">7</button></td>
          <td><button @click="digit(8)" class="digit">8</button></td>
          <td><button @click="digit(9)" class="digit">9</button></td>
          <td><button @click="division" class="oprator">÷</button></td>
          <td><button @click="removing" class="eq2">←</button></td>
        </tr>
        <tr>
          <td><button @click="digit(4)" class="digit">4</button></td>
          <td><button @click="digit(5)" class="digit">5</button></td>
          <td><button @click="digit(6)" class="digit">6</button></td>
          <td><button @click="remaining" class="oprator">%</button></td>
          <td><button @click="delete1" class="eq2">C</button></td> 
        </tr>
        <tr>
          <td><button @click="digit(1)" class="digit">1</button></td>
          <td><button @click="digit(2)" class="digit">1</button></td>
          <td><button @click="digit(3)" class="digit">1</button></td>
          <td><button @click="Multiplication" class="oprator">x</button></td>
          <td><button @click="sum" class="eq2">+</button></td>
        </tr>
        <tr>
          <td colspan="2"><button @click="digit(0)" class="digit">1</button></td>
          <td><button @click="Submission" class="oprator">-</button></td>
          <td><button @click="decimal" class="oprator">.</button></td>
          <td><button @click="equal" class="eq">=</button></td>
        </tr>
    </table>
  </div>
</template>

<script>
import { propsToAttrMap } from '@vue/shared';

  export default {
    name:"helloworld",
    props:{
      msg: String,
    },
    //creating values
    data() {
      return {
        screen:"",
        screen2:"",
        box1 :Number & Float32Array,
        box2 :Number & Float32Array,
        operators : "",
      };
    },
    methods: {
      //sum = +
      sum() {
        this.box1 = parseInt(this.screen, 10);
        this.operators = "+";
        this.screen = "";
      },
      //empty = ""
      empty() {
          this.box1 = parseInt(this.screen , 10);
          this.operators = "";
          this.screen = "";
      },
      division() {
        this.box1 = parseInt(this.screen , 10);
        this.operators = "/";
        this.screen = "";
      },
      Submission() {
        this.box1 = parseInt(this.screen, 10);
        this.operators = "-";
        this.screen = "";      
      },
      remaining() {
        this.box1 = parseInt(this.screen, 10 );
        this.operators = "%"
      },
      removing() {
        this.screen = this.screen.slice(1);
      },
      delete1() {
        this.screen = "";
      },
      Multiplication() {
        this.box1= parseInt(this.screen, 10);
        this.operators = "*";
        this.screen = "";
      },
      digit(n) {
        this.screen += (n)
      },
      
      decimal() {
        this.screen = this.screen + (".") + this.screen2;
      },
      equal() {
        //making a breakable loop
        switch (this.operators) {
          case "+":
            this.box2 = (this.screen, 10);
            this.screen = this.box1 + this.box2
            break;
          case ("/"):
            this.box2= (this.screen, 10);
            this.screen = (this.box1 / this.box2);
            break;
          case ("-"):
            this.box2 = (this.screen, 10);
            this.screen = (this.box1 - this.box2);
            break;
          case ("%"):
            this.box2 = (this.screen, 10);
            this.screen = (this.box1 % this.box2);
            break;
          case ("*"):
            this.box2 = (this.screen, 10),
            this.screen = (this.box1 * this.box2);
            break;
          case ("|"):
            this.screen = this.screen.slice(1);
            break;
          case ("C"):
            this.screen = "";
            break;
          //not sure about this 
          case ("."):
            this.screen = this.screen + (".") + this.screen2;
            break
          default:
            break;
        }
      }
    }
  }
</script>

<style scoped>

.digit {
  background-color:gray;
  border: 5px solid black;
  border-radius: 60px;
  border-bottom: 5px solid;
  font-size: 20px;  

}

button {
  width: 95%;
}
.oprator {
  font-size: 20px;  
  border-bottom: 5px solid;
  border-radius: 60px;
}
.eq {
  font-size: 20px;
  border-bottom: 5px solid;
  background-color:gray;
  border-bottom: 5px solid;
  border-top: px solid;

  
}
.eq2 {
  font-size: 20px;
  border-bottom: 5px solid;
  background-color:gray;
  border-bottom: 5px solid;
  border-top: 5px solid;
}
input {
box-sizing: 50px;
background-color:rgb(44, 70, 56)
}
#cal{
  border:  20px solid;
  border-bottom:rgb(22, 21, 21) 40px solid;
  border-top: rgb(22, 21, 21) 35px solid ;
  background-color:rgb(22, 21, 21);
  border-radius: px ;
}
</style>