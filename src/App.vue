<template>
<img alt="Vue logo" src="./assets/logo.png" />
<br />
<a-button type="primary" @click="addaxios">按钮 </a-button>
<br />
{{ data1 }}
{{ datared.data12 }}
<HelloWorld msg="Hello Vue 3.0 + Vite" />
</template>

<script>
import {
    getCurrentInstance,
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
        const {
            ctx
        } = getCurrentInstance();
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
        const addaxios = () => {
            addount();
            ctx
                .$axios({
                    method: "post",
                    url: "http://localhost:8088/home/post",
                    data: {
                        id: "requestUrl",
                    },
                })
                .then((result) => {
                    console.log(result);
                })
                .catch((err) => {
                    console.log(err);
                });
        };

        return {
            adduser,
            addount,
            data1,
            datared,
            addaxios,
        };
    },
};
</script>
