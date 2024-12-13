<template>
    <div class="brandText my-3 py-3">
        <div class="container">
            <h1 class="text-center text-capitalize">Fameset Pricing.</h1>
            <small>Bigin's promise to you is simple: No forced multi-year contracts, no hidden charges. You don't need
                to enter your credit card information to get started. Cancel anytime!</small>

            <div class="my-5">
                <div class="d-none d-md-flex justify-content-center gap-5">
                    <div v-for="(plan, index) in plans" :key="index"
                        class="card mb-3 p-3 py-4 text-white rounded border border-2 test-border"
                        :class="{ 'recommended': index === 1 }" :style="[
                            { backgroundColor: index === 1 ? 'black !important' : '' },
                            { border: index === 1 ? '3px solid gold !important' : '' }
                        ]" style="background-color:black !important ;">

                        <div v-if="index === 1" class="position-absolute rotate mb-3" style="font-size: 12px;top: -1%; left:38% ;">
                            <span class='text-dark p-1 px-2 rounded text-uppercase fw-bold' style=" background-color: gold;">Recommended</span>
                        </div>

                        <div class="py-2 border-bottom fw-bold">{{
                            plan.name }}</div>
                        <div class="card-body text-center">
                            <p class="mb-0 card-title fs-3">₹ <span class="fw-bold">{{ plan.price }} </span></p>
                            <p class="mb-0 "> <span class="smaller">Plus 18% gst</span></p>
                            <p><small class="text-capitalize">{{ plan.tag
                                    }}</small></p>
                            <div v-if="plan.name === 'Elite'" class="d-flex justify-content-center align-items-center">
                                <p class="fw-light d-inline-block px-4 rounded-3" style="background:gold;">
                                    <span class="text-decoration-line-through text-dark">{{ plan.mrp }}</span>
                                    <span class="text-dark"> ({{ getDiscount(plan) }}% discount)</span>
                                </p>
                            </div>

                            <ul class="list-group">
                                <small class="text-start text-uppercase fw-bold my-2 text-white">{{ plan.key
                                    }}</small>
                                <li v-for="(feature, featureIndex) in plan.features" :key="featureIndex"
                                    class="text-white px-0 list-group-item text-start text-capitalize border-0"
                                    style="background-color:black !important ;">
                                    <div class="d-flex justify-content-between">
                                        <div>
                                            <i class="bi bi-check-circle text-success method1"></i>
                                            <span class="px-2">
                                                {{ feature.text }}
                                            </span>
                                        </div>
                                        <i class="bi bi-info-circle method1" data-bs-toggle="tooltip"
                                            data-bs-placement="top" :data-bs-title="feature.tooltip"></i>
                                    </div>
                                </li>

                                <h6 v-if="plan.comingSoonFeatures"
                                    class="text-start text-uppercase mt-4 fw-bold text-warning">Coming Soon</h6>

                                <li v-for="(feature, featureIndex) in plan.comingSoonFeatures" :key="featureIndex"
                                    class="text-white px-0 list-group-item text-start text-capitalize border-0"
                                    style="background-color:black !important ;">
                                    <div class="d-flex justify-content-between">
                                        <div>
                                            <i class="bi bi-clock text-warning method1"></i>
                                            <span class="px-2">
                                                {{ feature.text }}
                                            </span>
                                        </div>
                                        <i class="bi bi-info-circle method1" data-bs-toggle="tooltip"
                                            data-bs-placement="top" :data-bs-title="feature.tooltip"></i>
                                    </div>
                                </li>
                            </ul>

                        </div>
                        <div class="card-footer bg-dark text-white p-0 border-top pt-2"
                            :style="{ backgroundColor: index === 1 ? 'black !important' : '' }"
                            style="background-color:black !important ;">
                            <p class="card-text text-capitalize smaller">{{ plan.description }}</p>
                            <div class="d-flex justify-content-center gap-2 my-3">
                                <button class="btn fw-bold text-white w-100 brand-btn" @click="enquiry(plan.name)">{{
                                    plan.button
                                }}</button>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="d-md-none">
                    <!-- Nav Tabs -->
                    <ul class="nav nav-tabs d-md-flex justify-content-center gap-5 border-bottom-0 shadow rounded p-2"
                        id="planTabs" role="tablist" style="background-color: black !important">
                        <li class="nav-item" v-for="(plan, index) in plans" :key="index" role="presentation">
                            <a class="btn nav-link text-white" :class="{ active: index === 1 }"
                                :id="'plan-' + plan.id + '-tab'" data-bs-toggle="tab" :href="'#plan-' + plan.id"
                                role="tab" :aria-controls="'plan-' + plan.id"
                                :aria-selected="index === 0 ? 'true' : 'false'">
                                {{ plan.name }}
                            </a>
                        </li>
                    </ul>

                    <!-- Tab Contents -->
                    <div class="tab-content mt-5">
                        <div v-for="(plan, index) in plans" :key="'content-' + index" :id="'plan-' + plan.id"
                            :class="{ 'show active': index === 1 }" class="tab-pane fade" role="tabpanel"
                            :aria-labelledby="'plan-' + plan.id">

                            <div class="card mb-3 p-3 py-4 text-white rounded border border-2 test-border"
                                :class="{ 'recommended': index === 1 }" :style="[
                                    { backgroundColor: index === 1 ? 'black !important' : '' },
                                    { border: index === 1 ? '3px solid gold !important' : '' }
                                ]" style="background-color:black !important ;">
                                <div v-if="index === 1" class="position-absolute rotate"
                                    style="font-size: 12px; top: -1%;left:33%; right:auto;">
                                    <span class='text-dark p-1 px-2 rounded text-uppercase fw-bold'
                                        style="background-color: gold;">Recommended</span>
                                </div>

                                <div class="py-2 border-bottom fw-bold">{{ plan.name }}</div>

                                <div class="card-body text-center">
                                    <p class="mb-0 card-title fs-3">₹ <span class="fw-bold">{{ plan.price }} </span></p>
                                    <p class="mb-0"><span class="smaller">Plus 18% GST</span></p>
                                    <p><small class="text-capitalize">{{ plan.tag }}</small></p>

                                    <div v-if="plan.name === 'Elite'"
                                        class="d-flex justify-content-center align-items-center">
                                        <p class="fw-light d-inline-block px-4 rounded-3" style="background:gold;">
                                            <span class="text-decoration-line-through text-dark">{{ plan.mrp }}</span>
                                            <span class="text-dark"> ({{ getDiscount(plan) }}% discount)</span>
                                        </p>
                                    </div>
                                    <ul class="list-group">
                                        <small class="text-start text-uppercase fw-bold my-2 text-white">{{ plan.key
                                            }}</small>
                                        <li v-for="(feature, featureIndex) in plan.features" :key="featureIndex"
                                            class="text-white px-0 list-group-item text-start text-capitalize border-0"
                                            style="background-color:black !important;">
                                            <div class="d-flex justify-content-between">
                                                <div>
                                                    <i class="bi bi-check-circle text-success method1"></i>
                                                    <span class="px-2">{{ feature.text }}</span>
                                                </div>
                                                <i class="bi bi-info-circle method1" data-bs-toggle="tooltip"
                                                    data-bs-placement="top" :data-bs-title="feature.tooltip"></i>
                                            </div>
                                        </li>

                                        <h6 v-if="plan.comingSoonFeatures"
                                            class="text-start text-uppercase mt-4 fw-bold text-warning">Coming Soon</h6>

                                        <li v-for="(feature, featureIndex) in plan.comingSoonFeatures"
                                            :key="featureIndex"
                                            class="text-white px-0 list-group-item text-start text-capitalize border-0"
                                            style="background-color:black !important;">
                                            <div class="d-flex justify-content-between">
                                                <div>
                                                    <i class="bi bi-clock text-warning method1"></i>
                                                    <span class="px-2">{{ feature.text }}</span>
                                                </div>
                                                <i class="bi bi-info-circle method1" data-bs-toggle="tooltip"
                                                    data-bs-placement="top" :data-bs-title="feature.tooltip"></i>
                                            </div>
                                        </li>
                                    </ul>

                                </div>

                                <div class="card-footer text-white p-0 border-top pt-2"
                                    style="background-color:black !important ;">
                                    <p class="card-text text-capitalize smaller">{{ plan.description }}</p>
                                    <div class="d-flex justify-content-center gap-2 my-3">
                                        <button class="btn fw-bold text-white w-100 brand-btn"
                                            @click="enquiry(plan.name)">{{
                                                plan.button
                                            }}</button>
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
                            text: "Profile Picture",
                            tooltip: "Easily update and showcase your professional profile picture to represent yourself effectively."
                        },
                        {
                            text: "Banner Image",
                            tooltip: "Enhance your visual presence with custom banner images designed for impact."
                        },
                        {
                            text: "Social Profiles",
                            tooltip: "Connect all your social profiles in one place for seamless networking."
                        },
                        {
                            text: "Bank Details",
                            tooltip: "Securely manage and share your bank details for effortless transactions."
                        },
                        {
                            text: "Contact Details",
                            tooltip: "Ensure easy accessibility with your up-to-date contact details."
                        },
                        {
                            text: "Link Website",
                            tooltip: "Showcase your online presence with fully customized and professional websites."
                        },
                        {
                            text: "Multiple Files",
                            tooltip: "Organize and manage multiple files efficiently in one secure location."
                        },
                        {
                            text: "Share",
                            tooltip: "Share your content and updates effortlessly across platforms."
                        },
                        {
                            text: "QR Code",
                            tooltip: "Generate and use QR codes for quick and convenient access to your information."
                        },
                        {
                            text: "Account Match",
                            tooltip: "Find and link accounts seamlessly to optimize your online interactions."
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
                            text: "Skill Bars",
                            tooltip: "Display your professional skills and expertise prominently on your card."
                        },
                        {
                            text: "Keywords",
                            tooltip: "Display your professional skills and expertise prominently on your card."
                        },
                        {
                            text: "Brand Url",
                            tooltip: "Display your professional skills and expertise prominently on your card."
                        },
                        {
                            text: "Download",
                            tooltip: "Display your professional skills and expertise prominently on your card."
                        },
                        {
                            text: "Fun Facts",
                            tooltip: "Showcase unique and interesting facts about yourself or your business."
                        },
                        {
                            text: "Achievements",
                            tooltip: "Highlight key skills or attributes that define your professional persona."
                        }
                    ]
                },
                {
                    id: 3,
                    name: "Elite",
                    price: "5,000",
                    mrp: "12,500",
                    tag: "/account/year",
                    description: "Enjoy our advanced offering for fast-growing businesses and Networking.",
                    button: "Get Started",
                    button2: "Buy now",
                    key: "key features",
                    features: [
                        {
                            text: "All features of pro plan",
                            tooltip: "Enjoy advanced features and premium benefits available in the Pro plan.",
                        },
                        {
                            text: "Reviews",
                            tooltip: "Display your professional skills and expertise prominently on your card."
                        },
                        {
                            text: "Timeline",
                            tooltip: "Showcase your career or project milestones in a visually appealing timeline."
                        },
                    ],
                    comingSoonFeatures: [
                        {
                            text: "Hearts",
                            tooltip: "Receive love and appreciation from your audience as they interact with your card.",
                        },
                        {
                            text: "Promotes",
                            tooltip: "Boost your visibility by promoting your card across multiple platforms.",
                        },
                        {
                            text: "Reactions",
                            tooltip: "Collect feedback and engagement through reactions to your card content.",
                        },
                        {
                            text: "Reviews",
                            tooltip: "Showcase customer feedback and reviews to build trust and credibility.",
                        },
                        {
                            text: "Testimonial",
                            tooltip: "Display heartfelt testimonials from clients or customers to strengthen your reputation.",
                        },
                    ],
                }
            ]


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
        },
        enquiry(name) {
            const phoneNumber = "8802172121";
            const whatsappUrl = `https://wa.me/${phoneNumber}?text=Hello, I would like to enquire about your services ${name}`;
            window.open(whatsappUrl, "_blank");
        }

    }
};
</script>

<style scoped>
.nav-link {
    transition: background-color 0.3s ease, color 0.3s ease;
}

.nav-link.active {
    background: var(--bg-glow) !important;
    color: black !important;
    transition: background-color 0.3s ease, color 0.3s ease, transform 0.3s ease;
}

.sticky-container {
    position: sticky;
    top: 70px;
    z-index: 10;
    background-color: white;
}

.test-border {
    border-color: black !important;
}
</style>
