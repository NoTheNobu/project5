<script setup>
    import { faker } from '@faker-js/faker'
    const firstname = faker.food.adjective()
    const lastname = faker.food.dish()
    const jobtitle = faker.food.ingredient()
    const bio = faker.food.description(2)
    const username = faker.internet.userName({firstName: firstname, lastName: lastname}).toLowerCase()
</script>

<template>
    <RouterLink :to="{name: 'CardDetail', params: {id: username}}">
        <div class="border border-purple-900 rounded-lg shadow bg-gray-300 h-full">
            <img class="object-fill h-480 w-960 rounded-t-lg" v-bind:src="faker.image.urlLoremFlickr({category: 'Food', height: 480, width: 960})" />
            <div class="p-4">
                <p class="mb-2 text-2x1 font-bold">{{ firstname }} {{ lastname }}</p>
                <p class="mb-3 font-normal text-red-600">{{ jobtitle }}</p>
                <p class="mb-3 font-normal text-blue-600">{{ bio }}</p>
            </div>
        </div>
    </RouterLink>
</template>