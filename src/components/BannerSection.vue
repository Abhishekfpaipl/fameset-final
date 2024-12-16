<template>
    <div>
        <div class="container-fluid text-white" style="background-color:black !important ;">
            <div class="row py-5" v-observe>
                <!-- Image Section -->
                <div class="col-12 col-md-6 d-flex justify-content-center align-items-center">
                    <div class="" style="width:1000px; max-width:70%">
                        <img src="/img/businessbanner.png" class="w-100">
                    </div>
                </div>
                <!-- Text and Points Section -->
                <div
                    class="col-12 col-md-6 d-flex flex-column justify-content-center align-items-md-start align-items-center">
                    <div class="text-md-start text-center mt-5 mt-md-0">
                        <p class="fs-1 fw-bold m-0 text-uppercase">fameset account</p>
                    </div>
                    <h3 class="mt-3 text-md-start text-center text-capitalize">
                        Attract and retain customers effortlessly with your fameset account
                    </h3>
                    <small class="text-md-start text-center">
                        Unlock the power of real, trusted reviews proven to drive significant revenue growth for your
                        business.
                    </small>
                    <div class="mt-3 text-center text-md-start">
                        <!-- Points with Animation -->
                        <p class="my-1" v-for="(point, index) in points" :key="index"
                            :class="index % 2 === 0 ? 'animate-from-left' : 'animate-from-right'">
                            <i class="bi bi-check2-square me-2 text-warning"></i>{{ point.title }}
                        </p>
                    </div>
                    <RouterLink to=" ">
                        <div class="btn my-4 fs-5 fw-bold text-white brand-btn text-capitalize" data-bs-toggle="modal"
                            data-bs-target="#queryModal">
                            Get started
                        </div>
                    </RouterLink>
                    <a href="#second">
                        <i class="bi bi-chevron-down fs-1 slide" style="color:var(--bg-tertiary)"></i>
                    </a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "BannerComp",
    data() {
        return {
            points: [
                { title: "Stay ahead in your market." },
                { title: "Make a good impression." },
                { title: "Maximize your business." },
                { title: "Enhance your network." },
                { title: "Boost your fame" }
            ]
        };
    },
    mounted() {
        const points = this.$el.querySelectorAll("p.my-1"); // Select all point elements
        const observer = new IntersectionObserver(
            (entries) => {
                entries.forEach((entry) => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add("show");
                    }
                });
            },
            { threshold: [0.1] }
        );

        points.forEach((point) => observer.observe(point));
    }
};
</script>

<style >
/* Animation for points coming from the left */
.animate-from-left {
    opacity: 0;
    transform: translateX(-50px);
    transition: opacity 0.8s ease-out, transform 0.8s ease-out;
}

/* Animation for points coming from the right */
.animate-from-right {
    opacity: 0;
    transform: translateX(50px);
    transition: opacity 0.8s ease-out, transform 0.8s ease-out;
}

/* Final state when points are visible */
.animate-from-left.show, .animate-from-right.show {
    opacity: 1;
    transform: translateX(0);
}

</style>