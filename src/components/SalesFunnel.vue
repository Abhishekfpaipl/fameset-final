<template>
    <div class="brandText">
        <div class="container">
            <h1 class="text-center text-capitalize mb-4">Required Steps for Account Setup</h1>
            <div class="d-flex flex-column m-auto align-items-start" style="max-width: 500px;">
                <div v-for="(lead, index) in values" :key="index" class="funnel-step"
                    :style="{ width: calculateWidth(index) }" v-observe>
                    <div class="card py-3 d-flex flex-column text-white"
                        style="background-color: black; border: 2px solid gold;">
                        <div class="image d-flex justify-content-between align-items-center">
                            <div class="d-flex gap-2 px-2"> 
                                <p class="mb-0 fw-bold">{{ values.length - index }}</p>
                                <p class="ms-2 mb-0 fw-bold">{{ lead.title }}</p>
                            </div>
                            <i class="bi bi-rewind-fill method1 me-2"></i>
                        </div>
                        <div class="content">
                            <p class="mb-0 text-white px-2">{{ lead.description }}</p>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "SalesFunnel",
    data() {
        return {
            values: [
                {
                    id: 7,
                    icon: 'bi-qr-code fs-4',
                    title: "Share",
                    color: "#5ccd5f",
                    description: "Easily share your profile or landing page via QR codes or direct links, enabling quick and seamless access for your audience.",
                },
                {
                    id: 6,
                    icon: 'bi-trophy fs-4',
                    title: "Achievements",
                    color: "#c9d825",
                    description: "Display your achievements and accolades to build trust and credibility, establishing yourself as an authority in your field.",
                },
                {
                    id: 5,
                    icon: 'bi-bar-chart-line fs-4',
                    title: "Connecting Details",
                    color: "#f8a42a",
                    description: "Enhance your customer interactions by collecting key details like emails, phone numbers, and social media handles directly from your landing page.",
                },
                {
                    id: 4,
                    icon: 'bi-image fs-4',
                    title: "Cover Banner Image",
                    color: "#f8d452",
                    description: "Design a visually engaging cover banner that represents your brand and attracts visitors to your page with the right imagery.",
                },
                {
                    id: 3,
                    icon: 'bi-person-check fs-4',
                    title: "Skill Bars & Fun Facts",
                    color: "#fbd453",
                    description: "Showcase your expertise through skill bars that highlight your abilities and share interesting facts that help engage your audience.",
                },
                {
                    id: 2,
                    icon: 'bi-file-earmark-bar-graph fs-4',
                    title: "Attributes & Basic Info",
                    color: "#f5925e",
                    description: "Provide essential information like your offerings, pricing, and contact details so your visitors can quickly understand what you offer.",
                },
                {
                    id: 1,
                    icon: 'bi-person-circle fs-4',
                    title: "Subscribe & Setup Account",
                    color: '#e76365',
                    description: "Create a compelling profile to showcase your skills and services. Customize it to match your branding and ensure a professional appearance.",
                },
            ],

        }
    },
    methods: {
        calculateWidth(index) {
            const totalSteps = this.values.length;
            const maxWidth = 100;
            const minWidth = 60;
            const stepWidth = (maxWidth - minWidth) / (totalSteps - 1);
            return `${minWidth + (stepWidth * index)}%`;
        }

    }
}
</script>

<style scoped>
.funnel-step {
    margin-bottom: 20px;
    transition: width 0.3s ease-in-out;
}

.card {
    transition: 0.3s ease-in-out;
    border-radius: 15px;
    overflow: hidden;
    position: relative;
}

.content {
    color: #111;
    text-align: center;
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.3s ease-in-out, opacity 0.3s ease-in-out;
    opacity: 0;
}

.card:hover .content {
    max-height: 300px;
    opacity: 1;
}

.image {
    transition: 0.3s ease-in-out;
}

.card:hover .image {
    transform: translateY(-10px);
}
</style>