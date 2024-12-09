<template>
    <div class="top-padding" style="background-color: black;">
        <TopSectionBanner />
        <div class="container py-5">
            <div class="card text-white border-0" style="background-color: black;">
                <div class="card-header">
                    <h5 class="text-start">Please read this legal warning ("Disclaimer") carefully before using
                        Fameset’s Networking Services ("Services").</h5>
                </div>
                <div class="card-body text-start">
                    <div id="accordion">
                        <div v-for="(section, index) in sections" :key="index" class="mb-3">
                            <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center brand-bg text-white"  type="button" :data-bs-toggle="'collapse'"
                                :data-bs-target="'#collapse' + index" aria-expanded="true"
                                :aria-controls="'collapse' + index">
                                <strong>{{ index + 1 }}. {{ section.title }}</strong>
                                <i class="bi bi-chevron-down"></i>
                            </button>
                            <div :id="'collapse' + index" class="collapse show">
                                <p>{{ section.content }}</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import TopSectionBanner from "@/components/TopSectionBanner.vue";
export default {
    name: "LegalWarning",
    components: {
        TopSectionBanner,
    },
    data() {
        return {
            sections: [
                {
                    title: "Acceptance of Terms",
                    content:
                        "By accessing, browsing, or using Fameset’s Services, you confirm that you have carefully reviewed and understood the terms outlined in this Disclaimer. Your continued use of the Services constitutes your explicit acceptance of these terms. If you disagree with any of the terms, conditions, or policies stated herein, you are expressly prohibited from accessing or using the Services. It is important that all users engage with the Services in accordance with these terms to ensure a transparent, safe, and legally compliant experience.",
                },
                {
                    title: "No Warranty",
                    content:
                        "The Services are provided on an 'as is' and 'as available' basis without any warranty of any kind, either express or implied. Fameset does not guarantee that the Services will meet your specific requirements, be uninterrupted, timely, secure, or error-free. We also disclaim any implied warranties, including, but not limited to, warranties of merchantability, fitness for a particular purpose, and non-infringement of third-party rights. Users should exercise their own discretion and perform necessary due diligence when interacting with the Services.",
                },
                {
                    title: "Limitation of Liability",
                    content:
                        "Under no circumstances shall Fameset, its affiliates, employees, or agents be held liable for any direct, indirect, incidental, special, or consequential damages arising from the use or inability to use the Services. This includes, but is not limited to, loss of data, loss of profits, loss of business opportunities, or any other financial or intangible losses that may occur. Our liability is strictly limited to the fullest extent permitted by applicable law, and you hereby acknowledge and accept these limitations when using the Services.",
                },
                {
                    title: "Compliance with Laws",
                    content:
                        "As a user of the Services, you are solely responsible for ensuring that your activities comply with all relevant local, national, and international laws, regulations, and policies. Fameset is not responsible for any violations of applicable laws or any legal repercussions that arise from your use of the Services. Failure to comply with these legal obligations may result in the suspension or termination of your access to the Services and could expose you to legal action.",
                },
                {
                    title: "Intellectual Property",
                    content:
                        "All content, logos, trademarks, designs, and other intellectual property used or displayed through the Services are the exclusive property of Fameset or its licensors. Users are granted a limited, non-transferable, and non-exclusive license to access and use the Services solely for their intended purpose. Unauthorized use, copying, reproduction, or distribution of any intellectual property associated with the Services is strictly prohibited and may result in legal action.",
                },
                {
                    title: "Third-Party Services",
                    content:
                        "The Services may contain links or integrations to third-party websites, applications, or services. While we aim to provide value through these third-party connections, Fameset does not endorse or control the content, privacy practices, or terms of service of any third-party services. Any interaction with third-party services is done at your own risk, and Fameset shall not be held liable for any issues arising from such interactions.",
                },
                {
                    title: "Modification and Termination",
                    content:
                        "Fameset reserves the right to modify, suspend, or terminate the Services at its sole discretion, without prior notice or liability. This may include changes to features, functionality, or overall service availability. We encourage users to review this Disclaimer periodically for any updates, as your continued use of the Services after any changes signifies your acceptance of those changes.",
                },
                {
                    title: "Governing Law",
                    content:
                        "This Disclaimer, as well as any disputes arising from your use of the Services, shall be governed by the laws of India. Any legal action or proceedings related to the Services shall be exclusively resolved in the competent courts located in Delhi, India. This clause ensures clarity and consistency in the resolution of any legal conflicts.",
                },
                {
                    title: "Contact Information",
                    content:
                        "If you have any questions or concerns regarding this Disclaimer or our Services, please feel free to contact us using the details below:\n\nFameset\n2nd Floor, Block B1/632, Janakpuri, 110058, Delhi, India\nEmail: support@fameset.com\nPhone: +91 8802172121",
                },
            ],
        };
    },
};
</script>

<style lang="scss" scoped></style>
