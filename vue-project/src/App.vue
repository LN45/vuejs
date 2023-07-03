<template>
  <!-- <HelloWorld :user="user" /> -->

  <HelloWorld @update-name="name => display(name)">
    <!-- <template v-slot:nom>
      <p>{{ user.name }}</p>
    </template>
    <template v-slot:ages>
      <p>{{ user.age }}</p>
    </template> -->
  </HelloWorld>


  <!-- <span>{{ sentence }}</span> -->

  <!-- <input type="text" v-model="name" />
  <input type="text" v-model="age" /> -->

  <!-- <div :class="[ user.age > 30 ? 'text-red' : 'text-green' ]">
    {{ user.name }}
  </div> -->

  <!-- <div v-if="user.age > 15">
    Mon âge
  </div>
  <div v-else>
    else
  </div> -->

  <!-- @input ou v-on:input fait la même chose -->
  <!-- sur btn checkbox ou btn radio on utilise le @change popur avoir l'appel à la fonction  au moment de sortir de l'input -->
  <!-- <input type="text" v-model="user.name" @input="display"/>
  <input type="text" v-model="user.age" /> -->
</template>

<script setup>
import HelloWorld from "@/components/HelloWorld.vue";
import { watch, ref } from "vue";
//import { reactive } from "vue";

// const user = reactive({
//   name: "NordCoders",
//   age: "29",
// });

// const sentence = computed(() => {
//   return `Je m'apelle ${name.value} et j'ai ${age.value}`;
// });

const name = ref("NordCoders");
const age = ref("30");

const display = (name) => {
  console.log(name);
}

watch(name, (newValue, oldValue) => {
  console.log('new' + newValue, oldValue);
})

// const display = () => {
//   console.log(user);
// };
// display();
</script>

<style scoped>
.text-red {
  color: indianred;
}

.text-green {
  color: green;
}
</style>
