<template lang="">
    <div>
        <div class="position-relative" style="width:100%; height:100%;">
            <img src="/img/bannerDesktop.jpg" alt="" class="d-none d-md-block"
                style="width: 100%; height: 400px; object-fit: cover;">
            <img src="/img/bannerDesktop.jpg" alt="" class="d-md-none"
                style="width: 100%; object-fit: cover;">
            <!-- <img src="/img/bannerMobile.jpg" alt="" class="d-md-none"
                style="width: 100%; height: 100%; object-fit: cover;"> -->
               
                <div class="center-content">
                    <h1 class="text-capitalize method1">{{pageName}}</h1> 
                </div>
            </div> 
    </div>
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
<style>
.method1 {
    background: linear-gradient(90deg, rgba(254, 242, 159, 1) 0%, rgba(210, 163, 73, 1) 50%, rgba(254, 242, 159, 1) 100%);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
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
}
</style>