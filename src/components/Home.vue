<template>
    <div>
        <h1 class="mb-6 text-3xl font-extrabold">Estou na Home</h1>

        <p class="mb-3">Este nome vem da store: {{ name }}</p>

        <input
            v-model="newName"
            type="text"
            class="p-2 mr-2 border border-gray-500 rounded"
        />

        <button @click="saveName" class="p-2 text-white bg-indigo-600 rounded">
            Enviar
        </button>
    </div>
</template>

<script setup>
import { computed, ref } from "vue"
import { useStore } from "vuex"
import { useRouter } from "vue-router"

const store = useStore()
const router = useRouter()

const name = computed(() => {
    return store.state.user.name
})

const newName = ref("")

function saveName() {
    store.dispatch("saveName", newName.value)
    newName.value = ""
    router.push('/about')
}
</script>

<script>
export default {
    name: "HomePage",
}
</script>

<style lang="css" scoped></style>
