<template>
    <div class=" top-padding" style="background-color: black;">
        <TopSectionBanner />
        <div class="container py-5">
            <div class="row justify-content-center">
                <div class="col-12">
                    <div class="card border-0 text-white text-start" style="background-color: black;">
                        <div id="privacyAccordion">
                            <!-- Introduction -->
                            <div class="mb-3">
                                <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                    type="button" data-bs-toggle="collapse" data-bs-target="#collapseIntro"
                                    aria-expanded="true" aria-controls="collapseIntro"
                                    style="background: var(--bg-glow);">
                                    <strong>Introduction</strong>
                                    <i class="bi bi-chevron-down"></i>
                                </button>
                                <div id="collapseIntro" class="collapse show">
                                    <p>
                                        <strong>Fameset</strong> values your privacy and is dedicated to
                                        protecting the personal information you provide.
                                        This Privacy Policy explains the types of information we collect, how we
                                        use it, the conditions under which we may share it, and the measures we
                                        take to safeguard it.
                                        By using our networking services and features—including Views,
                                        Achievements, Hearts, Promotes, Reactions, Reviews, and Testimonials—you
                                        agree to the practices described herein.
                                    </p>
                                </div>
                            </div>

                            <!-- Information We Collect -->
                            <div class="mb-3">
                                <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                    style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                    data-bs-target="#collapseCollect" aria-expanded="true"
                                    aria-controls="collapseCollect">
                                    <strong>1. Information We Collect</strong>
                                    <i class="bi bi-chevron-down"></i>
                                </button>
                                <div id="collapseCollect" class="collapse show">
                                    <p>We collect information to provide and improve our services effectively.
                                        This includes:</p>
                                    <ul>
                                        <li>
                                            <strong>Personal Information:</strong> This may include your name,
                                            email address, phone number, business name, and payment details,
                                            which are required during registration or when availing of our
                                            services.
                                        </li>
                                        <li>
                                            <strong>Usage Data:</strong> We gather data about how you interact
                                            with our services, such as profile views, reactions, activity logs,
                                            and engagement metrics, to enhance your experience and improve our
                                            offerings.
                                        </li>
                                    </ul>
                                </div>
                            </div>

                            <!-- How We Use Your Information -->
                            <div class="mb-3">
                                <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                    style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                    data-bs-target="#collapseUse" aria-expanded="true" aria-controls="collapseUse">
                                    <strong>2. How We Use Your Information</strong>
                                    <i class="bi bi-chevron-down"></i>
                                </button>
                                <div id="collapseUse" class="collapse show">
                                    <p>We use the information collected for purposes such as:</p>
                                    <ul>
                                        <li>Providing and enhancing networking services and features, such as
                                            Testimonials and Reviews.</li>
                                        <li>Personalizing your experience by customizing services and
                                            recommendations.</li>
                                        <li>Communicating with you about service updates, inquiries, or customer
                                            support issues.</li>
                                        <li>Analyzing user behavior, such as Promotes and Reactions, to improve
                                            platform usability and features.</li>
                                        <li>Maintaining platform security and preventing fraud or unauthorized
                                            access.</li>
                                    </ul>
                                </div>
                            </div>

                            <!-- Sharing Your Information -->
                            <div class="mb-3">
                                <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                    style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                    data-bs-target="#collapseShare" aria-expanded="true" aria-controls="collapseShare">
                                    <strong>3. Sharing Your Information</strong>
                                    <i class="bi bi-chevron-down"></i>
                                </button>
                                <div id="collapseShare" class="collapse show">
                                    <p>Your information is not sold or traded. We may share it under the
                                        following circumstances:</p>
                                    <ul>
                                        <li>
                                            <strong>Trusted Service Providers:</strong> To support the delivery
                                            of our services, such as payment processing or data analysis, we
                                            work with reliable partners.
                                        </li>
                                        <li>
                                            <strong>Legal Compliance:</strong> If required by law or to protect
                                            our rights and safety, we may disclose information to authorities or
                                            legal entities.
                                        </li>
                                    </ul>
                                </div>
                            </div>

                            <!-- Data Security -->
                            <div class="mb-3">
                                <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                    style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                    data-bs-target="#collapseSecurity" aria-expanded="true"
                                    aria-controls="collapseSecurity">
                                    <strong>4. Data Security</strong>
                                    <i class="bi bi-chevron-down"></i>
                                </button>
                                <div id="collapseSecurity" class="collapse show">
                                    <p>
                                        We adopt robust security measures to safeguard your personal data from
                                        unauthorized access, loss, or misuse.
                                        These include encryption protocols, secure server technologies, and
                                        regular security audits to ensure the integrity of our platform.
                                    </p>
                                </div>
                            </div>

                            <!-- Your Rights -->
                            <div class="mb-3">
                                <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                    style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                    data-bs-target="#collapseRights" aria-expanded="true"
                                    aria-controls="collapseRights">
                                    <strong>5. Your Rights</strong>
                                    <i class="bi bi-chevron-down"></i>
                                </button>
                                <div id="collapseRights" class="collapse show">
                                    <p>You have the right to manage your personal information and interactions
                                        with our platform. These include:</p>
                                    <ul>
                                        <li>Accessing and updating your personal details via account settings.
                                        </li>
                                        <li>Requesting deletion of your data, subject to applicable legal and
                                            technical constraints.</li>
                                        <li>Opting out of promotional emails while continuing to receive
                                            essential service updates.</li>
                                    </ul>
                                </div>
                            </div>

                            <!-- Cookies -->
                            <div class="mb-3">
                                <button class="btn mb-2 w-100 d-flex justify-content-between align-items-center"
                                    style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                    data-bs-target="#collapseCookies" aria-expanded="true"
                                    aria-controls="collapseCookies">
                                    <strong>6. Cookies</strong>
                                    <i class="bi bi-chevron-down"></i>
                                </button>
                                <div id="collapseCookies" class="collapse show">
                                    <p>
                                        Cookies and similar technologies help us enhance your browsing
                                        experience.
                                        You can manage your cookie preferences through your browser settings,
                                        but disabling cookies may limit certain functionalities of the platform.
                                    </p>
                                </div>
                            </div>

                            <!-- Changes to This Privacy Policy -->
                            <div class="mb-3">
                                <button class="btn w-100 mb-2 d-flex justify-content-between align-items-center"
                                    style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                    data-bs-target="#collapseChanges" aria-expanded="true"
                                    aria-controls="collapseChanges">
                                    <strong>7. Changes to This Privacy Policy</strong>
                                    <i class="bi bi-chevron-down"></i>
                                </button>
                                <div id="collapseChanges" class="collapse show">
                                    <p>
                                        Periodically, we may update this Privacy Policy to reflect changes in
                                        our practices or services.
                                        Any significant updates will be communicated through announcements on
                                        our website or via email.
                                    </p>
                                </div>
                            </div>

                            <!-- Contact Us -->
                            <div class="mb-3">
                                <button class="btn w-100 mb-2 d-flex justify-content-between align-items-center"
                                    style="background: var(--bg-glow);" type="button" data-bs-toggle="collapse"
                                    data-bs-target="#collapseContact" aria-expanded="true"
                                    aria-controls="collapseContact">
                                    <strong>8. Contact Us</strong>
                                    <i class="bi bi-chevron-down"></i>
                                </button>
                                <div id="collapseContact" class="collapse show">
                                    <p>
                                        If you have questions or concerns about this Privacy Policy, please
                                        reach out to us:<br>
                                        <strong>Fameset</strong><br>
                                        Email: <a href="mailto:support@fameset.com">support@fameset.in</a><br>
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

        }
    },

}
</script>

<style lang="scss" scoped></style>