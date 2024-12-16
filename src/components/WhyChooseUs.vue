<template>
    <div class="" style="background-color: black;">
        <div class="container p-3 pt-5 px-md-0 overflow-hidden">
            <h1 class="text-center text-capitalize">Lots of other features</h1>
            <h4 class="text-center text-capitalize">to manage your fame</h4>
            <div class="row d-flex justify-content-center pb-5 pt-2">
                <div class="col-lg-4 row row-cols-1 g-3 mt-0">
                    <div v-for="(service, index) in servicesLeft" :key="index" class="col" v-observe>
                        <div ref="test"
                            :class="['d-flex justify-content-start align-items-center text-white p-2', index % 2 === 0 ? 'from-right' : 'from-left']">
                            <div class="text-md-end text-start order-2 order-md-1 card-body me-md-3 ms-3 p-0">
                                <p class="fw-bold small mb-0 text-ellipsis1">{{ service.title }}</p>
                                <p class="smaller mb-0 text-ellipsis3">{{ service.description }}</p>
                            </div>
                            <div class="d-flex justify-content-center align-items-center rounded-circle overflow-hidden order-md-2 p-1 rotate brand-bg"
                                style="min-width:70px; height:70px;">
                                <i class="bi fs-2 method1" :class="service.icon"></i>
                            </div>
                        </div>
                    </div>

                </div>


                <div class="col-lg-4 p-5 mt-0 scale-0" ref="motorbikeImage">
                    <!-- <img src="/img/whychoose.svg" class="h-100 w-100 " > -->
                    <i class="bi bi-box2-heart font-img " style="color: gold !important;"></i>
                </div>


                <div class="col-lg-4 row row-cols-1 g-3 mt-0">
                    <div v-for="(service, index) in servicesRight" :key="index" class="col" v-observe>
                        <div :class="['d-flex justify-content-start align-items-center text-white p-2', index % 2 === 0 ? 'from-right' : 'from-left']" ref="test">
                            <div class="d-flex justify-content-center align-items-center rounded-circle overflow-hidden p-1 rotate brand-bg"
                                style="min-width:70px; height:70px; ">
                                <i class="bi fs-2   method1" :class="service.icon"></i>
                            </div>
                            <div class="text-start card-body ms-3 p-0">
                                <p class="fw-bold small mb-0 text-ellipsis1">{{ service.title }}</p>
                                <p class="smaller mb-0 text-ellipsis3">{{ service.description }} </p>
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
    name: "OurService",
    data() {
        return {
            "servicesLeft": [
                {
                    "id": 1,
                    "title": "Profile Picture",
                    "icon": "bi-person-circle",
                    "description": "Easily update and showcase your professional profile picture to represent yourself effectively."
                },
                {
                    "id": 2,
                    "title": "Banner Image",
                    "icon": "bi-image",
                    "description": "Enhance your visual presence with custom banner images designed for impact."
                },
                {
                    "id": 3,
                    "title": "Social Profiles",
                    "icon": "bi-people",
                    "description": "Connect all your social profiles in one place for seamless networking."
                },
                {
                    "id": 4,
                    "title": "Bank Details",
                    "icon": "bi-credit-card",
                    "description": "Securely manage and share your bank details for effortless transactions."
                },
                {
                    "id": 5,
                    "title": "Contact Details",
                    "icon": "bi-telephone",
                    "description": "Ensure easy accessibility with your up-to-date contact details."
                }
            ],
            "servicesRight": [
                {
                    "id": 1,
                    "title": "Link Websites",
                    "icon": "bi-globe",
                    "description": "Showcase your online presence with fully customized and professional websites."
                },
                {
                    "id": 2,
                    "title": "Link Multiple Files",
                    "icon": "bi-file-earmark",
                    "description": "Organize and manage multiple files efficiently in one secure location."
                },
                {
                    "id": 3,
                    "title": "Share",
                    "icon": "bi-share-fill",
                    "description": "Share your content and updates effortlessly across platforms."
                },
                {
                    "id": 4,
                    "title": "QR Code",
                    "icon": "bi-qr-code-scan",
                    "description": "Generate and use QR codes for quick and convenient access to your information."
                },
                {
                    "id": 5,
                    "title": "Account Match",
                    "icon": "bi-check-circle",
                    "description": "Find and link accounts seamlessly to optimize your online interactions."
                }
            ]

        }
    },
    mounted() {
        const image = this.$refs.motorbikeImage;
        const observer = new IntersectionObserver(
            (entries) => {
                entries.forEach((entry) => {
                    if (entry.isIntersecting) {
                        image.classList.add("scale-up");
                    }
                });
            },
            { threshold: [0.1] }
        );
        observer.observe(image);

        const columns = this.$refs.test;
        const observe = new IntersectionObserver(
            (entries) => {
                entries.forEach((entry) => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add("show");
                    }
                });
            },
            { threshold: [0.1] }
        );

        columns.forEach((col) => observe.observe(col));
    },
}
</script>
<style scoped>
.font-img {
    font-size: 240px !important;
}

@media (max-width:768px) {
    .font-img {
        font-size: 140px !important;
    }
}

/* Initial scale set to 0 */
.scale-0 {
    transform: scale(0);
    transition: transform 1.5s ease-in-out;
    /* Smooth scaling transition */
}

/* This class will be added when the image is in view */
.scale-up {
    transform: scale(1);
}

/* Initial state for columns animating from the right */
.from-right {
    opacity: 0;
    transform: translateX(80px);
    transition: opacity 1.5s ease-out, transform 1s ease-out;
}

/* Initial state for columns animating from the left */
.from-left {
    opacity: 0;
    transform: translateX(-80px);
    transition: opacity 1.5s ease-out, transform 1s ease-out;
}

/* When the element is observed and enters the viewport */
.from-right.show,
.from-left.show {
    opacity: 1;
    transform: translateX(0);
}
</style>