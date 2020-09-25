<template>
<img alt="Vue logo" src="./assets/logo.png" />
<br />
<a-button type="primary" @click="adduser">按钮 </a-button>
<HelloWorld msg="Hello Vue 3.0 + Vite" />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
    name: "App",
    components: {
        HelloWorld,
    },
    setup() {
        const adduser = () => {
            console.log("按钮事件");
        };

        return {
            adduser,
        };
    },
};
</script>
