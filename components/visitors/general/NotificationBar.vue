<template>
    <span>
        <div
            v-for="i in notificationErrors"
            :key="i.id"
            :class="'full-background ' + i.color"
        >
            {{i.text}}
        </div>
    </span>
</template>

<script>
export default {
    name: 'NotificationBar',
    data: () => ({
        notificationErrors: [{ 'color': 'red', id: 0, text: 'Oh, we are having some issues' }]
    })
}
</script>

<style scoped>
    div {
        padding: 0px;
    }
    .full-background {
        padding: 10px;
        z-index: 0;
        position: relative;
        text-align: center;
        color: white;
    }
</style>