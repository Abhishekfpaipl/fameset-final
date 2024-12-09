<template>
    <div class="top-padding" style="background-color: black;">
        <TopSectionBanner />
        <div class="container py-5">
            <div class="card border-0 text-white">
                <div class="card-body text-start" style="background-color: black;">
                    <div id="termsAccordion">
                        <div v-for="(section, index) in sections" :key="index" class="mb-3">
                            <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center brand-bg text-white"  type="button" :data-bs-target="'#collapse' + index"
                                data-bs-toggle="collapse" :aria-controls="'collapse' + index" aria-expanded="true">
                                <strong>{{ index + 1 }}. {{ section.title }}</strong>
                                <i class="bi bi-chevron-down"></i>
                            </button>
                            <div :id="'collapse' + index" class="collapse show">
                                <div v-if="section.content" v-html="section.content"></div>
                                <ul v-if="section.list">
                                    <li v-for="(item, i) in section.list" :key="i">{{ item }}</li>
                                </ul>
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
    name: 'TermOfUse',
    components: {
        TopSectionBanner,
    },
    data() {
        return {
            sections: [
                {
                    title: 'Introduction',
                    content: `
                        Welcome to Fameset! These Terms of Use govern your access to and use of our
                        networking services, including features such as Views, Achievements, Hearts,
                        Promotes, Reactions, Reviews, and Testimonials, available at [Website URL].
                        By using our platform, you agree to comply with these terms. If you do not
                        agree, please refrain from using our services.
                    `,
                },
                {
                    title: 'License to Use',
                    content: `
                        Fameset grants you a limited, non-exclusive, non-transferable license to use our
                        services solely for personal or professional networking purposes as provided by
                        Fameset. This license is subject to these Terms of Use and does not permit any
                        unauthorized commercial or derivative use of our platform.
                    `,
                },
                {
                    title: 'User Responsibilities',
                    list: [
                        'Provide accurate, complete, and up-to-date information when creating or maintaining an account.',
                        'Keep your account credentials confidential and notify us immediately of any unauthorized access.',
                        'Ensure your usage complies with all applicable laws, regulations, and these Terms of Use.',
                    ],
                },
                {
                    title: 'Prohibited Activities',
                    list: [
                        'Use our services for any illegal or unauthorized purpose.',
                        'Attempt to gain unauthorized access to our systems, user accounts, or networks.',
                        'Distribute harmful software, including viruses or malware, through the platform.',
                        'Conduct activities that disrupt the operation or performance of the platform.',
                    ],
                },
                {
                    title: 'Intellectual Property',
                    content: `
                        All content, features, and materials on Fameset, including but not limited to
                        Views, Achievements, Hearts, Promotes, Reactions, Reviews, and Testimonials, are
                        the intellectual property of Fameset. These assets are protected under Indian
                        and international copyright laws, and unauthorized use is strictly prohibited.
                    `,
                },
                {
                    title: 'Termination',
                    content: `
                        Fameset reserves the right to suspend or terminate your access to our platform
                        at any time, without prior notice, if you breach these Terms of Use or engage in
                        prohibited activities. Termination does not limit our rights to seek remedies
                        for violations.
                    `,
                },
                {
                    title: 'Limitation of Liability',
                    content: `
                        To the fullest extent permitted by law, Fameset disclaims liability for any
                        indirect, incidental, or consequential damages arising from your use of our
                        platform. This includes, but is not limited to, loss of data, profits, goodwill,
                        or any intangible losses.
                    `,
                },
                {
                    title: 'Changes to Terms',
                    content: `
                        These Terms of Use may be updated periodically to reflect changes in laws,
                        regulations, or our practices. Significant updates will be posted on our
                        platform, and continued use after changes signifies your agreement to the
                        revised terms.
                    `,
                },
                {
                    title: 'Governing Law',
                    content: `
                        These terms are governed by the laws of India. Any disputes arising under or in
                        connection with these Terms of Use shall be subject to the exclusive
                        jurisdiction of the courts located in Delhi, India.
                    `,
                },
                {
                    title: 'Contact Us',
                    content: `
                        If you have any questions or concerns about these Terms of Use, feel free to
                        contact us:<br>
                        <strong>Fameset</strong><br>
                        Email: <a href="mailto:support@fameset.com">support@fameset.com</a><br>
                        Phone: +91-8802172121<br>
                        Address: 2nd Floor, Block B1/632, Janakpuri, 110058, Delhi, India
                    `,
                },
            ],
        };
    },
};
</script>

<style lang="scss" scoped></style>
