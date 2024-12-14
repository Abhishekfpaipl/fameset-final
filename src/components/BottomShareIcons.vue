<template>
    <div>
        <!-- <div class="whatsapp rounded-circle border d-flex align-items-center justify-content-center bg-success text-white"
            @click="openWhatsapp()" style="width: 37px; height: 37px;">
            <i class="bi bi-whatsapp fs-5"></i>
        </div>

        <div class="phone rounded-circle border d-flex align-items-center justify-content-center bg-primary text-white"
            @click="openDialer()" style="width: 37px; height: 37px;">
            <i class="bi bi-telephone fs-5"></i>
        </div> -->

        <!-- <div class="query m-2 slide" data-bs-toggle="modal" data-bs-target="#queryModal">
            <img src="/img/logo.png" style="width: 50px; height: 50px;" alt=""> 
        </div> -->

        <div class="modal fade" id="queryModal" tabindex="-1" aria-labelledby="queryModalLabel" aria-hidden="true">
            <div class="modal-dialog">
                <div class="d-flex justify-content-center align-items-center">
                    <div class="rounded-circle wh-60 d-flex justify-content-center align-items-center"
                        data-bs-dismiss="modal" style="padding: 0px 6px !important;background: var(--bg-glow);">
                        <i class="bi bi-x fs-4 text-dark"></i>
                    </div>
                </div>
                <div class="modal-content">
                    <div class="modal-header d-flex justify-content-between align-items-center brand-bg">
                        <h1 class="modal-title fs-5 text-white" id="queryModalLabel">Enquiry Now</h1>
                        <div class="d-flex gap-4 align-items-center">
                            <i class="bi bi-telephone method1 fs-4" @click="openDialer()"></i>
                            <i class="bi bi-whatsapp method1 fs-4" @click="openWhatsapp()"></i>
                        </div>
                        <!-- <i class="bi bi-x fs-2 text-white" data-bs-dismiss="modal" aria-label="Close"></i> -->
                    </div>
                    <div class="modal-body brand-bg">
                        <form @submit.prevent="submitQuery()" class="row g-3 needs-validation" novalidate>
                            <div class="mb-3">
                                <input type="text" class="form-control bg-transparent text-white custom-placeholder"
                                    placeholder="Name*" v-model="name" required>
                            </div>
                            <div class="mb-3">
                                <input type="text" class="form-control bg-transparent text-white custom-placeholder"
                                    placeholder="Mobile*" v-model="number" required>
                            </div>
                            <div class="mb-3">
                                <input type="text" class="form-control bg-transparent text-white custom-placeholder"
                                    placeholder="Email*" v-model="email" required>
                            </div>
                            <div class=" mb-3">
                                <select class="p-2 w-100 rounded bg-transparent custom-select" v-model="selectedOption">
                                    <option value="" class="">I'm looking for</option>
                                    <option value="Lite (1000)">Lite (1000)</option>
                                    <option value="Pro (3000)">Pro (3000)</option>
                                    <option value="Elite (5000)">Elite (5000)</option>
                                </select>
                            </div>
                            <div class="mb-3">
                                <textarea v-model="query" rows="2"
                                    class="form-control flex-fill bg-transparent custom-placeholder"
                                    placeholder="Type your message..." required>
                                </textarea>
                            </div>
                            <div class="col-12">
                                <button class="btn w-100" type="submit"
                                    style="background: var(--bg-glow);">Submit</button>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div> 
    </div>
</template>
<script>
export default {
    data() {
        return {
            name: '',
            email: '',
            number: '',
            query: '',
            selectedOption: '',
        }
    },
    methods: {
        submitQuery() {
            console.log('Submit Query')
            const data = {
                name: this.name,
                email: this.email,
                query: this.query,
            }
            this.$store.dispatch('submitQuery', data)
        },
        openDialer() {
            const phoneNumber = 918802172121;
            window.location.href = `tel:${phoneNumber}`;
        },
        openWhatsapp() {
            window.open(`https://wa.me/${918802172121}?text=Hello...`, '_blank');
        }
    }
}
</script>
<style scoped>
.query {
    z-index: 9;
    position: fixed;
    bottom: 10%;
    right: 10px;
    padding: 5px;
    cursor: pointer;
    border-radius: 5px;
    display: flex;
    align-items: center;
}

.whatsapp {
    z-index: 9;
    position: fixed;
    bottom: 17%;
    right: 10px;
    cursor: pointer;
    padding: 5px !important
}

.phone {
    z-index: 9;
    position: fixed;
    bottom: 25%;
    right: 10px;
    cursor: pointer;
    padding: 5px
}

.custom-placeholder::placeholder {
    color: rgba(255, 255, 255, 0.7);
    /* Example: Semi-transparent white */
    font-style: italic;
    /* Optional: Styling the placeholder text */
}

.custom-select {
    background-color: transparent;
    /* Example: Semi-transparent black */
    color: white;
    /* Text color */
    border: 1px solid white;
    /* Optional: Border styling */
}

/* Style for dropdown options */
.custom-select option {
    background-color: black;
    /* Background color for dropdown options */
    color: white;
    /* Text color for options */
}
</style>