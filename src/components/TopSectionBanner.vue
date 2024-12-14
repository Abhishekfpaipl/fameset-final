<template>
    <!-- <div class="border-bottom border-2" style="border-color: gold !important;"> -->
        <div class="containerr position-relative" style="width:100%; height:100%;">
            <!-- Images for desktop and mobile -->
            <img src="/img/setionBanner.jpg" alt="" class="d-none d-md-block"
                style="width: 100%; height: 400px; object-fit: cover;">
            <img src="/img/setionBanner.jpg" alt="" class="d-md-none" style="width: 100%; object-fit: cover;">

            <!-- Overlay -->
            <div class="overlay"></div>

            <!-- Centered Content -->
            <div class="center-content">
                <h1 class="text-capitalize method1">{{ pageName }}</h1>
            </div>
        </div>
    <!-- </div> -->
</template>

<script>
export default {
    name: 'TopSectionBanner',
    data() {
        return {
            pageName: ''
        };
    },
    mounted() {
        let pageName = this.$route.path.split('/').pop();
        this.pageName = pageName.replace(/-/g, ' ');
    },
}
</script>

<style scoped>
.position-relative {
    position: relative;
}

.overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.7);
    z-index: 1;
}

.center-content {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    z-index: 2;
    /* Ensure text is above the overlay */
}

.containerr::after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 2px;
    /* Border height */
    background: linear-gradient(90deg,
            rgba(254, 242, 159, 1) 0%,
            rgba(210, 163, 73, 1) 50%,
            rgba(254, 242, 159, 1) 100%);
}
</style>
