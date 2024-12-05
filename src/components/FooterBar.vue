<template>
    <div class="container-fluid text-white pt-3" style="background-color: black !important;">
        <div class="row">
            <div class="col-12 col-md-4 mb-3 d-flex flex-column align-items-center justify-content-start">
                <router-link to="/"
                    class="d-flex gap-2 align-items-center justify-content-center text-decoration-none text-white">
                    <img :src="img" style="width: 70px;object-fit: contain;">
                    <div class="d-flex flex-column align-items-start">
                        <span class="text-uppercase text-white fs-1 lh-1">Fameset</span>
                        <!-- <span class="text-capitalize text-white">business networking card</span> -->
                    </div>
                </router-link>
                <p class="mt-4 px-2">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Eligendi, nulla. Adipisci
                    debitis
                    assumenda
                    porro illum ipsam harum, aliquam amet ducimus non accusamus tempora incidunt cupiditate nisi</p>
            </div>

            <div class=" col-12 col-md-4 mb-3 text-center">
                <p class="mb-2 fw-bold">Contact Us</p>
                <p class="mb-2">Email : support@fameset.com</p>
                <p class="mb-2">Mob no. : 91 8860012001</p>
                <p class="mb-2">Address : 2nd Floor, Block B1/632, <br> Janakpuri, 110058, Delhi, India</p>
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
