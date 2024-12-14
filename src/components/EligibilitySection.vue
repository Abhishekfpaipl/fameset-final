<template>
    <div class="container my-5">
        <div class="row row-cols-1 row-cols-md-2 g-3">
            <div v-for="(feature, index) in features" :key="index" class="col mb-4" v-observe>
                <div class="card h-100 bg-transparent method1" style="border: 1px solid gold;">
                    <div class="card-body">
                        <div class="d-flex gap-2 align-items-center justify-content-center">
                            <img :src="feature.gif" alt="Feature GIF" class="img-fluid mb-3" style="max-width: 50px;">
                            <h5 class="card-title">{{ feature.title }}</h5>
                        </div>
                        <p class="card-text">{{ feature.description }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'VerificationFeatures',
    data() {
        return {
            features: [
                {
                    title: 'Real-time Identity Verification',
                    description: 'Instantly verifies the identity of users using advanced algorithms and data matching.',
                    gif: '/img/test.gif'
                },
                {
                    title: 'Document Authentication',
                    description: 'Automatically checks the authenticity of government-issued IDs and other supporting documents.',
                    gif: '/img/test.gif'
                },
                {
                    title: 'Facial Recognition Technology',
                    description: 'This technology employs biometric facial recognition to match the user\'s face with their ID for added security.',
                    gif: '/img/test.gif'
                },
                {
                    title: 'Compliance & Regulation Support',
                    description: 'Ensures adherence to KYC regulations and industry standards, reducing compliance risks.',
                    gif: '/img/test.gif'
                }
            ]
        };
    }
};
</script>

<style scoped>
.card-body {
    text-align: center;
    padding: 20px;
}

.card img {
    width: 100%;
    max-width: 50px;
    height: auto;
    margin-bottom: 15px;
}
</style>
