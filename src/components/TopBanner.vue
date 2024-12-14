<template>
    <div>
        <div class="position-relative" style="width:100%; height:90vh ; object-fit: cover;">
            <img src="/img/deskbg.jpg" alt="" style="width: 100%; height: 100%; object-fit: cover;">
            <div class="center-content">
                <h1 class="text-capitalize method1">
                    <span class="fw-bold text-uppercase">Let's Charm</span> <br> Your Fame with<br><span
                        class="fw-bold text-uppercase">Fameset</span><br>
                </h1>
                <button class="btn text-dark fw-bold" data-bs-toggle="modal"
                data-bs-target="#queryModal" style="background: var(--bg-glow)">Get
                    Started</button>
            </div>
        </div>
    </div>
</template>
<script>
export default {

}
</script>
<style scoped>
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