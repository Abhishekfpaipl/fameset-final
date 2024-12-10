<template>
    <div class="container my-5">
        <div class="row align-items-center">
            <div class="col-md-6">
                <h2 class="mb-3">
                    <span class="text-warning">Seller Success</span> Stories
                </h2>
                <p class="mb-4">14 Lakh+ sellers trust Covisor Biz for their online business.</p>
            </div>
            <div class="col-md-6">
                <!-- <div class="position-relative">
                    <div class="card border-0 shadow bg-dark text-white">
                        <div class="card-body">
                            <div class="d-flex flex-column justify-content-center align-items-center mb-3">
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
                        <button class="btn rounded-circle shadow py-2" style="background-color: gold !important;"
                            @click="prevStory"><i class="bi bi-chevron-left"></i></button>
                    </div>
                    <div class="position-absolute top-50 translate-middle" style="right: -7%;">
                        <button class="btn rounded-circle shadow py-2" style="background-color: gold !important;"
                            @click="nextStory"><i class="bi bi-chevron-right"></i></button>
                    </div>
                </div>
                <div class="text-center mt-3">
                    <span v-for="(story, index) in stories" :key="index" class="dot mx-1"
                        :class="{ 'active': index === currentIndex }"></span>
                </div> -->

                <div id="googleReview" class="carousel slide" data-bs-ride="carousel">
                    <div class="carousel-inner">
                        <div class="carousel-item p-2 pt-5" :class="{ 'active': index === 0 }"
                            v-for="(pair, index) in stories" :key="index" data-bs-interval="3000" v-observe>
                            <div class="d-flex justify-content-between">
                                <div class="card pb-5 m-2 brand-bg text-white" style="min-height: 300px !important;">
                                    <div class="card-body">
                                        <div class="d-flex flex-column justify-content-center align-items-center mb-2">
                                            <i class="bi bi-person-circle"
                                                style="margin-top: -50px; font-size: 40px;"></i>
                                            <h5 class="card-title m-0 text-uppercase fw-bold">{{ pair.name }}
                                            </h5>
                                        </div>
                                        <p class="text-center px-3"><i class="bi bi-quote fs-4"></i> {{
                                            pair.quote }}
                                        </p>
                                        <div class="d-flex justify-content-end align-items-center mb-2">
                                            <span class="text-muted">{{ pair.date }}</span>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>

                    </div>
                    <button class="carousel-control-prev" type="button" data-bs-target="#googleReview"
                        data-bs-slide="prev">
                        <i class="bi bi-chevron-left fs-1" style="color:gold !important"></i>
                    </button>
                    <button class="carousel-control-next" type="button" data-bs-target="#googleReview"
                        data-bs-slide="next">
                        <i class="bi bi-chevron-right fs-1" style="color:gold !important"></i>
                    </button>
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
                    "name": "Aneeta",
                    "company": "BrandElevate Co.",
                    "image": "img/users/5.png",
                    "quote": "Aneeta’s Creative Agency Aneeta, a branding expert, saw Fameset as the perfect addition to her portfolio of services. She offered clients personalized Famesets integrated with brand colors, logos, and social media links. Her unique selling point was the ability to tie the Fameset design to the client’s marketing campaigns, creating a cohesive brand identity. By delivering tailored solutions and maintaining strong client relationships, Aneeta boosted her agency’s revenue while helping businesses enhance their digital presence."
                },
                {
                    "name": "Rahul",
                    "company": "ProNet Solutions",
                    "image": "img/users/6.png",
                    "quote": "Rahul’s Corporate Outreach Rahul, a business consultant, incorporated Fameset into his corporate training programs. He provided executives and teams with custom Famesets to streamline networking during conferences and business meetings. His strategy of bundling Famesets with other consultancy services created additional value for clients. Over time, Rahul expanded his reselling operations and secured contracts with multiple corporations, transforming Fameset into a core part of his business model."
                },
                {
                    "name": "Sadhana",
                    "company": "Green Network Hub",
                    "image": "img/users/7.png",
                    "quote": "Sadhana’s Eco-Friendly Network Sadhana, an environmentalist and entrepreneur, launched a Fameset reseller business aimed at NGOs and sustainability-focused businesses. She emphasized the paperless aspect of Fameset, which aligned perfectly with her clients’ eco-friendly values. Sadhana also partnered with environmental organizations to promote the adoption of digital networking tools. Her commitment to sustainability and effective partnerships helped her create a thriving reseller business with a loyal, niche client base."
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