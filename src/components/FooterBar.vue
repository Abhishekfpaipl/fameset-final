<template>
    <div class="container-fluid text-white pt-3 footer-container" style="background-color: black !important;">
        <div class="row pt-3">
            <div class="col-12 col-md-4 mb-3 d-flex flex-column align-items-center justify-content-start">
                <router-link to="/"
                    class="d-flex gap-2 align-items-center justify-content-center text-decoration-none text-white">
                    <img :src="img" style="width: 70px; object-fit: contain;">
                </router-link>
                <p class="mt-2 px-2">
                    <span class="fs-2 fw-bold method1">FAMESET <br></span>
                    <span class="fs-5 fw-bold method1">Let's Charm <br></span>
                    <span class="fs-5 fw-bold method1">Your Fame</span>
                </p>
            </div>

            <div class="col-12 col-md-4 mb-3 text-center">
                <p class="mb-2 fw-bold">Contact Us</p>
                <p class="mb-2">Email: support@fameset.com</p>
                <p class="mb-2">Mob no.: 91 8802172121</p>
                <p class="mb-2">Address: 2nd Floor, Block B1/632, <br> Janakpuri, 110058, Delhi, India</p>
            </div>
            <div class="col-12 col-md-4 d-flex justify-content-around">
                <div class="mb-3 text-start">
                    <p class="mb-2 fw-bold">Company</p>
                    <div class="d-flex flex-column">
                        <router-link :to="link.link" class="text-decoration-none my-1 text-white"
                            v-for="(link, index) in company" :key="index">{{ link.name }}</router-link>
                    </div>
                </div>
                <div class="mb-3 text-start">
                    <p class="mb-2 fw-bold">Resources</p>
                    <div class="d-flex flex-column">
                        <router-link :to="link.link" class="text-decoration-none my-1 text-white"
                            v-for="(link, index) in links" :key="index">{{ link.name }}</router-link>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
export default {
    name: 'FooterBar',
    data() {
        return {
            img: '/img/logo.png',
            company: [
                {
                    id: 4,
                    name: 'Contact Us',
                    link: '/contact-us'
                },
                {
                    id: 42,
                    name: 'About Us',
                    link: '/about-us'
                },
                {
                    id: 3,
                    name: 'Authorized seller',
                    link: '/authorized-reseller'
                },
                {
                    id: 9,
                    name: 'Career',
                    link: '/career'
                },
            ],
            links: [
                {
                    id: 13,
                    name: 'Legal',
                    link: '/legal-warning'
                },
                {
                    id: 1,
                    name: 'Privacy Policy',
                    link: '/privacy-policy'
                },
                {
                    id: 1,
                    name: 'Terms Of Use',
                    link: '/term-of-use'
                },
                // {
                //     id: 3,
                //     name: 'Business',
                //     link: '/business'
                // },
            ],
        }
    },
}
</script>

<style scoped>
.footer-container {
    position: relative;
}

.footer-container::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 2px;
    /* Adjust thickness of the border */
    background: linear-gradient(90deg,
            rgba(254, 242, 159, 1) 0%,
            rgba(210, 163, 73, 1) 50%,
            rgba(254, 242, 159, 1) 100%);
    z-index: 1;
}
</style>