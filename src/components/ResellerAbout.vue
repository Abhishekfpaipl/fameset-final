<template>
    <div>
        <div class="container my-5">
            <h3 class="text-center">Our Core Values</h3>
            <p class="text-center container">
                One thing that we've tried to keep consistent through all these years is our core set of values and
                beliefs. They have helped us get to where we are today, and they guide us as we grow. We inculcate these
                values in everything we do - from the littlest of things to the biggest of decisions.
            </p>
            <div class="p-2 row">
                <div v-for="(data, index) in datas" :key="index" class="col-12 col-md-6 g-3" v-observe>
                    <div class="d-flex flex-column align-items-center border h-100 p-2">
                        <i :class="data.icon" class="fs-2 mx-3 icon-shake" style="color: gold !important"></i>
                        <p class="fw-bold">{{ data.heading }}</p>
                        <p>{{ data.text }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            datas: [
                {
                    "icon": "bi bi-lightbulb",
                    "heading": "Innovate Fearlessly",
                    "text": "We value creativity and new ideas that challenge the norm and drive progress."
                },
                {
                    "icon": "bi bi-person",
                    "heading": "Authenticity Matters",
                    "text": "We celebrate individuality and encourage everyone to bring their true selves to work."
                },
                {
                    "icon": "bi bi-people",
                    "heading": "Respect & Inclusion",
                    "text": "We foster an environment of mutual respect and inclusivity, ensuring everyone feels valued."
                },
                {
                    "icon": "bi bi-check-square",
                    "heading": "Accountability Drives Excellence",
                    "text": "We take ownership of our work, striving for precision and excellence in everything we do."
                },
                {
                    "icon": "bi bi-gear",
                    "heading": "Proactive Problem Solving",
                    "text": "We encourage taking initiative to make improvements and solve problems with creativity and determination."
                },
                {
                    "icon": "bi bi-graph-up",
                    "heading": "Continuous Growth",
                    "text": "We prioritize learning and growth, empowering our team to evolve and thrive every day."
                }
            ]
        };
    }
};
</script>

<style scoped>
</style>
