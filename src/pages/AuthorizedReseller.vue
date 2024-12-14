<template>
    <div class="text-white top-padding" style="background-color: black;">
        <CarouselBanner />
        <ResllerImage />
        <div class="text-center text-white py-5">
            <div class="container">
                <p class="fs-1 fw-bold mb-0 text-capitalize">Become our authorized reseller</p>
                <p class="fs-5 fw-bold text-capitalize">Partnered with us and start your own business</p>
                <p>The reselling business opportunity for digital business cards offers a unique chance to tap into the
                    growing demand for professional digital identities in today's connected world. As businesses and
                    individuals look for ways to update and modernize their professional presence, digital business
                    cards have become an essential tool. Resellers can take advantage of this trend by offering
                    customizable, shareable, and eco-friendly business cards to a wide range of potential clients.
                </p>
            </div>
        </div>
        <div class="py-5">
            <div class="sticky-nav my-4">
                <div class="d-flex gap-3 p-3 py-2 overflow-x-scroll border-top border-bottom border-secondary"
                    id="scroll" style="background-color:black !important; white-space: nowrap;">
                    <div v-for="(section, index) in sections" :key="index">
                        <a :href="'#' + section.id" class="nav-link text-white"
                            @click.prevent="scrollToSection(section.id)"
                            :class="{ active: activeSection === section.id }">
                            {{ section.name }}
                        </a>
                    </div>
                </div>
            </div>

            <div class="container">
                <section v-for="(section, index) in sections" :key="index" :id="section.id" class="section"
                    style="padding-top:30px">
                    <h1 class="text-center text-warning mb-3 text-uppercase">{{ section.name }}</h1>
                    <component :is="section.component"></component>
                </section>
            </div>
        </div>
    </div>
</template>

<script>
import BenefitSection from "@/components/BenefitSection.vue"
import ResellerProfitSection from "@/components/ResellerProfitSection.vue"
import EligibilitySection from "@/components/EligibilitySection.vue"
import SoftwareSection from '@/components/SoftwareSection.vue';
import FaqSection from "@/components/FaqSection.vue"
import ResellerAbout from "@/components/ResellerAbout.vue"
import BusinessSuccessStory from '@/components/BusinessSuccessStory.vue';
import ResllerImage from '@/components/ResllerImage.vue';
import BusinessCounter from '@/components/BusinessCounter.vue';
import BusinessSell from '@/components/BusinessSell.vue';
import HowItWorks from '@/components/HowItWorks.vue';

export default {
    name: 'CareerPage',
    components: {
        BenefitSection,
        ResellerProfitSection,
        EligibilitySection,
        SoftwareSection,
        FaqSection,
        ResellerAbout,
        BusinessSuccessStory,
        ResllerImage,
        BusinessCounter,
        BusinessSell,
        HowItWorks,
    },
    data() {
        return {
            sections: [
                { id: 'Cost', name: 'Cost', component: 'ResellerProfitSection' },
                { id: 'EligibilitySection', name: 'Eligibility', component: 'EligibilitySection' },
                { id: 'Opportunity', name: 'Opportunity', component: 'BusinessCounter' },
                { id: 'Benefits', name: 'Benefits', component: 'BenefitSection' },
                { id: 'Why Choose', name: 'Why Choose', component: 'BusinessSell' },
                { id: 'How It Works', name: 'How It Works', component: 'HowItWorks' },
                { id: 'Success Story', name: 'Success Story', component: 'BusinessSuccessStory' },
                { id: 'FAQ', name: 'FAQ', component: 'FaqSection' },
                { id: 'About', name: 'About', component: 'ResellerAbout' },
                { id: 'Software', name: 'Software', component: 'SoftwareSection' },
            ],
            activeSection: '',
        };
    },
    mounted() {
        window.addEventListener('scroll', this.handleScroll);
    },
    unmounted() {
        window.removeEventListener('scroll', this.handleScroll);
    },
    methods: {
        scrollToSection(id) {
            const el = document.getElementById(id);
            if (el) {
                window.scrollTo({
                    top: el.offsetTop - 70, // Offset to account for sticky header
                    behavior: 'smooth',
                });
            }
        },
        handleScroll() {
            const scrollPosition = window.scrollY;
            console.log(scrollPosition)
            this.sections.forEach(section => {
                const el = document.getElementById(section.id);
                if (el) {
                    const rect = el.getBoundingClientRect();
                    if (rect.top <= 150 && rect.bottom >= 150) {
                        this.activeSection = section.id;
                    }
                }
            });
        }
    }
}
</script>

<style scoped>
.nav-link {
    color: white;
    text-decoration: none;
    padding: 5px 10px;
}

.nav-link.active {
    border-bottom: 3px solid var(--brand-color); /* Thicker border for visibility */
    font-weight: 600;
    color: var(--brand-color) !important;
}

.sticky-nav {
    position: sticky;
    top: 70px !important; /* Adjusted for sticky header */
    z-index: 9;
    background-color: white;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}
</style>
