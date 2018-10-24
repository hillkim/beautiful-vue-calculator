<template>
       
          
    <div class="calculator">
         
            <div class="display">
                    <div class="display1">{{formula || 0}}</div>
                    <!-- <hr style="background-color: rebeccapurple"> -->
                    <div class="display2">{{answer || 0}}</div>
                </div>
          <div class="calc-column1">
              <div @click='clear' class="btn-top">AC</div>
              <div  @click="append('1')" class="btn">1</div>
              <div  @click="append('2')" class="btn">2</div>
              <div  @click="append('3')" class="btn">3</div>
              <div  @click="append('0')"class="btn-btm">0</div>
          </div>
          <div class="calc-row2">
                <div @click="sign"class="btn-top">+/-</div>
                <div  @click="append('4')" class="btn">4</div>
                <div  @click="append('5')" class="btn">5</div>
                <div  @click="append('6')" class="btn">6</div>   
                <div  @click="append('00')" class="btn-btm">00</div>
                
            </div>
            <div class="calc-row3">
                    <div @click="percent" class="btn-top">%</div>
                    <div  @click="append('7')" class="btn">7</div>
                    <div  @click="append('8')" class="btn">8</div>
                    <div  @click="append('9')" class="btn">9</div>
                    <div  @click="append('.')" class="btn-btm">.</div>
                </div>
            <div class="calc-row4">
                    <div @click="append('/')" class="btn-ops">&#247;</div>
                    <div @click="append('*')" class="btn-ops">X</div>
                    <div @click="append('-')" class="btn-ops">-</div>
                    <div @click="append('+')" class="btn-ops">+</div>
                    <div @click="equals" class="btn-ops">=</div>
                </div>
       
        
        </div>
</template>
<script>
        export default {
          name: 'hello',
          data () {
            return {
              formula: '',
              previous: null,
              answer:null,
            }
          },
          methods: {
            append (number) {
                   this.formula += number
            },
            clear () {
              this.formula = ''
              this.answer=null
            },
            sign () {
                this.formula = this.formula.charAt(0) === '-' ? 
                this.formula.slice(1) : `-${this.formula}`;
            },
            equals () {
              this.answer = (0, eval)(this.formula)
            },
            percent() {
              this.answer = `${parseFloat(eval(this.formula)) / 100}`;
            }
          },
          computed: {
          }

        }
        </script>
<style>
.calculator{
  margin: 0 auto;
  margin-bottom: 0;
  max-width: 400px;
  height: 300px;
  font-size: 30px;
  background-color: rgb(60, 146, 146);
  border-radius: 0.1em;
  display: grid;
  grid-template-columns: repeat(4, 3fr);
  
}
.display{
  grid-column: 1/5;
  background-image: linear-gradient(to right, rgb(255, 0, 212),orange,rgb(0, 225, 255),green,blue,indigo,violet); 
  background-color: rgb(0, 105, 124);
  border-radius: 0.2em;
  text-align: right;
  color: white;
  border-style: groove;
  max-height: 30%;
  padding: 20px; 
  text-overflow: ellipsis;
  white-space:nowrap;
  overflow:visible;
  overflow-wrap:break-word;
  
}
.display2{
font-size:x-large;
justify-content: baseline;
}
.display1{
font-size: large;
text-anchor:start;
}
.btn,.btn-ops,.btn-top,.btn-btm{
    border-radius: 30%;
    border-width: 0em;
    margin: 0.2em;
    text-align: center;
    background-color: white;
    background-image: linear-gradient(rgb(0, 255, 234), rgb(196, 107, 207), rgb(163, 75, 141) );
}
.btn:hover,.btn-ops:hover,.btn-top:hover,.btn-btm:hover {background-color: #3e8e41}
.btn:active,.btn-ops:active,.btn-top:active,.btn-btm:active {
  background-color: #3e8e41;
  box-shadow: 0 5px #666;
  transform: translateY(-2px) translateX(2px);

}
.btn-ops{
    background-image:linear-gradient(to left, rgba(255,0,0,0), rgb(148,0,211));

}
.btn-top{
    background-image: linear-gradient(to top,rgba(255,0,0,0),rgb(65,105,225));
}
.btn-btm{
    background-image: linear-gradient(to bottom,rgba(255,0,0,0),rgb(65, 225, 185));
   
}


</style>