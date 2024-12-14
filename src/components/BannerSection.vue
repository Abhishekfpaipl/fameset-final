<template >
    <div>
        <div class="container-fluid  text-white" style="background-color:black !important ;">
            <div class="row py-5" v-observe>
                <div class="col-12 col-md-6 d-flex justify-content-center align-items-center">
                    <div class="" style="width:1000px; max-width:70%">
                        <img src="/img/businessbanner.png" class="w-100" >
                    </div>
                </div>
                <div class="col-12 col-md-6 d-flex flex-column justify-content-center align-items-md-start align-items-center"> 
                        <div class="text-md-start text-center mt-5 mt-md-0"> 
                            <p class="fs-1 fw-bold m-0 text-uppercase">fameset account</p>
                        </div>
                        <h3 class="mt-3 text-md-start text-center text-capitalize">Attract and retain customers effortlessly with your fameset account</h3>
                        <small class="text-md-start text-center">Unlock the power of real, trusted reviews proven to drive significant revenue growth for your business.</small>
                        <div class="mt-3 text-center text-md-start">
                            <p class="my-1"><i class="bi bi-check2-square me-2 text-warning"></i> Stay ahead in your market.</p>
                            <p class="my-1"><i class="bi bi-check2-square me-2 text-warning"></i> Make a good impression.</p>
                            <p class="my-1"><i class="bi bi-check2-square me-2 text-warning"></i> Maximize your business.</p>
                            <p class="my-1"><i class="bi bi-check2-square me-2 text-warning"></i> Enhance your network.</p>
                            <p class="my-1"><i class="bi bi-check2-square me-2 text-warning"></i> Boost your fame.</p>
                        </div> 
                        <RouterLink to=" ">
                            <div class="btn my-4 fs-5 fw-bold text-white brand-btn text-capitalize" data-bs-toggle="modal"
                            data-bs-target="#queryModal">
                                Get started
                            </div>
                        </RouterLink>
                        <a href="#second" class><i class="bi bi-chevron-down fs-1 slide" style="color:var(--bg-tertiary)"></i></a> 
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'BannerComp',
}
</script>
<style lang="">

</style>