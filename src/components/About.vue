<template>
    <h1 class="font-bold text-2xl">
        Sobre {{ name }}
    </h1>
</template>

<script setup>
import { computed } from 'vue';
import { useStore } from 'vuex';
const store = useStore()

const name = computed(() => {
    return store.state.user.name
})

// const newName = ref('')


</script>

<script>
export default {
    name: "AboutPage",
}
</script>

<style lang="css" scoped></style>
