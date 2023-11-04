<template>
    <div class="calc">
        <input type="number" v-model="input" />

        <div class="number-row">
            <div>
                <div class="number-col" @click="handleNumberClick('7')">7</div>
                <div class="number-col" @click="handleNumberClick('8')">8</div>
                <div class="number-col" @click="handleNumberClick('9')">9</div>
                <div class="operator-col" @click="handleOpratorClick('*')">X</div>
            </div>
            <div>
                <div class="number-col" @click="handleNumberClick('4')">4</div>
                <div class="number-col" @click="handleNumberClick('5')">5</div>
                <div class="number-col" @click="handleNumberClick('6')">6</div>
                <div class="operator-col" @click="handleOpratorClick('-')">-</div>
            </div>
            <div>
                <div class="number-col" @click="handleNumberClick('1')">1</div>
                <div class="number-col" @click="handleNumberClick('2')">2</div>
                <div class="number-col" @click="handleNumberClick('3')">3</div>
                <div class="operator-col" @click="handleOpratorClick('+')">+</div>
            </div>
            <div>
                <div class="number-col" @click="handleNumberClick('0')">0</div>
                <div class="operator-col" @click="clear()">C</div>
                <div class="operator-col" @click="handleOpratorClick('/')">/</div>
                <div class="operator-col" @click="handleCalculate()">=</div>
            </div>
        </div>
    </div>
</template>

<script>
import { ref } from 'vue';

    export default{
        methods:{
            clear(){
                console.log("clear")
                this.input = '';
            },
            handleNumberClick(num){
                this.input += num;
            },
            handleOpratorClick(operator){
                this.a = this.input;
                this.o = operator;
                this.clear();
            },
            handleCalculate(){
                this.b = this.input;
                console.log(this.a);
                console.log(this.b);
                if(this.o === '*'){
                    this.input = this.a * this.b;
                }
                if(this.o === '+'){
                    this.input = parseInt(this.a) + parseInt(this.b);
                }
                if(this.o === '-'){
                    this.input = this.a - this.b;
                }
                if(this.o === '/'){
                    this.input = this.a / this.b;
                }
            }
        },
        setup(){
            const input = ref('');
            const a = ref(0);
            const o = ref('');
            const b = ref(0);
            return{
                input,
                a,
                o,
                b
            };
        }
    };


</script>

<style scoped>
.calc {
    display: flex;
    flex-direction: column;
    align-items: center;
}
input{
    width: 200px;
    height: 30px;
    text-align: end;
}
.number-row{
    display: flex;
    flex-direction: column;
    margin-top: 20px;
}
.operator-col{
    display: inline-flex;
    border: 1px black solid;
    height: 50px;
    width: 50px;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    background-color: orange;
}
.number-col {
    display: inline-flex;
    border: 1px black solid;
    height: 50px;
    width: 50px;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    background-color: bisque;
}
</style>