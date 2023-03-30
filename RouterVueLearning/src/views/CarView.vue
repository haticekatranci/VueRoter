<script setup>
import {useRoute, RouterView, useRouter} from "vue-router"
import cars from "../data/cars.json"
import ContactView from "@/views/ContactView.vue";


const route = useRoute()
const router = useRouter()
const carId = parseInt(route.params.id)

console.log(carId)

const car = cars.find(c => c.id === carId)
const showContact = () => {
    if(carId === 4) return;
    return router.push(`/cars/${carId}/contact`)
}
console.log(car.contact.dealer)

console.log(car.contact.number)

</script>

<template>
  <div>
    <h1>car view</h1>
    <p>{{car.name}}</p>
    <p>{{car.year}}</p>
    <p>{{car.price}}</p>
    <button @click="showContact">Click for contact</button>

    <RouterView/>
  </div>
</template>