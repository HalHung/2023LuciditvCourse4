<template>
    <div id="demo">
        <h1>Hellow 
            <span class="name">{{ name }}</span>
        </h1>
        <div>
            <input placeholder="請輸入" v-model="myinput" clearable class="my-input" />
            <div>這裡是你輸入的內容：
                <div class="show-input">{{ myinput }}</div>
            </div>
        </div>
    </div>
</template>
    
<script setup lang='ts'>
import { ref, reactive, onMounted, watch } from 'vue'
const name = ref('Hal')
const myinput = ref('')

watch(() => myinput.value, (newValue, oldValue) => {
    console.log('myinput: ', myinput.value);
    // console.log('新值: ', newValue, ' 舊值: ', oldValue);
})

// onMounted(() => {
//     console.log('name: ', name.value);
// })
</script>
    
<style>
#demo {
    text-align: center;
}

h1 {
    font-size: 50px;
    color:darkorange;
    font-weight: 900;
}

.name {
    color: darkcyan;
}

.my-input {
    width: 500px !important;
    margin-bottom: 10px;
}

.show-input {
    font-size: 34px;
    color: midnightblue;
    font-weight: 500;
}
</style>