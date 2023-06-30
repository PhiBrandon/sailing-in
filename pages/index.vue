<script setup>
import { MagicLink } from "@thirdweb-dev/wallets";
import { ThirdwebSDK } from "@thirdweb-dev/sdk";



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
    <img src="/img/comrade.jpg" alt="For The Way of Man" />
    <h1>Comrade Coin</h1>
    <Login />
</template>