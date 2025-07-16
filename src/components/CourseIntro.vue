<template>
    <li>
        <h2>{{ id }}-Current:{{ current }}-isCurrent:{{ isCurrent }}</h2>
        <button @click="toggleCourseDetail">show detail</button>
        <button @click="toggleCurrent">toggle isCurrent status</button>
        <ul v-if="detailsVisible">
            <li>{{ name }}</li>
            <li>{{ duration }}</li>
        </ul>
    </li>
</template>

<script>
export default {
    props: {
        id: { type: String, required: true },
        name: { type: String, required: true },
        duration: {
            type: Number, required: true, validator: function (value) {
                return value > 7
            }
        },
        current: { type: Boolean, required: false, default: false }
    },
    data() {
        return {
            detailsVisible: true,
            isCurrent: this.current
        }
    },
    methods: {
        toggleCourseDetail() {
            this.detailsVisible = !this.detailsVisible
        },
        toggleCurrent() {
            this.isCurrent = !this.isCurrent;
        }
    }
}
</script>
<style>
#app ul {
    margin: 0;
    padding: 0;
    list-style: none;
}

#app li {
    box-shadow: 0 4px 8px rgba(0, 0, 128, 0.26);
    margin: 1rem auto;
    border-radius: 8px;
    text-align: center;
    width: 50%;
    max-width: 40rem;
    background-color: #b6fab6;
}

#app button {
    font: inherit;
    cursor: pointer;
    border: 1px solid #FF0077;
    background-color: #f3baf3;
    color: blue;

}
</style>