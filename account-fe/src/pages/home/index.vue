<template>
    <view class="home">
        1111
        <text class="title">{{ title }}</text>
        <button @click="handleOpenCalendar">打开日历</button>
        <uni-calendar
            ref="calendarRef"
            :insert="false"
            :lunar="true"
            @confirm="handleCalendarConfirm"
        />
    </view>
</template>

<script setup lang="ts">
import { ref } from 'vue';
const title = ref('Hello11');
const calendarRef = ref<{ open(): void } | null>(null);

const handleCalendarConfirm = (e: any) => {
    console.log('e', e);
};

const handleOpenCalendar = () => {
    calendarRef.value?.open();
};
</script>

<style>
.content {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
</style>
