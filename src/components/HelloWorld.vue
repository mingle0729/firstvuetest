<template>
  <div id="gugudan">
    <div></div>
    <h1>{{ msg }}</h1>
    <p>
      vue를 이용한 구구단 출력 프로그램 작성<br>
    </p>
    <p class="addPaddind">
      <input type="text" v-model="dan" placeholder="단을 입력해주세요">
      <button id="btnPrint" v-on:click="fnPrint"> 구구단 출력하기</button>
    </p>
    <br>
    <br>
    <br>
    <br>
    <table class="tbPrint" v-show="danYn">
      <thead>
        <th colspan="2">
          <h1> {{ dan }}단 </h1>
        </th>
      </thead>
      <tbody v-for="i in 9" v-bind:key="i">
        <td>
          {{dan}} * {{i}}
        </td>
        <td>
          {{dan * i}}
        </td>
      </tbody>
    </table>
  </div>
</template>

<script>

export default {
  data() {
    return {
      danYn: false,
    }
  },
  methods: {
    fnPrint : function() {
      this.danYn = true;
    }
  },
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#gugudan {
  text-align: center; /* 중앙정렬 */
}
table {
  width: 100%;
  border-collapse: collapse; /* 테두리 한줄로 표현 */
}
table, th, td { 
  border: 1px solid #e7e7e7; 
}
th {
  background-color: rgb(255, 187, 0);
  color: #fff;
}
td {
  width: 50%;
  line-height: 35px;
}
input {
  margin-right: 0.5rem;
  border: 1px solid #e7e7e7;    
  margin-right: 0.5rem;
  border-radius: 0.25rem;
  padding: 0 0.5rem;
  height: 2.1rem;
}
button {
  border-radius: 0.25rem;
  line-height: 1.7rem;    
  color: #fff;
  border-color: rgb(255, 187, 0);
  background-color: rgb(255, 187, 0);
  height: 2.1rem;
}
button:hover {
  background-color: rgb(255, 240, 199);
  border-color: rgb(255, 240, 199);
  color: rgb(109, 108, 108);
  cursor: pointer;
  
}
</style>
