<template>
    <div class="container rounded-top-5" style="background-color: black !important">
        <ul class="nav nav-pills justify-content-start align-items-center" id="pills-tab" role="tablist">
            <div class="d-flex overflow-x-scroll gap-3 my-3 p-2 px-3 rounded" id="scroll">
                <li class="nav-item border border-secondary rounded" role="presentation" v-for="(price, index) in faqs"
                    :key="index">
                    <button class="nav-link text-white bg-dark " style="white-space: nowrap"
                        :class="{ 'active': index === activeTabIndex }" :id="'tab-' + index" data-bs-toggle="pill"
                        :data-bs-target="'#content-' + index" type="button" role="tab"
                        :aria-controls="'content-' + index" :aria-selected="index === activeTabIndex"
                        @click="onTabClick(index)">{{
                            price.name
                        }}</button>
                </li>
            </div>
        </ul>

        <div class="tab-content" id="pills-tabContent">
            <div class="d-flex align-items-center shadow p-2 mb-3">
                <div class="input-group  mb-3">
                    <input type="search" class="form-control border-secondary text-dark" id="floatingInput"
                        v-model="searchTerm" @keyup.enter="search" ref="searchInput" placeholder="Search here...">
                    <span class="input-group-text border-secondary"
                        style="color:#FFF5DD !important; background-color: black !important" id="basic-addon1"> <i
                            class="bi bi-search me-2" @click="search"></i> Search</span>
                </div>
            </div>
            <div class="tab-pane fade" :class="{ 'show active': index === activeTabIndex }"
                v-for="(price, index) in faqs" :key="index" :id="'content-' + index" role="tabpanel"
                :aria-labelledby="'tab-' + index" tabindex="0">
                <div class="row">
                    <div class="col-12" v-for="(faq, index) in filteredFaqs(price.plans)" :key="index"  v-observe>
                        <div class="accordion accordion-flush" id="accordionFlushExample">
                            <div class="accordion-item my-2 border-0">
                                <h2 class="accordion-header border border-secondary">
                                    <button
                                        class="accordion-button collapsed brand-bg text-white border-start border-4 "
                                        type="button" data-bs-toggle="collapse"
                                        :data-bs-target="'#flush-collapseOne' + index" aria-expanded="false"
                                        :aria-controls="'flush-collapseOne' + index"
                                        style="border-color: var(--brand-color) !important;">
                                        <span class="me-2">Q{{ index + 1 }}.</span> {{ faq.question }}
                                    </button>
                                </h2>
                                <div :id="'flush-collapseOne' + index"
                                    class="accordion-collapse collapse border-0  text-dark"
                                    data-bs-parent="#accordionFlushExample" style="background-color: gold !important">
                                    <div class="accordion-body text-start">{{ faq.answer }}</div>
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
export default {
    name: "PriceSection",
    data() {
        return {
            searchTerm: '',
            activeTabIndex: 0,
            faqs: [
                {
                    id: 109,
                    name: "All",
                    plans: [
                        {
                            "question": "What is a Fameset account?",
                            "answer": "A Fameset account is a personalized digital profile that serves as an advanced version of a business card. It includes essential information such as your name, contact details, job title, social media links, and can be further customized with branding, reviews, testimonials, achievements, skill bars, and more. It can be shared via smartphones, email, or social media."
                        },
                        {
                            "question": "How does the reseller program work?",
                            "answer": "As a reseller, you partner with a Fameset account provider to sell their services, which include features like reviews, hearts, testimonials, achievements, and skill bars. You earn a profit by marking up the pricing for the digital cards you sell. Many reseller programs offer customizable plans for individuals or businesses to integrate these features into their offerings."
                        },
                        {
                            "question": "How do I customize the Fameset accounts?",
                            "answer": "Fameset accounts can be customized with your clients' branding and include additional features like skill bars to showcase expertise, achievements, testimonials, and hearts for social proof. You can also personalize the layout, color scheme, and add interactive features such as contact forms and social media links."
                        },
                        {
                            "question": "Is there a subscription fee?",
                            "answer": "Yes, most Fameset account services operate on a subscription model where users pay annually or monthly to maintain their digital profiles. Subscription fees cover access to features like skill bars, testimonials, reviews, and achievements, and you will receive a commission for each new customer and renewal."
                        },
                        {
                            "question": "Do I need a technical background to sell Fameset accounts?",
                            "answer": "No, you don't need a technical background. Most platforms offering Fameset accounts provide easy-to-use interfaces for customizing and managing these digital profiles. Your focus will be on marketing, customer support, and helping clients leverage features like reviews, testimonials, skill bars, and achievements."
                        },
                        {
                            "question": "Can I resell to both individuals and businesses?",
                            "answer": "Yes, Fameset accounts are suitable for both individuals and businesses. You can sell these accounts to professionals looking to showcase their skills and achievements, as well as businesses wanting to enhance their branding with features like testimonials, timelines, and reviews."
                        },
                        {
                            "question": "Do I need to create my own website to sell Fameset accounts?",
                            "answer": "While having a website can boost your credibility, it’s not a requirement. Many reseller programs provide ready-to-use marketing materials, landing pages, and tools that can help you promote and sell Fameset accounts, including features like testimonials, reviews, and skill bars."
                        },
                        {
                            "question": "What support will I get as a reseller?",
                            "answer": "As a reseller, you’ll receive training, sales tools, marketing materials, and dedicated customer support. You'll get assistance in helping your clients utilize features like hearts, reviews, and timelines, and support with any questions or troubleshooting that arise."
                        },
                        {
                            "question": "How much profit can I make as a reseller?",
                            "answer": "Your profit depends on the Fameset account pricing model and the volume of sales you generate. Typically, resellers earn a commission on each sale and renewal, and as you expand your customer base and offer additional features like testimonials and achievements, your profits can increase."
                        },
                        {
                            "question": "Do I need to keep stock or inventory?",
                            "answer": "No, as a digital card reseller, there’s no need for stock or inventory. All services are cloud-based, and your customers will receive their Fameset accounts online, which can include dynamic features like skill bars, reviews, achievements, and more."
                        }
                    ]

                },
                {
                    name: "Benefits",
                    plans: [
                        {
                            question: "What are the main benefits of starting a Fameset account service?",
                            answer: "Starting a Fameset account service comes with low startup costs, eco-friendly practices, and the ability to tap into a high-demand market. It also allows you to earn recurring revenue through subscription-based pricing."
                        },
                        {
                            question: "How much investment is required to start a Fameset account service?",
                            answer: "The investment required is minimal since there are no physical products or shipping logistics involved. Most of your expenses will focus on marketing and acquiring customers."
                        },
                        {
                            question: "Why is a Fameset account service considered eco-friendly?",
                            answer: "Fameset accounts are entirely digital, reducing the need for paper and printing. By offering these services, you contribute to minimizing waste and supporting sustainable business practices."
                        },
                        {
                            question: "Is there a growing demand for Fameset accounts?",
                            answer: "Yes, as the world shifts toward digital networking, the demand for Fameset accounts is rapidly increasing. This positions your business to serve a growing market."
                        },
                        {
                            question: "How does a Fameset account service generate recurring revenue?",
                            answer: "Many Fameset services operate on a subscription-based model, where clients renew their accounts annually or monthly. This ensures a steady flow of recurring income for your business."
                        },
                        {
                            question: "Can Fameset accounts be customized for clients?",
                            answer: "Absolutely! Fameset accounts can include extensive customization options, such as logos, color schemes, QR codes, social media links, and personalized contact information, ensuring a unique and tailored experience for each client."
                        },
                        {
                            question: "Is a Fameset account reselling business scalable?",
                            answer: "Yes, it is highly scalable. Since there's no inventory to manage, you can focus on growing your customer base and expanding your service offerings to increase revenue."
                        },
                        {
                            question: "Can I manage a Fameset account business remotely?",
                            answer: "Yes, a Fameset account reselling business is highly flexible and can be managed remotely. All you need is a computer and an internet connection to operate your business from anywhere."
                        }
                    ]
                },
                {
                    name: "How it works",
                    plans: [
                        {
                            question: "How do I create a Fameset account?",
                            answer: "Creating a Fameset account is simple. You need to sign up by providing basic personal or business information and bank account details for payouts."
                        },
                        {
                            question: "Can I customize my Fameset account offerings?",
                            answer: "Yes, you can customize your Fameset offerings with features like contact details, social media links, branding, and more. This ensures a unique experience tailored to your needs."
                        },
                        {
                            question: "How do I start receiving orders for my Fameset services?",
                            answer: "Once your Fameset is set up, clients can place orders for personalized solutions that enhance their networking and branding. Promote your services to attract clients."
                        },
                        {
                            question: "How can I share my Fameset account with others?",
                            answer: "Famesets are easy to share via QR codes, direct links, or through social media. This helps increase visibility and reach."
                        },
                        {
                            question: "How will I receive payments for my Fameset services?",
                            answer: "Payments are processed seamlessly, and payouts are directly deposited into your bank account within the agreed payment cycle."
                        }
                    ]
                },
                {
                    name: "Eligibility",
                    plans: [
                        {
                            question: "What is KYC, and why is it required?",
                            answer: "KYC (Know Your Customer) is a verification process that confirms your identity and ensures compliance with financial and regulatory requirements. It is required to prevent fraud, money laundering, and other illicit activities."
                        },
                        {
                            question: "Who is eligible to complete KYC?",
                            answer: "Individuals and businesses who want to access certain financial services or platforms, such as receiving payouts, are eligible to complete KYC. Eligibility may vary depending on the service provider's requirements."
                        },
                        {
                            question: "What documents are needed for KYC verification?",
                            answer: "Typically, you will need a government-issued ID (such as a passport, driver’s license, or national ID card) and proof of address (like a utility bill or bank statement). Businesses may need to provide registration certificates and tax-related documents."
                        },
                        {
                            question: "How long does the KYC process take?",
                            answer: "The KYC process usually takes 24 to 48 hours, depending on the accuracy and completeness of the documents submitted. Some platforms offer instant verification through automated systems."
                        },
                        {
                            question: "What happens if my KYC verification fails?",
                            answer: "If your KYC verification fails, you will typically receive a notification explaining the reason. You may need to resubmit the required documents or correct any errors to complete the process."
                        },
                        {
                            question: "Is KYC mandatory for all users?",
                            answer: "Yes, KYC is mandatory for users who want to access services like financial transactions, withdrawals, or payouts. It ensures compliance with legal and regulatory standards."
                        },
                        {
                            question: "Is my data safe during the KYC process?",
                            answer: "Yes, reputable platforms use secure systems to protect your data during the KYC process. Ensure that you provide your information only to trusted and verified service providers."
                        }
                    ]
                },
                {
                    name: "Software",
                    plans: [
                        {
                            question: "What is a sales funnel landing page?",
                            answer: "A sales funnel landing page helps you connect with customers using our contact form and allows you to sync their data with your preferred CRM for seamless follow-up."
                        },
                        {
                            question: "How does lead capture automation work?",
                            answer: "Lead capture automation gathers leads from various sources like websites, Facebook, Google, lead providers, and referrals onto one platform, ensuring zero data leakage."
                        },
                        {
                            question: "What is lead distribution, and how does it help my team?",
                            answer: "Lead distribution allows you to easily track and allocate leads between your teams based on dynamic criteria like requirements, geography, or lead type."
                        },
                        {
                            question: "How can sales automation improve my sales process?",
                            answer: "Sales automation streamlines communication with leads across various channels and automates repetitive sales tasks, saving time and increasing efficiency."
                        },
                        {
                            question: "What is Direct Call Integration?",
                            answer: "Direct Call Integration enables you to call prospects with a single click. It also allows you to track and record conversations, ensuring high compliance and improved productivity."
                        },
                        {
                            question: "What features does WhatsApp Call Integration offer?",
                            answer: "WhatsApp Call Integration lets you call prospects instantly, track conversations, and maintain compliance while ensuring smooth communication."
                        },
                        {
                            question: "What kind of real-time reports are available?",
                            answer: "You can access over 135+ real-time reports that help measure various metrics, such as campaign spending, sales closure rates, and team performance."
                        },
                        {
                            question: "How can I import leads into the system?",
                            answer: "You can easily import leads into the platform using tools like Excel or CSV uploads. This ensures seamless integration of data from other sources into your CRM."
                        },
                        {
                            question: "Is it possible to export leads from the system?",
                            answer: "Yes, you can export leads from the CRM to external systems or files for analysis or reporting purposes. The process is straightforward and efficient."
                        },
                        {
                            question: "What is leads auto-qualification?",
                            answer: "Leads auto-qualification automatically categorizes leads based on parameters such as region, behavior, and engagement, helping you focus on high-potential prospects."
                        },
                        {
                            question: "Can I add custom details to CRM records?",
                            answer: "Yes, you can add notes, labels, or other documents to CRM records to ensure all relevant information is captured and easily accessible."
                        },
                        {
                            question: "How does activity automation help my team?",
                            answer: "Activity automation allows you to create workflows for tasks like follow-ups and notifications, ensuring faster, error-free communication and service delivery."
                        },
                        {
                            question: "What are the user management capabilities?",
                            answer: "The system enables you to invite team members, upload user data via Excel/CSV, or connect with Microsoft 365 or Google Workspace for streamlined user management."
                        },
                        {
                            question: "How can I stay updated about CRM activities?",
                            answer: "You can receive real-time notifications about CRM activities across all your devices, ensuring you stay informed and responsive."
                        },
                        {
                            question: "What does scheduling leads involve?",
                            answer: "Scheduling leads allows you to plan and prioritize follow-ups, ensuring timely communication and better conversion rates."
                        },
                        {
                            question: "How can I close deals quickly using the CRM?",
                            answer: "The CRM enables you to generate invoices directly from a prospect's record, update the deal stage, and monitor the status, helping you close deals faster."
                        }
                    ]
                }
            ],
        };
    },
    methods: {
        filteredFaqs(plans) {
            if (!this.searchTerm) {
                return plans;
            }
            const term = this.searchTerm.toLowerCase();
            return plans.filter(faq =>
                faq.question.toLowerCase().includes(term) || faq.answer.toLowerCase().includes(term)
            );
        },
        onTabClick(index) {
            this.activeTabIndex = index;
            this.scrollTabIntoView(index);
        },
        scrollTabIntoView(index) {
            const tabElement = document.getElementById(`tab-${index}`);
            if (tabElement) {
                tabElement.scrollIntoView({ behavior: 'smooth', inline: 'center', block: 'nearest' });
            }
        }
    },
    mounted() {
        this.$refs.searchInput.focus();
    }
};
</script>

<style scoped>
.nav-link {
    transition: background-color 0.3s ease, color 0.3s ease;
}

.nav-link.active {
    /* background-color:black!important; */
    background-color: black !important;
    border-bottom: 2px solid var(--brand-color) !important;
    color: var(--brand-color) !important;
    font-weight: 600;
    transition: background-color 0.3s ease, color 0.3s ease, transform 0.3s ease;
}

.accordion-button:not(.collapsed) {
    color: white !important;
    background-color: gold !important;
    box-shadow: none !important;
}

.accordion-button:focus {
    z-index: 3;
    outline: 0;
    box-shadow: none !important;
}

.accordion-button::after {
    filter: invert(1) !important
}
</style>
