<template>
    <div class="container my-5">
        <div class="row align-items-center">
            <div class="col-md-6">
                <h2 class="mb-3">
                    <span class="text-warning">Seller Success</span> Stories
                </h2>
                <p class="mb-4">14 Lakh+ sellers trust Covisor Biz for their online business.</p>
                <!-- <button class="btn btn-outline-primary">See All Stories</button> -->
            </div>
            <div class="col-md-6">
                <div class="position-relative">
                    <div class="card border-0 shadow bg-dark text-white">
                        <div class="card-body">
                            <div class="d-flex flex-column justify-content-center align-items-center mb-3">
                                <img :src="currentStory.image" alt="Seller" class="rounded-circle me-3" width="60"
                                    height="60">
                                <div>
                                    <h5 class="card-title mb-0">{{ currentStory.name }}</h5>
                                    <p class="card-text">{{ currentStory.company }}</p>
                                </div>
                            </div>
                            <blockquote class="blockquote mb-0">
                                <p>{{ currentStory.quote }}</p>
                            </blockquote>
                        </div>
                    </div>
                    <div class="position-absolute top-50 translate-middle" style="left: 0%;">
                        <button class="btn rounded-circle shadow py-2"
                            style="background-color: var(--brand-color) !important;" @click="prevStory"><i
                                class="bi bi-chevron-left"></i></button>
                    </div>
                    <div class="position-absolute top-50 translate-middle" style="right: -7%;">
                        <button class="btn rounded-circle shadow py-2"
                            style="background-color: var(--brand-color) !important;" @click="nextStory"><i
                                class="bi bi-chevron-right"></i></button>
                    </div>
                </div>
                <div class="text-center mt-3">
                    <span v-for="(story, index) in stories" :key="index" class="dot mx-1"
                        :class="{ 'active': index === currentIndex }"></span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            currentIndex: 0,
            stories: [
                {
                    "name": "Emily",
                    "company": "BrandElevate Co.",
                    "image": "img/users/5.png",
                    "quote": "Emily’s Creative Agency Emily, a branding expert, saw Fameset as the perfect addition to her portfolio of services. She offered clients personalized Famesets integrated with brand colors, logos, and social media links. Her unique selling point was the ability to tie the Fameset design to the client’s marketing campaigns, creating a cohesive brand identity. By delivering tailored solutions and maintaining strong client relationships, Emily boosted her agency’s revenue while helping businesses enhance their digital presence."
                },
                {
                    "name": "Aiden",
                    "company": "ProNet Solutions",
                    "image": "img/users/6.png",
                    "quote": "Aiden’s Corporate Outreach Aiden, a business consultant, incorporated Fameset into his corporate training programs. He provided executives and teams with custom Famesets to streamline networking during conferences and business meetings. His strategy of bundling Famesets with other consultancy services created additional value for clients. Over time, Aiden expanded his reselling operations and secured contracts with multiple corporations, transforming Fameset into a core part of his business model."
                },
                {
                    "name": "Olivia",
                    "company": "Green Network Hub",
                    "image": "img/users/7.png",
                    "quote": "Olivia’s Eco-Friendly Network Olivia, an environmentalist and entrepreneur, launched a Fameset reseller business aimed at NGOs and sustainability-focused businesses. She emphasized the paperless aspect of Fameset, which aligned perfectly with her clients’ eco-friendly values. Olivia also partnered with environmental organizations to promote the adoption of digital networking tools. Her commitment to sustainability and effective partnerships helped her create a thriving reseller business with a loyal, niche client base."
                },
            ]
        }
    },
    computed: {
        currentStory() {
            return this.stories[this.currentIndex];
        }
    },
    methods: {
        nextStory() {
            this.currentIndex = (this.currentIndex + 1) % this.stories.length;
        },
        prevStory() {
            this.currentIndex = (this.currentIndex - 1 + this.stories.length) % this.stories.length;
        }
    }
}
</script>

<style scoped>
.dot {
    height: 10px;
    width: 10px;
    background-color: #000;
    border-radius: 50%;
    display: inline-block;
}

.dot.active {
    background-color: var(--brand-color);
}
</style>