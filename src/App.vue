<template>
<img alt="Vue logo" src="./assets/logo.png" />
<br />
<a-button type="primary" @click="addount">按钮 </a-button>
<br />
{{ data1 }}
{{ datared.data12 }}
<HelloWorld msg="Hello Vue 3.0 + Vite" />
</template>

<script>
import {
    reactive,
    ref
} from "vue";
import HelloWorld from "./components/HelloWorld.vue";

export default {
    name: "App",
    components: {
        HelloWorld,
    },
    setup() {
        const data1 = ref("0");
        const datared = reactive({
            data12: 1,
        });
        const adduser = () => {
            data1++;
            console.log(data1);
            console.log("按钮事件");
        };
        const addount = () => {
            data1.value++;
            datared.data12 = datared.data12 * 2;
            console.log("按钮事件");
        };

        return {
            adduser,
            addount,
            data1,
            datared,
        };
    },
};
</script>
