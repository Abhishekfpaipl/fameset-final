<template>
    <div>
        <form @submit.prevent="submitQuery()" class="row g-3 needs-validation" novalidate>
            <div class="mb-3">
                <input type="text" class="form-control bg-transparent text-white custom-placeholder" placeholder="Name*"
                    v-model="name" required>
            </div>
            <div class="mb-3">
                <input type="tel" class="form-control bg-transparent text-white custom-placeholder"
                    placeholder="Mobile*" v-model="number" required>
            </div>
            <div class="mb-3">
                <input type="email" class="form-control bg-transparent text-white custom-placeholder"
                    placeholder="Email*" v-model="email" required>
            </div>
            <div class=" mb-3">
                <select class="p-2 w-100 rounded bg-transparent custom-select" v-model="selectedOption">
                    <option value="" class="">I'm looking for</option>
                    <option value="Lite (1000)">Lite (₹ 1,000)</option>
                    <option value="Pro (3000)">Pro (₹ 3,000)</option>
                    <option value="Elite (5000)">Elite (₹ 6,000)</option>
                </select>
            </div>
            <div class="mb-3">
                <textarea v-model="query" rows="2"
                    class="form-control flex-fill bg-transparent custom-placeholder text-white"
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
            // Validation: Check if all required fields are filled
            if (!this.name || !this.email || !this.number || !this.selectedOption || !this.query) {
                alert("Please fill all required fields.");
                return;
            }

            // Serialize data into a user-friendly message
            const message = `
        Hello,
        Here are my details:
        Name: ${this.name}
        Email: ${this.email}
        Mobile: ${this.number}
        Package: ${this.selectedOption}
        Query: ${this.query}
    `;

            // Encode message for URL
            const encodedMessage = encodeURIComponent(message.trim());

            // WhatsApp URL with encoded message
            const phoneNumber = "8802172121";
            const whatsappUrl = `https://wa.me/${phoneNumber}?text=${encodedMessage}`;

            // Open WhatsApp in a new tab
            window.open(whatsappUrl, "_blank");
        },
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