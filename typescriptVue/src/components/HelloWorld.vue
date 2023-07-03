<template>
  <!-- <h1 v-text="title"></h1>
  <h2 v-text="subTitle"></h2>
  <button v-on:click="editTitle('Hello World Edited')">Editer title</button>
  <button v-on:click="editSubTitle('80')">Editer subtitle</button> -->
  <div v-for="item in props.items">
    <span v-text="item.name"></span>
    <span v-text="item.age"></span>
  </div>
  <button v-on:click="display('name')">Display name</button>
  <button v-on:click="display('age')">Display age</button>
</template>

<script setup lang="ts">
import type { User } from "@/types/User";
import type { UserType } from "@/types/UserType";

// const state = reactive({
//   title: 'Hello World' as string,
//   subTitle: 90 as string | number
// });

const props = defineProps<{
  items: User[];
}>();

const display = (property: UserType) => {
  props.items.forEach((item: User)=> {
    console.log(item[property]);
  })
}


// let title = ref<string>("Hello World");
// let subTitle = ref<string | number>(90);

// const editTitle = (editTitle: string) => {
//   title.value = editTitle;
// };

// const editSubTitle = (editSubTitle: string | number) => {
//   subTitle.value = editSubTitle;
// };
</script>

