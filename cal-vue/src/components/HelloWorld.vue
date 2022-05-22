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
          <td></td>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
        </tr>
        <tr>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
        </tr>
        <tr>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
        </tr>
        <tr>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
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
      delete() {
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