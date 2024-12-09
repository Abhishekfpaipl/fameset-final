<template>
    <div class="top-padding" style="background-color: black;">
        <TopSectionBanner />
        <div class="container py-5 "> 
            <div class="card border-0 text-white">
                <div class="card-body text-start" style="background-color: black;">
                    <div id="termsAccordion">
                        <!-- Introduction -->
                        <div class="mb-3">
                            <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                data-bs-target="#collapseIntro" aria-expanded="true" aria-controls="collapseIntro">
                                <strong>1. Introduction</strong>
                                <i class="bi bi-chevron-down"></i>
                            </button>
                            <div id="collapseIntro" class="collapse show">
                                <p>
                                    Welcome to Fameset! These Terms of Use govern your access to and use of our
                                    networking services, including features such as Views, Achievements, Hearts,
                                    Promotes, Reactions, Reviews, and Testimonials, available at [Website URL].
                                    By using our platform, you agree to comply with these terms. If you do not
                                    agree, please refrain from using our services.
                                </p>
                            </div>
                        </div>

                        <!-- License to Use -->
                        <div class="mb-3">
                            <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                data-bs-target="#collapseLicense" aria-expanded="true" aria-controls="collapseLicense">
                                <strong>2. License to Use</strong>
                                <i class="bi bi-chevron-down"></i>
                            </button>
                            <div id="collapseLicense" class="collapse show">
                                <p>
                                    Fameset grants you a limited, non-exclusive, non-transferable license to use our
                                    services solely for personal or professional networking purposes as provided by
                                    Fameset. This license is subject to these Terms of Use and does not permit any
                                    unauthorized commercial or derivative use of our platform.
                                </p>
                            </div>
                        </div>

                        <!-- User Responsibilities -->
                        <div class="mb-3">
                            <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                data-bs-target="#collapseResponsibilities" aria-expanded="true"
                                aria-controls="collapseResponsibilities">
                                <strong>3. User Responsibilities</strong>
                                <i class="bi bi-chevron-down"></i>
                            </button>
                            <div id="collapseResponsibilities" class="collapse show">
                                <p>As a user of Fameset, you agree to adhere to the following responsibilities:</p>
                                <ul>
                                    <li>Provide accurate, complete, and up-to-date information when creating or
                                        maintaining an account.</li>
                                    <li>Keep your account credentials confidential and notify us immediately of any
                                        unauthorized access.</li>
                                    <li>Ensure your usage complies with all applicable laws, regulations, and these
                                        Terms of Use.</li>
                                </ul>
                            </div>
                        </div>

                        <!-- Prohibited Activities -->
                        <div class="mb-3">
                            <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                data-bs-target="#collapseProhibited" aria-expanded="true"
                                aria-controls="collapseProhibited">
                                <strong>4. Prohibited Activities</strong>
                                <i class="bi bi-chevron-down"></i>
                            </button>
                            <div id="collapseProhibited" class="collapse show">
                                <p>To maintain the integrity of our platform, you must not engage in the following
                                    activities:</p>
                                <ul>
                                    <li>Use our services for any illegal or unauthorized purpose.</li>
                                    <li>Attempt to gain unauthorized access to our systems, user accounts, or
                                        networks.</li>
                                    <li>Distribute harmful software, including viruses or malware, through the
                                        platform.</li>
                                    <li>Conduct activities that disrupt the operation or performance of the
                                        platform.</li>
                                </ul>
                            </div>
                        </div>

                        <!-- Intellectual Property -->
                        <div class="mb-3">
                            <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                data-bs-target="#collapseIP" aria-expanded="true" aria-controls="collapseIP">
                                <strong>5. Intellectual Property</strong>
                                <i class="bi bi-chevron-down"></i>
                            </button>
                            <div id="collapseIP" class="collapse show">
                                <p>
                                    All content, features, and materials on Fameset, including but not limited to
                                    Views, Achievements, Hearts, Promotes, Reactions, Reviews, and Testimonials, are
                                    the intellectual property of Fameset. These assets are protected under Indian
                                    and international copyright laws, and unauthorized use is strictly prohibited.
                                </p>
                            </div>
                        </div>

                        <!-- Termination -->
                        <div class="mb-3">
                            <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                data-bs-target="#collapseTermination" aria-expanded="true"
                                aria-controls="collapseTermination">
                                <strong>6. Termination</strong>
                                <i class="bi bi-chevron-down"></i>
                            </button>
                            <div id="collapseTermination" class="collapse show">
                                <p>
                                    Fameset reserves the right to suspend or terminate your access to our platform
                                    at any time, without prior notice, if you breach these Terms of Use or engage in
                                    prohibited activities. Termination does not limit our rights to seek remedies
                                    for violations.
                                </p>
                            </div>
                        </div>

                        <!-- Limitation of Liability -->
                        <div class="mb-3">
                            <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                data-bs-target="#collapseLiability" aria-expanded="true"
                                aria-controls="collapseLiability">
                                <strong>7. Limitation of Liability</strong>
                                <i class="bi bi-chevron-down"></i>
                            </button>
                            <div id="collapseLiability" class="collapse show">
                                <p>
                                    To the fullest extent permitted by law, Fameset disclaims liability for any
                                    indirect, incidental, or consequential damages arising from your use of our
                                    platform. This includes, but is not limited to, loss of data, profits, goodwill,
                                    or any intangible losses.
                                </p>
                            </div>
                        </div>

                        <!-- Changes to Terms -->
                        <div class="mb-3">
                            <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                data-bs-target="#collapseChanges" aria-expanded="true" aria-controls="collapseChanges">
                                <strong>8. Changes to Terms</strong>
                                <i class="bi bi-chevron-down"></i>
                            </button>
                            <div id="collapseChanges" class="collapse show">
                                <p>
                                    These Terms of Use may be updated periodically to reflect changes in laws,
                                    regulations, or our practices. Significant updates will be posted on our
                                    platform, and continued use after changes signifies your agreement to the
                                    revised terms.
                                </p>
                            </div>
                        </div>

                        <!-- Governing Law -->
                        <div class="mb-3">
                            <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                data-bs-target="#collapseLaw" aria-expanded="true" aria-controls="collapseLaw">
                                <strong>9. Governing Law</strong>
                                <i class="bi bi-chevron-down"></i>
                            </button>
                            <div id="collapseLaw" class="collapse show">
                                <p>
                                    These terms are governed by the laws of India. Any disputes arising under or in
                                    connection with these Terms of Use shall be subject to the exclusive
                                    jurisdiction of the courts located in Delhi, India.
                                </p>
                            </div>
                        </div>

                        <!-- Contact Us -->
                        <div class="mb-3">
                            <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                data-bs-target="#collapseContact" aria-expanded="true" aria-controls="collapseContact">
                                <strong>10. Contact Us</strong>
                                <i class="bi bi-chevron-down"></i>
                            </button>
                            <div id="collapseContact" class="collapse show">
                                <p>
                                    If you have any questions or concerns about these Terms of Use, feel free to
                                    contact us:<br>
                                    <strong>Fameset</strong><br>
                                    Email: <a href="mailto:support@fameset.com">support@fameset.com</a><br>
                                    Phone: +91-8802172121<br>
                                    Address: 2nd Floor, Block B1/632, Janakpuri, 110058, Delhi, India
                                </p>
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
        TopSectionBanner
    },
    data() {
        return {

        }
    },

}
</script>

<style lang="scss" scoped></style>