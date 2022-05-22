<template>
  <div>

    <table id="cal" dir="ltr">
        <tr>
          <td colspan="5" >
            <input 
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
      
  }
</script>