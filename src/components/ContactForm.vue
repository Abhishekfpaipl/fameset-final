<template>
    <div>
        <form @submit.prevent="submitQuery()" class="row g-3 needs-validation" novalidate>
            <div class="mb-3">
                <input type="text" class="form-control bg-transparent text-white custom-placeholder" placeholder="Name*"
                    v-model="name" required>
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
                <select class="form-select bg-transparent custom-select" v-model="selectedOption">
                    <option value="" class="">I'm looking for</option>
                    <option value="Lite (1000)">Lite (1000)</option>
                    <option value="Pro (3000)">Pro (3000)</option>
                    <option value="Elite (5000)">Elite (5000)</option>
                </select>
            </div>
            <div class="mb-3">
                <textarea v-model="query" rows="2" class="form-control flex-fill bg-transparent custom-placeholder"
                    placeholder="Type your message..." required>
                                </textarea>
            </div>
            <div class="col-12">
                <button class="btn w-100" type="submit" style="background: var(--bg-glow);">Submit</button>
            </div>
        </form>
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
        };
    },
    methods: {
        submitQuery() {
            if (this.name != "" && this.service != "" && this.notes != "") {
                const phoneNumber = '918802172121'; // Replace with your WhatsApp number
                const message = `Hello, my name is ${this.name}. I need the following services: ${this.service}. Here are some additional notes: ${this.note}.`;
                const whatsappUrl = `https://api.whatsapp.com/send?phone=${phoneNumber}&text=${encodeURIComponent(message)}`;
                window.open(whatsappUrl, '_blank');
                this.name = "",
                    this.service = "",
                    this.note = "";
            }
        }
    }
}
</script>
<style scoped>
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