<template>
    <div class="my-3 py-3">
        <div class="container">

            <div class="row row-cols-1 row-cols-md-4 my-3">
                <div class="col" v-for="(plan, index) in plans" :key="index" v-observe>
                    <div class="card mb-3 px-3 py-2 rounded-0 brand-bg text-white h-100"
                        :class="{ 'recommended': index === 2 }" style="">
                        <div class="py-2 border-bottom fw-bold">{{ plan.name }}</div>
                        <div class="card-body text-center">
                            <div class="d-flex justify-content-center align-items-center gap-2">
                                <p v-if="plan.price" class="mb-0 card-title smaller"><span class="fw-bold">₹ {{
                                    plan.price }} </span></p>
                                <p v-else class="mb-0 card-title smaller fw-bold">Custom</p>
                            </div>
                            <p><small class="text-capitalize smaller">sale</small></p>
                            <div v-if="plan.price" class="d-flex justify-content-center align-items-center">
                                <p class="fw-bold d-inline-block px-4 rounded-3"
                                    style="background-color: gold !important">
                                    <span class="text-dark"> ({{ getDiscount(plan) }}% Off)</span>
                                </p>
                            </div>
                            <p v-else class="fw-light d-inline-block px-4 rounded-3" style="color: gold !important">
                                Contact</p>

                            <ul v-if="plan.features" class="list-group">
                                <small class="text-start text-uppercase fw-bold my-2 smaller"
                                    style="color:var(--brand-color) !important;">{{ plan.key
                                    }}</small>
                                <li v-for="(feature, featureIndex) in plan.features" :key="featureIndex"
                                    class="px-0 d-flex justify-content-between list-group-item brand-bg text-white text-start text-capitalize border-0 smaller">
                                    <div class="">
                                        <i class="bi bi-check-circle" style="color:var(--brand-color) !important;"></i>
                                        <span class="px-2">
                                            {{ feature.text }}
                                        </span>
                                    </div>
                                    <i class="bi bi-info-circle" data-bs-toggle="tooltip" data-bs-placement="top"
                                        data-bs-custom-class="custom-tooltip" :data-bs-title="feature.tooltip"></i>
                                </li>
                            </ul>
                        </div>
                        <div class="card-footer  p-0 border-top pt-2">
                            <div class="btn-group w-100 my-2">
                                <a :href="'https://wa.me/8802172121?text=' + encodeURIComponent('Hello, I want to get your ' + plan.name + ' service')"
                                    class="btn text-capitalize px-4 text-dark btn-warning">
                                    <i class="bi bi-whatsapp"></i>
                                    <span class="ms-2">Enquiry</span>
                                </a>
                            </div>
                        </div>
                    </div>
                </div>

            </div>

            <!-- <div class="my-3">
                <ul class="nav nav-pills justify-content-center sticky-container" id="pills-tab" role="tablist">
                    <div class="d-flex border p-2 px-3 rounded shadow " style="">
                        <li class="nav-item" role="presentation" v-for="(price, index) in pricing" :key="index">
                            <button class="nav-link text-muted" :class="{ 'active': index === 0 }" :id="'tab-' + index"
                                data-bs-toggle="pill" :data-bs-target="'#content-' + index" type="button" role="tab"
                                :aria-controls="'content-' + index" :aria-selected="index === 0">{{ price.name
                                }}</button>
                        </li>
                    </div>
                </ul>
                <div class="tab-content mt-2 pt-4" id="pills-tabContent">
                    <div class="tab-pane fade" :class="{ 'show active': index === 0 }" v-for="(price, index) in pricing"
                        :key="index" :id="'content-' + index" role="tabpanel" :aria-labelledby="'tab-' + index"
                        tabindex="0">
                        <div class="container">
                           
                        </div>
                    </div>
                </div>
            </div> -->
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
                    id: 124,
                    name: "Lite",
                    price: "50,000",
                    mrp: "1,00,000",
                    link: "/digital-marketing/",
                    tag: "/user/yearly/billed yearly",
                    description: "Start with our Starter plan and upgrade only when you need additional features.",
                    button: "Get Started",
                    key: "key features",
                    features: [
                        {
                            "text": "One Time",
                            "tooltip": "This service is performed once for a specific result or outcome."
                        },
                        {
                            "text": "100 Accounts ",
                            "tooltip": "Applies to 100 individual accounts per category or service."
                        },
                        {
                            "text": "CRM Software",
                            "tooltip": "Applies to 100 individual accounts per category or service."
                        },
                        {
                            "text": "Traning",
                            "tooltip": "Applies to 100 individual accounts per category or service."
                        },
                        {
                            text: "Content Marketing",
                            tooltip: "Create and distribute engaging content to attract and retain audiences."
                        },

                    ]
                },
                {
                    id: 54,
                    name: "Pro",
                    price: "1,50,000",
                    mrp: "3,00,000",
                    link: "/digital-marketing/",
                    tag: "/user/yearly/billed yearly",
                    description: "Choose the right set of features you need to begin your  journey.",
                    button: "Get Started",
                    button2: "Buy now",
                    key: "key features",
                    features: [
                        {
                            "text": "One Time",
                            "tooltip": "This service is performed once for a specific result or outcome."
                        },
                        {
                            "text": "100 Accounts ",
                            "tooltip": "Applies to 100 individual accounts per category or service."
                        },
                        {
                            "text": "CRM Software",
                            "tooltip": "Applies to 100 individual accounts per category or service."
                        },
                        {
                            "text": "Traning",
                            "tooltip": "Applies to 100 individual accounts per category or service."
                        },

                    ]
                },
                {
                    id: 64,
                    name: "Elite",
                    link: "/digital-marketing/",
                    price: "2,50,000",
                    mrp: "5,00,000",
                    tag: "/user/yearly/billed yearly",
                    description: "Enjoy our advanced offering for fast-growing businesses and startups.",
                    button: "Get Started",
                    button2: "Buy now",
                    key: "key features",
                    features: [
                        {
                            "text": "One Time",
                            "tooltip": "This service is performed once for a specific result or outcome."
                        },
                        {
                            "text": "100 Accounts ",
                            "tooltip": "Applies to 100 individual accounts per category or service."
                        },
                        {
                            "text": "CRM Software",
                            "tooltip": "Applies to 100 individual accounts per category or service."
                        },
                        {
                            "text": "Traning",
                            "tooltip": "Applies to 100 individual accounts per category or service."
                        },

                    ]
                },
                {
                    id: 64,
                    name: "All",
                    price: "3,60,000",
                    mrp: "9,00,000",
                    link: "/digital-marketing/",
                    tag: "/user/yearly/billed yearly",
                    description: "Enjoy our advanced offering for fast-growing businesses and startups.",
                    button: "Get Started",
                    button2: "Buy now",
                    key: "key features",
                    features: [
                        {
                            "text": "One Time",
                            "tooltip": "This service is performed once for a specific result or outcome."
                        },
                        {
                            "text": "100 Accounts Each",
                            "tooltip": "Applies to 100 individual accounts per category or service."
                        },
                        {
                            "text": "CRM Software",
                            "tooltip": "Applies to 100 individual accounts per category or service."
                        },
                        {
                            "text": "Traning",
                            "tooltip": "Applies to 100 individual accounts per category or service."
                        },

                    ]
                }
            ]
        }
    },
    computed: {
        pricing() {
            return this.$store.getters.getPricing
        }
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
            return 0; // Default return if calculation fails
        }

    }
};
</script>

<style scoped>
.nav-link {
    transition: background-color 0.3s ease, color 0.3s ease;
}

.nav-link.active {
    background-color: var(--brand-color) !important;
    color: white !important;
    transition: background-color 0.3s ease, color 0.3s ease, transform 0.3s ease;
    /* transform: scale(1.2); */
}

.sticky-container {
    position: sticky;
    top: 70px;
    z-index: 1000;
    background-color: white;
}
</style>
