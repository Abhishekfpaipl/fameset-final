<template>
    <div class="top-padding" style="background-color: black;">
        <TopSectionBanner />
        <div class="container py-5">
            <div class="row justify-content-center">
                <div class="col-12">
                    <div class="card border-0 text-white text-start" style="background-color: black;">
                        <div id="privacyAccordion">
                            <div v-for="(section, index) in privacySections" :key="index" class="mb-3">
                                <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center brand-bg text-white"
                                    :type="'button'" data-bs-toggle="collapse" :data-bs-target="'#collapse' + index"
                                    :aria-controls="'collapse' + index" aria-expanded="true" >
                                    <strong>{{ section.title }}</strong>
                                    <i class="bi bi-chevron-down"></i>
                                </button>
                                <div :id="'collapse' + index" class="collapse show">
                                    <p v-html="section.content"></p>
                                    <ul v-if="section.list">
                                        <li v-for="(item, i) in section.list" :key="i">
                                            <strong v-if="item.strong">{{ item.strong }}:</strong>
                                            {{ item.text }}
                                        </li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import TopSectionBanner from '@/components/TopSectionBanner.vue';

export default {
    name: 'PrivacyPolicy',
    components: {
        TopSectionBanner
    },
    data() {
        return {
            privacySections: [
                {
                    title: "Introduction",
                    content: `<strong>Fameset</strong> values your privacy and is dedicated to protecting the personal information you provide.
                            This Privacy Policy explains the types of information we collect, how we use it, the conditions under which we may share it, and the measures we take to safeguard it.
                            By using our networking services and features—including Views, Achievements, Hearts, Promotes, Reactions, Reviews, and Testimonials—you agree to the practices described herein.`,
                },
                {
                    title: "1. Information We Collect",
                    content: "We collect information to provide and improve our services effectively. This includes:",
                    list: [
                        {
                            strong: "Personal Information",
                            text: "This may include your name, email address, phone number, business name, and payment details, which are required during registration or when availing of our services."
                        },
                        {
                            strong: "Usage Data",
                            text: "We gather data about how you interact with our services, such as profile views, reactions, activity logs, and engagement metrics, to enhance your experience and improve our offerings."
                        }
                    ]
                },
                {
                    title: "2. How We Use Your Information",
                    content: "We use the information collected for purposes such as:",
                    list: [
                        { text: "Providing and enhancing networking services and features, such as Testimonials and Reviews." },
                        { text: "Personalizing your experience by customizing services and recommendations." },
                        { text: "Communicating with you about service updates, inquiries, or customer support issues." },
                        { text: "Analyzing user behavior, such as Promotes and Reactions, to improve platform usability and features." },
                        { text: "Maintaining platform security and preventing fraud or unauthorized access." }
                    ]
                },
                {
                    title: "3. Sharing Your Information",
                    content: "Your information is not sold or traded. We may share it under the following circumstances:",
                    list: [
                        {
                            strong: "Trusted Service Providers",
                            text: "To support the delivery of our services, such as payment processing or data analysis, we work with reliable partners."
                        },
                        {
                            strong: "Legal Compliance",
                            text: "If required by law or to protect our rights and safety, we may disclose information to authorities or legal entities."
                        }
                    ]
                },
                {
                    title: "4. Data Security",
                    content: `We adopt robust security measures to safeguard your personal data from unauthorized access, loss, or misuse.
                            These include encryption protocols, secure server technologies, and regular security audits to ensure the integrity of our platform.`
                },
                {
                    title: "5. Your Rights",
                    content: "You have the right to manage your personal information and interactions with our platform. These include:",
                    list: [
                        { text: "Accessing and updating your personal details via account settings." },
                        { text: "Requesting deletion of your data, subject to applicable legal and technical constraints." },
                        { text: "Opting out of promotional emails while continuing to receive essential service updates." }
                    ]
                },
                {
                    title: "6. Cookies",
                    content: `Cookies and similar technologies help us enhance your browsing experience.
                            You can manage your cookie preferences through your browser settings, but disabling cookies may limit certain functionalities of the platform.`
                },
                {
                    title: "7. Changes to This Privacy Policy",
                    content: `Periodically, we may update this Privacy Policy to reflect changes in our practices or services.
                            Any significant updates will be communicated through announcements on our website or via email.`
                },
                {
                    title: "8. Contact Us",
                    content: `If you have questions or concerns about this Privacy Policy, please reach out to us:<br>
                            <strong>Fameset</strong><br>
                            Email: <a href="mailto:support@fameset.com" class="text-decoration-none text-white">support@fameset.in</a><br>
                            Phone: +91-8802172121<br>
                            Address: 2nd Floor, Block B1/632, Janakpuri, 110058, Delhi, India`
                }
            ]
        };
    }
};
</script>

<style lang="scss" scoped></style>
