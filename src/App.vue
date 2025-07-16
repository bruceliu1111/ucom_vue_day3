<template>
    <h1>Hello World from SFC(single file component)</h1>
    <ul>
        <course-intro id="poop" name="python and oop" duration=35></course-intro>
        <course-intro id="bdpy" name="python and big data" duration=42></course-intro>

    </ul>
</template>

<script>
export default {
    data() {
        return {
            courses: [{ id: "poop", name: "python oop", duration: 35 }]
        }
    }
}
</script>