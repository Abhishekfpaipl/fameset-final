<template>
    <div class="container-fluid brand-bg" >
        <div class="row py-5 text-white">
            <h1 class="text-center text-capitalize my-5">{{ title }}</h1>
            <div class="col">
                <div class="text-center">
                    <p class="small text-capitalize mb-0">{{ serviceAltText }}</p>
                    <p class="m-0 fs-3 fw-bold d-flex justify-content-center align-items-center">
                        <AutoCounter :data="serviceCount"> </AutoCounter>&nbsp;+
                    </p>
                    <p class="mt-0 text-capitalize smaller fw-bold">{{ service }}</p>
                </div>
            </div>
            <div class="col">
                <div class="text-center">
                    <p class="small text-capitalize mb-0">{{ categoryAltText }}</p>
                    <p class="m-0 fs-3 fw-bold d-flex justify-content-center align-items-center">
                        <AutoCounter :data="categoryCount"> </AutoCounter>&nbsp;+
                    </p>
                    <p class="mt-0 text-capitalize smaller fw-bold">{{ category }}</p>
                </div>
            </div>
            <div class="col">
                <div class="text-center">
                    <p class="small text-capitalize mb-0">{{ placeAltText }}</p>
                    <p class="m-0 fs-3 fw-bold d-flex justify-content-center align-items-center">
                        <AutoCounter :data="placeCount"> </AutoCounter>&nbsp;+
                    </p>
                    <p class="mt-0 text-capitalize smaller fw-bold">{{ place }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import AutoCounter from '@/components/AutoCounter.vue'
export default {
    name: 'CustomCounter',
    components: {
        AutoCounter
    },
    props: {
        service: { type: String, },
        category: { type: String, },
        place: { type: String, },
        serviceCount: { type: Number, },
        placeCount: { type: Number, },
        categoryCount: { type: Number, },
        image: { type: String, required: true }, // Make the image prop required
        title: { type: String, },
        icon: { type: String, },
        path: { type: String, },
        serviceAltText: { type: String, },
        placeAltText: { type: String, },
        categoryAltText: { type: String, },
    },
}
</script>
