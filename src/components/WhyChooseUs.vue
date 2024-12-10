<template>
    <div class="" style="background-color: black;">
        <div class="container p-3 pt-5 px-md-0">
            <h1 class="text-center text-capitalize">Lots of other features</h1>
            <h4 class="text-center text-capitalize">to manage your fame</h4>
            <div class="row d-flex justify-content-center pb-5 pt-2">
                <div class="col-lg-4 row row-cols-1 g-3 mt-0">
                    <div v-for="(service, index) in servicesLeft" :key="index" class="col">
                        <div class="d-flex align-items-start">
                            <i class="bi fs-4 pe-4" :class="service.icon"></i>
                            <div class="d-flex flex-column text-start flex-fill">
                                <p class="fs-5 fw-b title mb-0">{{ service.title }}</p>
                                <small class="smaller fw-light mb-0">{{ service.description }}</small>
                            </div>
                        </div>
                    </div>
                </div>


                <div class="col-lg-4 overflow-hidden p-5 mt-0">
                    <img src="/img/whychoose.svg" class="h-100 w-100 of-cover">
                </div>


                <div class="col-lg-4 row row-cols-1 g-3 mt-0">
                    <div v-for="(service, index) in servicesRight" :key="index" class="col">
                        <div class="d-flex align-items-start">
                            <i class="bi fs-5 pe-4" :class="service.icon"></i>
                            <div class="d-flex flex-column text-start flex-fill">
                                <p class="fs-5 fw-b title mb-0">{{ service.title }}</p>
                                <small class="smaller fw-light mb-0">{{ service.description }}</small>
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
<style lang="">

</style>