<template>
    <div class="brand-bg">
        <h1 class="text-center text-capitalize mb-4">our customer's reviews</h1>
        <article :class="['wrapper', { 'wrapper--vertical': isVertical }]" class="pb-5">
            <div class="marquee" :class="{ 'marquee--vertical': isVertical }">
                <div class="marquee__group mt-5" :style="{ 'animation-direction': isReverse ? 'reverse' : 'normal' }">
                    <div class="" v-for="(card, index) in cards" :key="index">
                        <div class="card border-0 h-100 shadow">
                            <div class="card-header d-flex justify-content-center algin-items-center">
                                <div class="rounded-circle overflow-hidden  shadow p-1"
                                    style="width:60px; height:60px; margin-top:-40px;">
                                    <img :src="card.image" alt="Profile" class="rounded-circle"
                                        style="width: 100%; height: 100%;object-fit: cover;" />
                                </div>
                            </div>
                            <div class="card-body py-2 px-1" style="max-width: 250px;">
                                <p class="name smaller mb-0 mt-0 pb-2 text-ellipsis1 border-bottom border-2">{{
                                    card.name
                                }}</p>
                                <p class="  smaller mb-0  text-ellipsis3 pt-2 ">{{ card.review }} </p>
                            </div>
                        </div>
                    </div>
                </div>
                <div aria-hidden="true" class="marquee__group mt-5"
                    :style="{ 'animation-direction': isReverse ? 'reverse' : 'normal' }">
                    <div class="" v-for="(card, index) in cards" :key="index">
                        <div class="card border-0 h-100 shadow">
                            <div class="card-header d-flex justify-content-center algin-items-center">
                                <div class="rounded-circle overflow-hidden  shadow p-1"
                                    style="width:60px; height:60px; margin-top:-40px;">
                                    <img :src="card.image" alt="Profile" class="rounded-circle"
                                        style="width: 100%; height: 100%;object-fit: cover;" />
                                </div>
                            </div>
                            <div class="card-body py-2 px-1" style="max-width: 250px;">
                                <p class="name smaller mb-0 mt-0 pb-2 text-ellipsis1 border-bottom border-2">{{
                                    card.name
                                }}</p>
                                <p class="  smaller mb-0  text-ellipsis3  pt-2">{{ card.review }} </p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="marquee marquee--reverse" :class="{ 'marquee--vertical': isVertical }">
                <div class="marquee__group mt-5" :style="{ 'animation-direction': isReverse ? 'normal' : 'reverse' }">
                    <div class="" v-for="(card, index) in cards2" :key="index">
                        <div class="card border-0 h-100 shadow">
                            <div class="card-header d-flex justify-content-center algin-items-center">
                                <div class="rounded-circle overflow-hidden  shadow p-1"
                                    style="width:60px; height:60px; margin-top:-40px;">
                                    <img :src="card.image" alt="Profile" class="rounded-circle"
                                        style="width: 100%; height: 100%;object-fit: cover;" />
                                </div>
                            </div>
                            <div class="card-body  py-2 px-1" style="max-width: 250px;">
                                <p class="name smaller mb-0 mt-0 pb-2 text-ellipsis1 border-bottom border-2">{{
                                    card.name
                                }}</p>
                                <p class="  smaller mb-0  text-ellipsis3  pt-2">{{ card.review }} </p>
                            </div>
                        </div>
                    </div>
                </div>
                <div aria-hidden="true" class="marquee__group mt-5"
                    :style="{ 'animation-direction': isReverse ? 'normal' : 'reverse' }">
                    <div class="" v-for="(card, index) in cards2" :key="index">
                        <div class="card border-0 h-100  shadow">
                            <div class="card-header d-flex justify-content-center algin-items-center">
                                <div class="rounded-circle overflow-hidden  shadow p-1"
                                    style="width:60px; height:60px; margin-top:-40px;">
                                    <img :src="card.image" alt="Profile" class="rounded-circle"
                                        style="width: 100%; height: 100%;object-fit: cover;" />
                                </div>
                            </div>
                            <div class="card-body py-2 px-1" style="max-width: 250px;">
                                <p class="name smaller mb-0 mt-0 pb-2 text-ellipsis1 border-bottom border-2">{{
                                    card.name
                                }}</p>
                                <p class="  smaller mb-0  text-ellipsis3 pt-2 ">{{ card.review }} </p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="marquee" :class="{ 'marquee--vertical': isVertical }">
                <div class="marquee__group mt-5" :style="{ 'animation-direction': isReverse ? 'reverse' : 'normal' }">
                    <div class="" v-for="(card, index) in cards3" :key="index">
                        <div class="card border-0 h-100 shadow">
                            <div class="card-header d-flex justify-content-center algin-items-center">
                                <div class="rounded-circle overflow-hidden  shadow p-1"
                                    style="width:60px; height:60px; margin-top:-40px;">
                                    <img v-if="card.image" :src="card.image" alt="Profile" class="rounded-circle"
                                        style="width: 100%; height: 100%;object-fit: cover;" />
                                    <i v-else class="bi bi-person-circle"></i>
                                </div>
                            </div>
                            <div class="card-body py-2 px-1" style="max-width: 250px;">
                                <p class="name smaller mb-0 mt-0 pb-2 text-ellipsis1 border-bottom border-2">{{
                                    card.name
                                }}</p>
                                <p class="  smaller mb-0  text-ellipsis3 pt-2 ">{{ card.review }} </p>
                            </div>
                        </div>
                    </div>
                </div>
                <div aria-hidden="true" class="marquee__group mt-5"
                    :style="{ 'animation-direction': isReverse ? 'reverse' : 'normal' }">
                    <div class="" v-for="(card, index) in cards3" :key="index">
                        <div class="card border-0 h-100 shadow">
                            <div class="card-header d-flex justify-content-center algin-items-center">
                                <div class="rounded-circle overflow-hidden  shadow p-1"
                                    style="width:60px; height:60px; margin-top:-40px;">
                                    <img :src="card.image" alt="Profile" class="rounded-circle"
                                        style="width: 100%; height: 100%;object-fit: cover;" />
                                </div>
                            </div>
                            <div class="card-body py-2 px-1" style="max-width: 250px;">
                                <p class="name smaller mb-0 mt-0 pb-2 text-ellipsis1 border-bottom border-2">{{
                                    card.name
                                }}</p>
                                <p class="smaller mb-0  text-ellipsis3 pt-2">{{ card.review }} </p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </article>
    </div>
