<script setup>
import { MagicLink } from "@thirdweb-dev/wallets";
import { ThirdwebSDK } from "@thirdweb-dev/sdk";

const email = ref("")
const loggedIn = ref(false)

const MAGIC_PUB = "pk_live_2437D048F73AF9B9"
const walletlogin = new MagicLink({
    apiKey: MAGIC_PUB,
});

// now connect using email or phone number

const user = async () => {
    console.log(email.value)
    if (email.value == "") {
        console.log(email.value)
        alert("Please enter email")
    } else {
        console.log("worked")
        await walletlogin.connect({
            email: email.value,
        });
        loggedIn.value = true
        email.value = ""
    }

}

</script>

<template>
    <div class="bg-black text-white h-screen h-full flex flex-col justify-center items-center">
        <img src="/img/comrade.jpg" alt="For The Way of Man" />
        <h1>Comrade Coin</h1>
        <input v-model="email" type="text" name="email" placeholder="Email address"
            class="p-2 border-2 border-white rounded-md text-black" />
        <button v-if="!loggedIn" @click="user"
            class="p-4 px-10 mt-2 mb-10 hover:bg-white hover:text-black border-white border rounded-md shadow-lg shadow-white">Connect</button>
        <button v-else 
            class="p-4 px-10 mt-2 mb-10 hover:bg-white hover:text-black border-white border rounded-md shadow-lg shadow-white">Buy Now</button>

    </div>
</template>