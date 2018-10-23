<template>
       
          
    <div class="calculator">
         
            <div class="display">
                    <h4>Display One</h4>
                    <hr style="background-color: rebeccapurple">
                    <h3>Display two</h3>
                </div>
          <div class="calc-column1">
              <div class="btn">1</div>
              <div class="btn">2</div>
              <div class="btn">3</div>
              <div class="btn">4</div>
              <div class="btn">5</div>
          </div>
          <div class="calc-row2">
                <div class="btn">6</div>
                <div class="btn">7</div>
                <div class="btn">8</div>
                <div class="btn">9</div>   
                <div class="btn">10</div>
                
            </div>
            <div class="calc-row3">
                    <div class="btn">11</div>
                    <div class="btn">12</div>
                    <div class="btn">13</div>
                    <div class="btn">14</div>
                    <div class="btn">15</div>
                </div>
            <div class="calc-row4">
                    <div class="btn">16</div>
                    <div class="btn">17</div>
                    <div class="btn">18</div>
                    <div class="btn-corner">19</div>
                    <div class="btn">20</div>
                </div>
       
        
        </div>
</template>
<script>
        export default {
          name: 'hello',
          data () {
            return {
              msg: 'Welcome to Your Vue.js PWA'
            }
          }
        }
        </script>
<style>
.calculator{
  margin: 0 auto;
  width: 400px,auto;
  font-size: 30px;
  background-color: rgb(14, 190, 190);
  display: grid;
  grid-template-columns: repeat(4, 3fr);
  grid-auto-rows: minmax(5, auto);
}
.display{
  grid-column: 1 / 5;
  background-color: rgb(0, 105, 124);
  color: white;
}
.btn{
    border-radius: 2px;
    border-width: 2em;
    border-color: blue;
    background-color: rgb(255,255,255);
}


</style>