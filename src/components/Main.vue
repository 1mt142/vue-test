<script setup>
import { ref } from 'vue'

defineProps({
  name: String
})

const count = ref(0)

</script>

<template>
  <h1>{{ name }}</h1>
  <div>
    <h3>From Data</h3>
 <ul v-for="item in instructors" :key="item.name">
  <li>
   {{item.name}}
  </li> 
   <li >
     {{ item.contact }}
  </li>
</ul>
     </div>
  <div>
    <input name="name" ref="name_field" type="text" placeholder="Name" v-model="purchase.name" />
    <input name="contact" type="number"  placeholder="contact" v-model="purchase.contact"/>
    <button @click="queuePurchase" type="submit">Enter Data</button>
  </div>

</template>

<script>
export default {

  data() {
    return {
      instructors:[],
      purchase: {
        name: '',
        contact: '',
      }
    }
  },
    methods: {
    queuePurchase() {
      this.instructors.push({...this.purchase} );
      this.purchase.name=''
      this.purchase.contact=''
    }
  },
  mounted() {
    console.log(`the component is now mounted.`)
     this.$refs.name_field.focus()

  }
}
</script>

<style scoped>
h1 {
  color: #42b983;
  background-color: aqua;
}
</style>
