<template>
    <div class="container">
        <h3>History</h3>
        <div class="flex">
            <p
                v-for="(number, index) in history"
                :key="index"
                :class="activeIndexes(parseInt(value)).includes(index) && 'matched'"
            >
            {{number}}
            </p>
        </div>
        <input 
            placeholder="Search by Index"
            type="number"
            v-model="value"
            
            >
    </div>
</template>

<script>
import { mapState, mapGetters } from "vuex"

export default {
    data() {
        return {
            value: 0
        }
    },
    computed: {
        ...mapState(["history"]),
        ...mapGetters(["activeIndexes"])
    }
}
</script>

<style scoped>
.container {
    margin-top: 7rem;
}
.flex {
    display: flex;
    text-align: center;
    width: 25rem;
    margin: 0 auto;
    justify-content: center;
    flex-wrap: wrap;
}
.flex p {
    margin: 1rem;
    padding: 1rem;
}
.matched {
    color: white;
    background-color: #41B893;
    border-radius: 15%;
}
</style>
