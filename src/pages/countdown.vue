<route lang="json">
{
    "meta": {
        "title": "Countdown"
    }
}
</route>

<template>
    <vue-countdown v-if="seconds" :time="countdownTime" v-slot="{ days, hours, minutes, seconds }" :style="{
        'font-size': fontSize,
        'text-shadow': `0px 0px 25px rgba(255, 255, 255, 1)`
    }">
    {{ minutes < 10 ? `0${minutes}` : minutes }}:{{ seconds < 10 ? `0${seconds}` : seconds }}
    </vue-countdown>
    <div class="" v-else>
        00:00
    </div>
</template>
<script setup lang="ts">
import { useRoute } from 'vue-router'

const route = useRoute()
const seconds: number = (route.query.seconds ?? 0) as number
const countdownTime: number = seconds * 1000
const fontSize = route.query.fontSize ?? '5em'
</script>
