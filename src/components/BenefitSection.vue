<template>
    <div class="container px-3 px-md-0">
        <div class="row d-flex justify-content-center pb-5 pt-2">
            <div class="col-lg-4 row row-cols-1 g-3 mt-0">
                <div v-for="(service, index) in servicesLeft" :key="index" class="col" v-observe>
                    <div class="d-flex align-items-start">
                        <i class="bi fs-4 pe-4" :class="service.icon"></i>
                        <div class="d-flex flex-column text-start flex-fill">
                            <p class="fs-5 fw-b title mb-0">{{ service.heading }}</p>
                            <small class="smaller fw-light mb-0">{{ service.description }}</small>
                        </div>
                    </div>
                </div>
            </div>


            <div class="col-lg-4 overflow-hidden p-5 mt-0">
                <img src="/img/benefit.svg" class="h-100 w-100 of-cover">
            </div>


            <div class="col-lg-4 row row-cols-1 g-3 mt-0">
                <div v-for="(service, index) in servicesRight" :key="index" class="col" v-observe>
                    <div class="d-flex align-items-start">
                        <i class="bi fs-5 pe-4" :class="service.icon"></i>
                        <div class="d-flex flex-column text-start flex-fill">
                            <p class="fs-5 fw-b title mb-0">{{ service.heading }}</p>
                            <small class="smaller fw-light mb-0">{{ service.description }}</small>
                        </div>
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
            works: [

            ],
            servicesLeft: [
                {
                    icon: 'bi bi-shop fs-3',
                    heading: 'Low Startup Cost',
                    description: "Starting a Fameset service requires minimal upfront investment. Without the need for physical products or shipping logistics, your main expenses are focused on marketing and customer acquisition."
                },
                {
                    icon: 'bi bi-currency-rupee fs-3',
                    heading: "Eco-Friendly",
                    description: "Famesets are an eco-friendly solution, reducing the need for paper and printing. By offering digital cards, you help minimize waste and support sustainable business practices."
                },
                {
                    icon: 'bi bi-headset fs-3',
                    heading: "High Demand",
                    description: "As the world shifts toward digital networking, the demand for Famesets is growing. Offering these cards positions your business to serve a rapidly expanding market."
                },
                {
                    icon: 'bi bi-diagram-2 fs-3',
                    heading: "Recurring Revenue Model",
                    description: "Many Fameset services offer subscription-based pricing, allowing you to earn recurring revenue from clients who renew their cards on an annual or monthly basis."
                }
            ],
            servicesRight: [
                {
                    icon: 'bi bi-bar-chart-line fs-3',
                    heading: "Customizable Solutions",
                    description: "Famesets offer extensive customization options, including logos, color schemes, QR codes, social media links, and personalized contact information, ensuring a unique card for every client."
                },
                {
                    icon: 'bi bi-lock fs-3',
                    heading: "Scalable Business",
                    description: "Reselling Famesets allows for easy scalability. With no need for inventory management, your focus is on expanding your customer base and increasing your service offerings."
                },
                {
                    icon: 'bi bi-phone fs-3',
                    heading: "Remote Business",
                    description: "Fameset reselling business can be managed remotely. Whether from home or on the go, all you need is a computer and an internet connection to manage your business."
                }
            ]

        }
    },
}

</script>