</template>

<script>

export default {
    name: "HomeTestimonialSection",
    props: {
        brandColorOne: {
            type: String,
            default: '#000'
        }
    },
    data() {
        return {
            isVertical: false,
            isReverse: false,
            cards: [
                {
                    image: 'img/customers/4.jpeg',
                    title: 'Perfect for Networking',
                    tax: 'Streamlined my contact sharing',
                    time: 'Used for 2 months',
                    name: 'Ravi Patel',
                    subtitle: 'Founder at TechSavvy Solutions',
                    review: 'The QR Code feature is a game-changer! Sharing my contact details has never been so effortless. My clients love how professional it looks.'
                },
                {
                    image: 'img/customers/2.jpeg',
                    title: 'Boosts Engagement',
                    tax: 'Availed maximum reactions',
                    time: 'Used for 3 months',
                    name: 'Aarushi Khanna',
                    subtitle: 'Marketing Manager at Brandify Co.',
                    review: 'I’ve seen a significant increase in client engagement thanks to the views and reactions tracking feature. The payment integration is an added bonus!'
                },
                {
                    image: 'img/customers/3.jpeg',
                    title: 'Great for Freelancers',
                    tax: 'Enhanced my portfolio',
                    time: 'Used for 6 weeks',
                    name: 'Vikram Mehra',
                    subtitle: 'Freelance Graphic Designer',
                    review: 'The timeline and skillset features let me showcase my expertise effectively. My clients have complimented my card multiple times!'
                },
                {
                    image: 'img/customers/1.jpeg',
                    title: 'Simplifies Connections',
                    tax: 'Increased network by 30%',
                    time: 'Used for 1 month',
                    name: 'Simran Batra',
                    subtitle: 'Director at Batra Consulting',
                    review: 'Sharing my fameset account via social profiles is super quick. The fun facts section adds a personal touch, making it more relatable.'
                },
                {
                    image: 'img/customers/5.jpeg',
                    title: 'Builds Trust Instantly',
                    tax: 'Highlighted my achievements',
                    time: 'Used for 3 months',
                    name: 'Rahul Verma',
                    subtitle: 'Co-Founder at NeoBiz Ventures',
                    review: 'The achievements and testimonial sections help build instant trust with new clients. I also love the website widget—it’s seamless!'
                },
                {
                    image: 'img/customers/6.jpeg',
                    title: 'Outstanding Features',
                    tax: 'Effortless Sharing',
                    time: 'within 2 weeks',
                    name: 'Priya Sharma',
                    subtitle: 'Sales Executive at NexGen Realty',
                    review: 'This fameset account made me stand out at networking events. The ability to track hearts and promotes is so motivating.'
                },
            ],
            cards2: [
                {
                    image: 'img/customers/7.jpeg',
                    title: 'User-Friendly Design',
                    tax: 'Enhanced online presence',
                    time: 'within 1 month',
                    name: 'Kunal Aggarwal',
                    subtitle: 'CEO at GreenTree Pvt. Ltd.',
                    review: 'The contact details and payment integration have made my interactions smoother. Reactions and reviews help me improve my client relationships.'
                },
                {
                    image: 'img/customers/8.jpeg',
                    title: 'Highly Customizable',
                    tax: 'Added personal branding',
                    time: 'Used for 4 months',
                    name: 'Rahul Joshi',
                    subtitle: 'Life Coach and Mentor',
                    review: 'The customization options allowed me to reflect my personality in the card. The testimonial section is a great trust-building tool.'
                },
                {
                    image: 'img/customers/9.jpeg',
                    title: 'Perfect for Startups',
                    tax: 'Gained new clients',
                    time: 'within 30 days',
                    name: 'Aditya Ghosh',
                    subtitle: 'Founder at InstaGrow Tech',
                    review: 'The promotes and reactions tracking features have helped me measure how well my networking efforts are performing.'
                },
                {
                    image: 'img/customers/10.jpeg',
                    title: 'Saves Time',
                    tax: 'Simplified client onboarding',
                    time: 'Used for 1 month',
                    name: 'Neha Singh',
                    subtitle: 'HR Consultant',
                    review: 'With the QR Code and payment integration, I’ve been able to onboard clients more efficiently. It’s a great investment!'
                },
                {
                    image: 'img/customers/11.jpeg',
                    title: 'Impressive Layout',
                    tax: 'Boosted my credibility',
                    time: 'Used for 2 months',
                    name: 'Arjun Nair',
                    subtitle: 'Financial Advisor',
                    review: 'The attributes and achievements sections allowed me to highlight my skills effectively. My clients feel more confident in my services.'
                },
                {
                    image: 'img/customers/12.jpeg',
                    title: 'Great for Promotions',
                    tax: 'Enhanced visibility',
                    time: 'within 15 days',
                    name: 'Ritik Roy',
                    subtitle: 'Event Planner',
                    review: 'The reactions and hearts features provide instant feedback on my promotions. The fameset account is sleek and modern.'
                },
                {
                    image: 'img/customers/14.jpeg',
                    title: 'A Complete Solution',
                    tax: 'Effortlessly integrated',
                    time: 'Used for 1 month',
                    name: 'Deepak Kumar',
                    subtitle: 'Freelance Photographer',
                    review: 'The website widget integration is seamless. I love how my portfolio, payment options, and testimonials are all in one place.'
                },
                {
                    image: 'img/customers/13.jpeg',
                    title: 'Perfect for Showcasing',
                    tax: 'Boosted my portfolio views',
                    time: 'within 3 weeks',
                    name: 'Tanya Mishra',
                    subtitle: 'Content Writer',
                    review: 'The timeline and fun facts sections make my portfolio engaging and interesting. I’ve received more views than ever before!'
                },

            ],
            cards3: [
                {
                    image: 'img/customers/15.jpeg',
                    title: 'Engages Audience',
                    tax: 'Increased client interactions',
                    time: 'Used for 2 months',
                    name: 'Rohan Kapoor',
                    subtitle: 'Fitness Trainer',
                    review: 'The reactions and reviews features have helped me improve my services. My clients enjoy the easy sharing options too!'
                },
                {
                    image: 'img/customers/16.jpg',
                    title: 'Modern and Elegant',
                    tax: 'Enhanced client trust',
                    time: 'Used for 45 days',
                    name: 'Shivam Sharma',
                    subtitle: 'Interior Designer',
                    review: 'The card layout is so modern and elegant! The attributes and skills sections make my services stand out.'
                },
                {
                    image: 'img/customers/17.jpg',
                    title: 'Makes Networking Easy',
                    tax: 'Built strong connections',
                    time: 'within 3 weeks',
                    name: 'Harsh Jain',
                    subtitle: 'Software Developer',
                    review: 'Sharing via social profiles and QR Code has been a breeze. The achievements section helped me land new projects.'
                },
                {
                    image: 'img/customers/18.jpg',
                    title: 'Highly Functional',
                    tax: 'Exceeded expectations',
                    time: 'Used for 3 months',
                    name: 'Akshay Gupta',
                    subtitle: 'Business Analyst',
                    review: 'The reactions and reviews features give me real-time feedback. The timeline helps showcase my career growth.'
                },
                {
                    image: 'img/customers/19.jpg',
                    title: 'Cost-Effective Solution',
                    tax: 'Saved on printing costs',
                    time: 'Used for 2 months',
                    name: 'Lokesh Verma',
                    subtitle: 'Freelance Content Strategist',
                    review: 'I’ve replaced physical business cards with this digital one. It’s eco-friendly, cost-effective, and packed with features!'
                },
                {
                    image: 'img/customers/20.jpg',
                    title: 'Great Design',
                    tax: 'Attracted new opportunities',
                    time: 'Used for 1 month',
                    name: 'Kabir Sen',
                    subtitle: 'Architect',
                    review: 'The fameset account is aesthetically designed. My clients appreciate the attributes and skills sections—it’s professional and impressive.'
                },
                {
                    image: 'img/customers/21.jpg',
                    title: 'Simplifies Sharing',
                    tax: 'Built a wider network',
                    time: 'within 20 days',
                    name: 'Vivek Kumar',
                    subtitle: 'Entrepreneur',
                    review: 'The easy sharing options and interactive features have helped me expand my network. The fameset account is a must-have!'
                }
            ]
        };
    },
    methods: {
        toggleDirection() {
            this.isVertical = !this.isVertical;
            this.isReverse = !this.isReverse;
        },
    },
};
</script>
<style scoped>
.card-header {
    background: linear-gradient(180deg, rgba(245, 197, 24, 1) 0%, rgb(0, 0, 0) 95%);
    padding: 10px;
    text-align: center;
    border-bottom: 0px !important;
}

.card {
    background-color: black !important;
    color: white !important
}
</style>
