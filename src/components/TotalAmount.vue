<template>
    <div>
        <div class="div-8">
              <div class="div-9">총 수입:{{ " " + totalAmount.totalIncome.toLocaleString('ko-KR')}}원</div>|
              <div class="div-10">총 지출:{{" " + totalAmount.totalExpense.toLocaleString('ko-KR')}}원</div>
        </div>
    </div>
</template>


<script setup>
import axios from 'axios';
import { reactive, onMounted } from 'vue';

const totalAmount = reactive({totalIncome : "", totalExpense : ""});

const userId = sessionStorage.getItem("id");

const getList = () => {
    axios.get(`http://localhost:3001/account?user_id=${userId}`)
    .then(res => {
        totalAmount.totalIncome = res.data[0].total_income;
        totalAmount.totalExpense = res.data[0].total_expand;
        console.log(totalAmount);
    })
    .catch(e => {
        console.log(e);
        return;
    })
}

onMounted(() => {
    getList();
})


</script>


<style scoped>
    .div-8 {
    display: flex;
    gap: 9px;
    font-size: large;
  }
  @media (max-width: 991px) {
    .div-8 {
      white-space: initial;
    }
  }
  .div-9 {
    color: #6293ce;
    font-family: Inter, sans-serif;
    flex-grow: 1;
  }
  .div-10 {
    color: #f66464;
    font-family: Inter, sans-serif;
  }
</style>