<template>
    <div :style="{ backgroundColor: bgColor }" class="p-6 m-4 rounded shadow-lg text-white">
        <h1 class="text-4xl font-bold text-center">{{ text }}</h1>
    </div>
</template>

<script>
    export default {
        props: {
            text: {
                type: String,
                required: false
            },
            bgColor: {
                type: String,
                required: false
            }
        }
    }
</script>