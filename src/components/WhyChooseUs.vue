<template>
    <div class="" style="background-color: black;">
        <div class="container p-3 pt-5 px-md-0">
            <h1 class="text-center text-capitalize">Lots of other features</h1>
            <h4 class="text-center text-capitalize">to manage your fame</h4>
            <div class="row d-flex justify-content-center pb-5 pt-2">
                <div class="col-lg-4 row row-cols-1 g-3 mt-0">
                    <div v-for="(service, index) in servicesLeft" :key="index" class="col" v-observe>
                        <div class="d-flex justify-content-start align-items-center text-white p-2">
                            <div class="text-md-end text-start order-2 order-md-1 card-body me-md-3 ms-3 p-0">
                                <p class="fw-bold small mb-0 text-ellipsis1">{{ service.title }}</p>
                                <p class="smaller mb-0 text-ellipsis3">{{ service.description }} </p>
                            </div>
                            <div class="d-flex justify-content-center align-items-center rounded-circle overflow-hidden order-md-2 p-1 rotate brand-bg"
                                style="min-width:70px; height:70px; ">
                                <i class="bi fs-2 method1" :class="service.icon"></i>
                            </div>
                        </div>
                    </div>
                </div>


                <div class="col-lg-4 overflow-hidden p-5 mt-0">
                    <!-- <img src="/img/whychoose.svg" class="h-100 w-100 of-cover"> -->
                    <i class="bi bi-box2-heart-fill font-img method1"></i>
                </div>


                <div class="col-lg-4 row row-cols-1 g-3 mt-0">
                    <div v-for="(service, index) in servicesRight" :key="index" class="col" v-observe>
                        <div class="d-flex justify-content-start align-items-center text-white p-2">
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
                    "title": "Websites",
                    "icon": "bi-globe",
                    "description": "Showcase your online presence with fully customized and professional websites."
                },
                {
                    "id": 2,
                    "title": "Multiple Files",
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
    }
}
</script>
<style scoped>
.font-img{
    font-size:240px !important;
}
@media (max-width:768px) {
    .font-img{
        font-size:140px !important;
    }
}

</style>