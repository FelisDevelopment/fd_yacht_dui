<route lang="json">
{
    "meta": {
        "title": "Text"
    }
}
</route>

<template>
    <div :style="{
        'font-size': fontSize,
        'text-shadow': `0px 0px 25px rgba(255, 255, 255, 1)`
    }" v-text="text"></div>
</template>
<script setup lang="ts">
import { useRoute } from 'vue-router'

const route = useRoute()
const text: string = (route.query.text) as string
const fontSize: string = (route.query.fontSize) as string ?? '5em'
</script>
