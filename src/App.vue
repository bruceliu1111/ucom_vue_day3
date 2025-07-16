<template>
    <h1>Hello World from SFC(single file component)</h1>
    <ul>
        <course-intro v-for="course in courses" :key="course.id" :id="course.id" :name="course.name"
            :duration="course.duration" :current="course.current"></course-intro>
    </ul>
</template>

<script>
export default {
    created() {
        console.log("app元件被呼叫, 初始化中...")
        this.emitter.on('toggle-current', idx => {
            const course = this.courses.find(course => course.id === idx)
            course.current = !course.current
            console.log(`已變更${idx}的current state`)
        })
    },
    data() {
        return {
            courses: [{ id: "poop", name: "python oop", duration: 35, current: true },
            { id: "bdpy", name: "python and big data", duration: 42, current: false },
            { id: "pykt", name: 'keras and tensorflow', duration: 35, current: true }
            ]
        }
    }
}
</script>