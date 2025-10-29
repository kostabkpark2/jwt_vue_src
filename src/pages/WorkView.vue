<template>
  
    <h2>xxx의 Vue 실습 페이지</h2>

    <div class="work">
    <team-card @delete-card="deleteCard" v-for="(member, index) in members" :name="member.name" :food="member.food" :src-url="member.srcUrl" :team-num="teamNum" :team-name="teamName" :is-show="member.isShow" :idx="index"></team-card>
    </div>
</template>

<script setup>
  import { reactive } from 'vue';
  import TeamCard from '@/components/TeamCard.vue'
  const members = reactive(
  [
  {name: "둘리", food: "딸기, 사과", srcUrl: "/images/dooly.jpg", isShow: true},
  {name: "또치", food: "오뎅우동, 김밥", srcUrl: "images/ddochi.jpg", isShow: true},
  {name: "도우너", food: "피자, 치킨", srcUrl: "images/dauner.png", isShow: true},
  {name: "올라프", food: "라멘, 마라탕", srcUrl: "images/olaf.jpg", isShow: true},
  ]);
  const teamNum = 7;
  const teamName = '유니코';

  function deleteCard(idx){
    console.log(idx)
    members[idx].isShow = false;
    console.log(members[idx]);
  }
  
</script>
<style>
  .work{
    display: flex;
    flex-direction: row;
  }
</style>