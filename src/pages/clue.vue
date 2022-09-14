<route lang="json">
{
    "meta": {
    "title": "Clue"
    }
}
</route>
<template>
    <div class="grid grid-cols-2 gap-3" :style="{
        'font-size': fontSize
    }">
        <div class="flex gap-2 items-center">
            <i class="fa-solid fa-circle-up"></i>
            <span v-text="up"></span>
        </div>
        <div class="flex gap-2 items-center">
            <i class="fa-solid fa-circle-right"></i>
            <span v-text="right"></span>
        </div>
        <div class="flex gap-2 items-center">
            <i class="fa-solid fa-circle-down"></i>
            <span v-text="down"></span>
        </div>
        <div class="flex gap-2 items-center">
            <i class="fa-solid fa-circle-left"></i>
            <span v-text="left"></span>
        </div>
        <div class="flex justify-center items-center col-span-2">
            <i class="fa-solid" :class="[`fa-${identifier}`]"></i>
        </div>
    </div>
</template>
<script setup lang="ts">
import { useRoute } from 'vue-router'

const route = useRoute()

const fontSize: string = (route.query.fontSize) as string ?? '3em'
const identifier: string = (route.query.identifier ?? 'none') as string
const up: number = (route.query.up ?? 0) as number
const right: number = (route.query.right ?? 0) as number
const down: number = (route.query.down ?? 0) as number
const left: number = (route.query.left ?? 0) as number

</script>
