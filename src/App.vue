<template>
    <h1>Hello World from SFC(single file component)</h1>
    <ul>
        <course-intro v-for="course in courses" :key="course.id" :id="course.id" :name="course.name"
            :duration="course.duration" :current="course.current"></course-intro>
        <!-- <course-intro id="poop" name="python and oop" duration=35></course-intro>
        <course-intro id="bdpy" name="python and big data" duration=42></course-intro>
        <course-intro id="pykt" name="python and big data" duration="8"></course-intro> -->
    </ul>
</template>

<script>
export default {
    data() {
        return {
            courses: [{ id: "poop", name: "python oop", duration: 35, current: true },
            { id: "bdpy", name: "python and big data", duration:  42, current: false },
            { id: "pykt", name: 'keras and tensorflow', duration: 44, current: true },
            { id: "swift", name: 'iOS use Swift4.0', duration: 58, current: true }
            ]
        }
    }
}
</script>