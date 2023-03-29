<script setup>
import cars from "../data/cars.json"
import {RouterLink} from "vue-router";
</script>

<template>
    <div>
        <div class="cars">
            <RouterLink to="/cars/${car.id}" v-for="car in cars" :key="car.id" >
                <p>{{ car.name }}</p>
                <p>{{ car.price }}</p>
                <p>{{ car.year }}</p>
            </RouterLink>



        </div>
        <h1>About View</h1>
        <p>{{ cars }}</p>
        <p></p>

    </div>
</template>
<script setup>
</script>