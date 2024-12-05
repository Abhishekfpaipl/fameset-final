<template>
    <div class="brandText my-3 py-3">
        <div class="container">
            <h1 class="text-center text-capitalize">Fameset Pricing.</h1>
            <small>Bigin's promise to you is simple: No forced multi-year contracts, no hidden charges. You don't need
                to enter your credit card information to get started. Cancel anytime!</small>

            <div class="my-3">
                <div class="tab-content mt-2 pt-4" id="pills-tabContent">
                    <div class="tab-pane fade" :class="{ 'show active': index === 0 }" v-for="(price, index) in pricing"
                        :key="index" :id="'content-' + index" role="tabpanel" :aria-labelledby="'tab-' + index"
                        tabindex="0">
                        <div class="d-md-flex justify-content-center gap-3">
                            <div v-for="(plan, index) in price.plans" :key="index"
                                class="card mb-3 px-3 bg-dark text-white rounded-0"
                                :class="{ 'recommended': index === 1 }">

                                <div v-if="index === 1" class="position-absolute top-0 start-0 m-2 ms-0"
                                    style="font-size: 12px;">
                                    <span class='text-white bg-danger p-1 px-2 rounded-end-3'>Recommended</span>
                                </div>

                                <div class="py-2 border-bottom fw-bold">{{
                                    plan.name }}</div>
                                <div class="card-body text-center">
                                    <p class="mb-0 card-title fs-3">₹ <span class="fw-bold">{{ plan.price }} </span></p>
                                    <p class="mb-0 "> <span class="smaller">Plus 18% gst</span></p>
                                    <p><small class="text-capitalize">{{ plan.tag
                                            }}</small></p>
                                    <div class="d-flex justify-content-center align-items-center">
                                        <p class="fw-light bg-dark d-inline-block px-4 rounded-3">
                                            <span class="text-decoration-line-through text-white">{{ plan.mrp }}</span>
                                            <span class="text-white"> ({{ getDiscount(plan) }}% discount)</span>
                                        </p>
                                    </div>

                                    <ul v-if="plan.features" class="list-group">
                                        <small class="text-start text-uppercase fw-bold my-2 text-primary">{{ plan.key
                                            }}</small>
                                        <li v-for="(feature, featureIndex) in plan.features" :key="featureIndex"
                                            class="bg-dark text-white px-0 d-flex justify-content-between list-group-item text-start text-capitalize border-0">
                                            <div class="">
                                                <i class="bi bi-check-circle text-success"></i>
                                                <span class="px-2">
                                                    {{ feature.text }}
                                                </span>
                                            </div>
                                            <i class="bi bi-info-circle" data-bs-toggle="tooltip"
                                                data-bs-placement="top" data-bs-custom-class="custom-tooltip"
                                                :data-bs-title="feature.tooltip"></i>
                                        </li>
                                    </ul>
                                </div>
                                <div class="card-footer bg-dark text-white p-0 border-top pt-2">
                                    <p class="card-text text-capitalize smaller">{{ plan.description }}</p>
                                    <div class="d-flex justify-content-center gap-2 my-3">
                                        <button class="btn btn-danger w-100">{{ plan.button }}</button>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "PriceSection",
    data() {
        return {
            pricing: [
                {
                    id: 2,
                    name: "Yearly",
                    description: "This is a basic plan",
                    plans: [
                        {
                            id: 1,
                            name: "Lite",
                            price: "1,000",
                            mrp: "1,200",
                            tag: "/account/year",
                            description: "Start with our lite plan and upgrade only when you need additional features.",
                            button: "Get Started",
                            key: "key features",
                            features: [
                                {
                                    text: "Contact Details",
                                    tooltip: "Easily share your contact information like phone number, email, and address."
                                },
                                {
                                    text: "Social Profiles",
                                    tooltip: "Link your social media profiles to enhance your professional connections."
                                },
                                {
                                    text: "Share",
                                    tooltip: "Share your digital business card instantly via email, social media, or messaging apps."
                                },
                                {
                                    text: "Qr Code",
                                    tooltip: "Generate a QR code for seamless sharing and access to your business card."
                                },
                                {
                                    text: "Fun Facts",
                                    tooltip: "Showcase unique and interesting facts about yourself or your business."
                                },
                                {
                                    text: "Attributes",
                                    tooltip: "Highlight key skills or attributes that define your professional persona."
                                }
                            ] 
                        },
                        {
                            id: 2,
                            name: "Pro",
                            price: "3,000",
                            mrp: "5,000",
                            tag: "/account/year",
                            description: "Choose the right set of features you need to begin your Networking journey.",
                            button: "Get Started",
                            button2: "Buy now",
                            key: "key features",
                            features: [
                                {
                                    text: "All features of lite plan",
                                    tooltip: "Access all the essential features included in the Lite plan for your digital card."
                                },
                                {
                                    text: "Skillset",
                                    tooltip: "Display your professional skills and expertise prominently on your card."
                                },
                                {
                                    text: "Timeline",
                                    tooltip: "Showcase your career or project milestones in a visually appealing timeline."
                                },
                                {
                                    text: "Payment",
                                    tooltip: "Add secure payment links or QR codes to facilitate transactions directly from your card."
                                },
                                {
                                    text: "Website Widget",
                                    tooltip: "Integrate your digital card seamlessly into your website for easy access."
                                }
                            ] 
                        },
                        {
                            id: 3,
                            name: "Elite",
                            price: "10,000",
                            mrp: "25,000",
                            tag: "/account/year",
                            description: "Enjoy our advanced offering for fast-growing businesses and Networking.",
                            button: "Get Started",
                            button2: "Buy now",
                            key: "key features",
                            features: [
                                {
                                    text: "All features of pro plan",
                                    tooltip: "Enjoy advanced features and premium benefits available in the Pro plan."
                                },
                                {
                                    text: "Views",
                                    tooltip: "Track the number of times your digital card has been viewed by others."
                                },
                                {
                                    text: "Achievements",
                                    tooltip: "Highlight your significant accomplishments to impress your audience."
                                },
                                {
                                    text: "Hearts",
                                    tooltip: "Receive love and appreciation from your audience as they interact with your card."
                                },
                                {
                                    text: "Promotes",
                                    tooltip: "Boost your visibility by promoting your card across multiple platforms."
                                },
                                {
                                    text: "Reactions",
                                    tooltip: "Collect feedback and engagement through reactions to your card content."
                                },
                                {
                                    text: "Reviews",
                                    tooltip: "Showcase customer feedback and reviews to build trust and credibility."
                                },
                                {
                                    text: "Testimonial",
                                    tooltip: "Display heartfelt testimonials from clients or customers to strengthen your reputation."
                                }
                            ] 
                        }
                    ]
                },
            ],


        };
    },
    mounted() {
        this.initTooltips();
    },
    updated() {
        this.initTooltips();
    },
    methods: {
        initTooltips() {
            // Initialize tooltips (assuming using Bootstrap's tooltip)
            const tooltipTriggerList = [].slice.call(
                document.querySelectorAll('[data-bs-toggle="tooltip"]')
            );
            tooltipTriggerList.forEach(function (tooltipTriggerEl) {
                new window.bootstrap.Tooltip(tooltipTriggerEl);
            });
        },
        getDiscount(plan) {
            if (plan.mrp && typeof plan.mrp === 'string') {
                const mrp = parseFloat(plan.mrp.replace(/[^\d.-]/g, ''));
                const price = parseFloat(plan.price.replace(/[^\d.-]/g, ''));
                if (!isNaN(mrp) && !isNaN(price) && mrp > 0) {
                    return ((mrp - price) / mrp * 100).toFixed(0);
                }
            }
            return 0;
        }

    }
};
</script>

<style scoped>
.nav-link {
    transition: background-color 0.3s ease, color 0.3s ease;
}

.nav-link.active {
    background-color: var(--bg-primary) !important;
    color: white !important;
    transition: background-color 0.3s ease, color 0.3s ease, transform 0.3s ease;
    transform: scale(1.2);
}

.sticky-container {
    position: sticky;
    top: 70px;
    z-index: 10;
    background-color: white;
}
</style>
