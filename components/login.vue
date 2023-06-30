<script>
const email = ref("")
const loggedIn = ref(false)
</script>


<template>
    <input v-model="email" type="text" name="email" placeholder="Email address"
        class="p-2 border-2 border-white rounded-md text-black" />
    <button v-if="!loggedIn" @click="user"
        class="p-4 px-10 mt-2 mb-10 hover:bg-white hover:text-black border-white border rounded-md shadow-lg shadow-white">Connect</button>
    <button v-else
        class="p-4 px-10 mt-2 mb-10 hover:bg-white hover:text-black border-white border rounded-md shadow-lg shadow-white">Buy
        Now</button>
</template>