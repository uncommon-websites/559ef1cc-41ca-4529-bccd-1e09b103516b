<script lang="ts">
	import { onMount } from 'svelte';

    // Data for sections
    const navLinks = ["Rankings", "Best Colleges", "Advice", "Compare Schools", "Scholarships"];
    
    const logos = [
        { name: "Harvard", width: 100 },
        { name: "MIT", width: 80 },
        { name: "Stanford", width: 100 },
        { name: "Yale", width: 80 },
        { name: "Princeton", width: 110 },
        { name: "Columbia", width: 120 },
        { name: "Duke", width: 80 }
    ];

    const features = [
        {
            tag: "COMPREHENSIVE RANKINGS",
            title: "Compare 1,500+ colleges across 17 ranking factors",
            image: "phone",
            color: "bg-gray-100"
        },
        {
            tag: "DATA-DRIVEN INSIGHTS",
            title: "Trusted methodology analyzing graduation rates, faculty resources, and more",
            image: "analytics",
            color: "bg-gray-100"
        },
        {
            tag: "SCHOOL COMPARISON",
            title: "Side-by-side comparison of tuition, acceptance rates, and outcomes",
            image: "search",
            color: "bg-gray-100"
        },
        {
            tag: "EXPERT GUIDANCE",
            title: "College admissions advice from education experts",
            image: "editor",
            color: "bg-gray-100"
        },
        {
            tag: "SCHOLARSHIP FINDER",
            title: "Discover financial aid opportunities matched to your profile",
            image: "admin",
            color: "bg-gray-100"
        },
        {
            tag: "STUDENT REVIEWS",
            title: "Real perspectives from current students and alumni",
            image: "video",
            color: "bg-gray-100"
        }
    ];

    const testimonials = [
        {
            quote: "U.S. News rankings helped me narrow down my college list from 50 schools to 10 that were actually the right fit for my major and budget.",
            name: "Sarah Martinez",
            role: "Freshman at UC Berkeley",
            avatar: "SM"
        },
        {
            quote: "As a guidance counselor, U.S. News is my go-to resource. The methodology is transparent and the data is comprehensive.",
            name: "Michael Chen",
            role: "High School Guidance Counselor",
            avatar: "MC"
        },
         {
            quote: "The comparison tool made it so easy to see which schools offered the best value for my intended major. I found my dream school!",
            name: "Emily Johnson",
            role: "Sophomore at Northwestern",
            avatar: "EJ"
        },
        {
            quote: "U.S. News gave us the confidence that we were making an informed decision. The rankings and data analysis are unmatched.",
            name: "David Thompson",
            role: "Parent of College Student",
            avatar: "DT"
        },
        {
            quote: "I recommend U.S. News to every family I work with. It's the most trusted source for college information.",
            name: "Jennifer Park",
            role: "College Admissions Consultant",
            avatar: "JP"
        },
        {
            quote: "The scholarship finder helped me discover opportunities I never would have found on my own. It made college affordable.",
            name: "Marcus Williams",
            role: "Junior at Georgia Tech",
            avatar: "MW"
        }
    ];

    const partnershipServices = [
        "Transparent ranking methodology",
        "Annual data verification process",
        "Direct partnerships with 1,500+ institutions",
        "Guidance counselor resources",
        "Student success tracking",
        "Regular methodology updates",
        "Educational research and insights"
    ];

    const comparisons = [
        {
            tag: "DATA METHODOLOGY",
            left: "User-generated reviews and crowdsourced ratings with limited verification",
            right: "Rigorous methodology analyzing 17 factors including graduation rates, faculty resources, and peer assessment"
        },
        {
            tag: "RANKING TRANSPARENCY",
            left: "Opaque algorithms and unclear weighting of ranking factors",
            right: "Fully transparent methodology published annually with detailed explanations of each ranking factor"
        },
        {
            tag: "SCHOOL COVERAGE",
            left: "Limited data on smaller schools and regional institutions",
            right: "Comprehensive rankings of 1,500+ institutions across all categories and regions"
        },
        {
            tag: "EXPERT GUIDANCE",
            left: "Generic college advice articles and test prep materials",
            right: "Expert editorial team providing in-depth admissions guidance and scholarship strategies"
        },
        {
            tag: "DATA ACCURACY",
            left: "Self-reported data with inconsistent verification",
            right: "Direct partnerships with institutions and rigorous annual data verification process"
        }
    ];

    const faqs = [
        "How does U.S. News calculate college rankings?",
        "Are the rankings updated annually?",
        "How can I compare schools side-by-side?",
        "What factors should I consider beyond rankings?",
        "How do I find scholarships that match my profile?",
        "Can I trust the data provided by U.S. News?",
        "How do I use rankings to create my college list?",
        "What's the difference between national and regional rankings?",
        "How can guidance counselors access U.S. News resources?"
    ];

</script>

<div class="font-sans text-gray-900 bg-white selection:bg-primary-200 selection:text-black">
    <!-- Navbar -->
    <nav class="sticky top-0 z-50 bg-white/80 backdrop-blur-md border-b border-gray-100">
        <div class="max-w-[1400px] mx-auto px-6 h-16 flex items-center justify-between">
            <div class="flex items-center gap-2">
                <!-- Logo Mark -->
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="text-primary-600">
                    <path opacity="0.5" d="M16.6765 3.05148C18.9425 3.05148 20.7794 4.88843 20.7794 7.15442C20.7794 9.42043 18.9425 11.2574 16.6765 11.2574H12.5735V7.15442C12.5735 4.88843 14.4105 3.05148 16.6765 3.05148Z" fill="currentColor"/>
                    <path d="M3 7.15442C3 4.88843 4.83695 3.05148 7.10294 3.05148C9.36895 3.05148 11.2059 4.88843 11.2059 7.15442V11.2574H7.10294C4.83695 11.2574 3 9.42043 3 7.15442Z" fill="currentColor"/>
                    <path d="M7.10294 20.8309C4.83695 20.8309 3 18.9939 3 16.7279C3 14.4619 4.83695 12.625 7.10294 12.625H11.2059V16.7279C11.2059 18.9939 9.36895 20.8309 7.10294 20.8309Z" fill="currentColor"/>
                    <path d="M20.7794 16.7279C20.7794 18.9939 18.9425 20.8309 16.6765 20.8309C14.4105 20.8309 12.5735 18.9939 12.5735 16.7279V12.625H16.6765C18.9425 12.625 20.7794 14.4619 20.7794 16.7279Z" fill="currentColor"/>
                </svg>
                <span class="font-medium text-lg tracking-tight">U.S. News</span>
            </div>

            <div class="hidden md:flex items-center gap-8 text-sm font-medium text-gray-600">
                {#each navLinks as link}
                    <a href="#" class="hover:text-black transition-colors">{link}</a>
                {/each}
            </div>

            <button class="bg-primary-600 text-white px-5 py-2 rounded-full text-sm font-medium hover:bg-primary-700 transition-colors">
                Explore Rankings
            </button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="pt-20 pb-16 px-6 text-center overflow-hidden">
        <div class="max-w-4xl mx-auto mb-12">
            <h1 class="font-serif text-6xl md:text-7xl lg:text-[5rem] leading-[1.1] mb-6 font-normal tracking-tight">
                Find your perfect <br/> college match
            </h1>
            <p class="text-lg md:text-xl text-gray-600 max-w-2xl mx-auto mb-8 leading-relaxed">
                Trusted rankings and expert guidance to help you compare schools, understand your options, and make the best decision for your future.
            </p>
            <button class="bg-primary-600 text-white px-8 py-3 rounded-full text-base font-medium hover:bg-primary-700 transition-colors">
                Explore Rankings
            </button>
        </div>

        <!-- Hero Image Collage Mockup -->
        <div class="relative max-w-[1400px] mx-auto h-[400px] md:h-[600px] mt-12 select-none pointer-events-none">
            <!-- We will build a CSS composition of screens -->
            <div class="relative w-full h-full flex justify-center items-end">
                
                <!-- Left Laptop -->
                <div class="absolute left-[-10%] bottom-0 w-[60%] md:w-[45%] z-10 transform -translate-x-10 translate-y-10">
                     <div class="bg-gray-900 rounded-t-xl p-1 shadow-2xl border border-gray-800 aspect-[16/10] overflow-hidden">
                        <!-- Screen Content -->
                        <div class="bg-gray-800 w-full h-full rounded-lg relative overflow-hidden">
                            <div class="absolute inset-0 bg-gradient-to-br from-blue-900 to-black opacity-80"></div>
                            <div class="p-4 text-white">
                                <div class="text-xs text-gray-400 mb-2">Space Tech</div>
                                <div class="h-2 w-20 bg-gray-600 rounded mb-4"></div>
                                <div class="grid grid-cols-2 gap-4">
                                    <div class="h-20 bg-gray-700/50 rounded"></div>
                                    <div class="h-20 bg-gray-700/50 rounded"></div>
                                </div>
                            </div>
                        </div>
                     </div>
                </div>

                <!-- Center Laptop (Main) -->
                <div class="absolute bottom-0 z-20 w-[70%] md:w-[50%] transform translate-y-5">
                    <div class="bg-black rounded-t-2xl p-2 shadow-2xl border border-gray-800 aspect-[16/10]">
                        <div class="bg-white w-full h-full rounded-xl overflow-hidden relative">
                            <!-- Mock UI -->
                            <div class="flex h-full">
                                <div class="w-1/3 bg-gray-50 p-4 border-r border-gray-100">
                                    <div class="h-8 w-8 bg-gray-200 rounded-full mb-4"></div>
                                    <div class="h-2 w-20 bg-gray-200 rounded mb-2"></div>
                                    <div class="h-2 w-16 bg-gray-200 rounded mb-6"></div>
                                    <div class="space-y-2">
                                        <div class="h-8 w-full bg-white border border-gray-200 rounded shadow-sm"></div>
                                        <div class="h-8 w-full bg-transparent rounded"></div>
                                    </div>
                                </div>
                                <div class="w-2/3 p-4">
                                    <div class="h-32 bg-gray-100 rounded-lg mb-4 flex items-center justify-center">
                                        <div class="w-12 h-12 bg-gray-300 rounded-full"></div>
                                    </div>
                                    <div class="h-4 w-3/4 bg-gray-100 rounded mb-2"></div>
                                    <div class="h-4 w-1/2 bg-gray-100 rounded"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Right Phone/Tablet -->
                <div class="absolute right-[-5%] bottom-10 w-[25%] md:w-[15%] z-30 transform translate-x-5">
                    <div class="bg-black rounded-[2rem] p-2 shadow-2xl border border-gray-800 aspect-[9/19]">
                        <div class="bg-white w-full h-full rounded-[1.5rem] overflow-hidden p-2 flex flex-col">
                             <div class="h-4 w-20 bg-gray-100 rounded mx-auto mb-4 mt-2"></div>
                             <div class="flex-1 bg-gray-50 rounded-xl p-2">
                                <div class="h-16 bg-primary-50 rounded-lg mb-2 border border-primary-100"></div>
                                <div class="h-16 bg-gray-100 rounded-lg mb-2"></div>
                             </div>
                        </div>
                    </div>
                </div>

                 <!-- Another Right Screen (Tablet?) -->
                <div class="absolute right-[10%] bottom-0 w-[40%] md:w-[30%] z-10 transform translate-x-10 translate-y-10">
                     <div class="bg-white rounded-t-xl p-1 shadow-2xl border border-gray-200 aspect-[4/3] overflow-hidden">
                        <div class="bg-gray-50 w-full h-full rounded-lg p-3">
                             <div class="flex gap-2 mb-3">
                                <div class="w-1/3 h-20 bg-white shadow-sm rounded-lg"></div>
                                <div class="w-1/3 h-20 bg-white shadow-sm rounded-lg"></div>
                                <div class="w-1/3 h-20 bg-white shadow-sm rounded-lg"></div>
                             </div>
                             <div class="h-32 bg-white shadow-sm rounded-lg"></div>
                        </div>
                     </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Logos Section -->
    <section class="py-16 border-b border-gray-100">
        <div class="max-w-[1400px] mx-auto px-6 text-center">
            <p class="text-sm text-gray-500 mb-10">Ranking America's top universities and colleges</p>
            <div class="flex flex-wrap justify-center items-center gap-12 md:gap-16 opacity-70 grayscale hover:grayscale-0 transition-all duration-500">
                {#each logos as logo}
                    <div class="h-8 flex items-center justify-center">
                        <!-- Placeholder for logo text/svg -->
                        <span class="font-bold text-xl font-serif italic">{logo.name}</span>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Meet Sana Learn Grid -->
    <section class="py-24 px-6 bg-gray-50">
        <div class="max-w-[1400px] mx-auto">
            <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Everything you need to choose the right school</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    From comprehensive rankings to expert admissions advice, U.S. News provides the trusted data and insights that help millions of students find their perfect college match every year.
                </p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                {#each features as feature}
                    <div class="group bg-white rounded-2xl overflow-hidden shadow-sm hover:shadow-md transition-shadow duration-300 flex flex-col h-[500px]">
                        <div class="p-8 pb-0 flex-1">
                            <span class="inline-block bg-primary-100 text-primary-800 text-[10px] font-bold tracking-wider px-2 py-1 rounded mb-4 uppercase">
                                {feature.tag}
                            </span>
                            <h3 class="font-serif text-2xl leading-tight mb-4">
                                {feature.title}
                            </h3>
                        </div>
                        <div class="h-[300px] bg-gray-100 relative overflow-hidden mt-4 mx-4 rounded-t-xl group-hover:translate-y-[-5px] transition-transform duration-500">
                            <!-- Mockup Content based on type -->
                            {#if feature.image === 'phone'}
                                <div class="absolute bottom-[-20px] left-1/2 transform -translate-x-1/2 w-[180px] h-[350px] bg-black rounded-[2rem] border-4 border-black shadow-xl overflow-hidden">
                                     <div class="bg-white w-full h-full p-3 pt-8">
                                        <div class="h-2 w-12 bg-gray-200 rounded mx-auto mb-4"></div>
                                        <div class="space-y-2">
                                            <div class="h-16 bg-gray-50 rounded-lg"></div>
                                            <div class="h-16 bg-gray-50 rounded-lg"></div>
                                        </div>
                                     </div>
                                </div>
                            {:else if feature.image === 'video'}
                                <div class="absolute inset-0 p-4 flex items-end justify-center">
                                    <div class="w-full h-[90%] bg-gray-800 rounded-t-lg shadow-lg relative overflow-hidden">
                                        <div class="absolute inset-0 flex items-center justify-center text-white/20">
                                            <svg width="48" height="48" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 14.5v-9l6 4.5-6 4.5z"/></svg>
                                        </div>
                                        <div class="absolute bottom-4 left-4 flex gap-2">
                                            <div class="w-8 h-8 bg-gray-600 rounded-full"></div>
                                            <div class="w-8 h-8 bg-gray-600 rounded-full"></div>
                                        </div>
                                    </div>
                                </div>
                            {:else if feature.image === 'search'}
                                 <div class="absolute bottom-[-40px] right-[-20px] w-full h-full bg-white shadow-lg rounded-tl-2xl p-6 border border-gray-100">
                                     <div class="flex items-center gap-3 mb-4 border-b pb-4">
                                         <div class="w-8 h-8 bg-primary-600 rounded-full"></div>
                                         <div class="h-2 w-32 bg-gray-200 rounded"></div>
                                     </div>
                                     <div class="space-y-3">
                                         <div class="h-2 w-full bg-gray-100 rounded"></div>
                                         <div class="h-2 w-5/6 bg-gray-100 rounded"></div>
                                         <div class="h-2 w-4/6 bg-gray-100 rounded"></div>
                                     </div>
                                 </div>
                            {:else}
                                <div class="absolute inset-4 bg-white shadow-sm rounded-lg border border-gray-100 flex items-center justify-center">
                                    <div class="text-gray-300">UI Mockup</div>
                                </div>
                            {/if}
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="py-24 px-6 bg-white">
        <div class="max-w-[1400px] mx-auto">
            <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Trusted by students, <br/> parents, and counselors</h2>
                <p class="text-lg text-gray-600 leading-relaxed mb-10">
                    Over 40 million users rely on U.S. News to make one of life's most important decisions. <br/> See what they have to say about their experience.
                </p>
                <div class="flex justify-center gap-4">
                    <!-- G2 Badges Mockup -->
                    {#each Array(5) as _, i}
                        <div class="w-16 h-20 bg-gradient-to-br from-red-50 to-orange-50 border border-red-100 rounded flex flex-col items-center justify-center p-1 text-[8px] text-center text-red-800 font-bold shadow-sm">
                            <div class="w-6 h-6 bg-red-500 rounded-full mb-1 text-white flex items-center justify-center">G2</div>
                            Leader
                        </div>
                    {/each}
                </div>
            </div>

            <div class="columns-1 md:columns-2 lg:columns-3 gap-6 space-y-6">
                {#each testimonials as testimonial}
                    <div class="break-inside-avoid bg-gray-50 p-8 rounded-2xl">
                        <p class="text-lg leading-relaxed mb-6">"{testimonial.quote}"</p>
                        <div class="flex items-center gap-3">
                            <div class="w-10 h-10 bg-gray-300 rounded-full flex items-center justify-center text-sm font-bold text-gray-600">
                                {testimonial.avatar}
                            </div>
                            <div>
                                <div class="font-medium">{testimonial.name}</div>
                                <div class="text-sm text-gray-500">{testimonial.role}</div>
                            </div>
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Partnership Section -->
    <section class="py-24 px-6 bg-white border-t border-gray-100">
        <div class="max-w-[1400px] mx-auto">
             <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Built on trust <br/> and transparency</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    Our rankings aren't just numbers. They're backed by rigorous methodology, <br/> direct partnerships with institutions, and decades of educational expertise.
                </p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                <div class="bg-gray-50 p-12 rounded-3xl h-full">
                    <h3 class="font-serif text-2xl mb-8">Our commitment to accuracy</h3>
                    <ul class="space-y-4">
                        {#each partnershipServices as service}
                            <li class="flex items-center gap-3">
                                <div class="w-5 h-5 rounded-full bg-primary-600 flex items-center justify-center shrink-0">
                                    <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="4" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
                                </div>
                                <span class="text-gray-700">{service}</span>
                            </li>
                        {/each}
                    </ul>
                </div>
                <div class="h-full min-h-[500px] rounded-3xl overflow-hidden relative">
                    <!-- Image of guidance counselor with students -->
                    <div class="absolute inset-0 bg-gray-200">
                        <img src="/generated/image-high-school-guidance-counselor-meeting-w-1765515681224-0.webp" alt="Guidance counselor meeting with students" class="w-full h-full object-cover" />
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Case Studies Section -->
    <section class="py-24 px-6 bg-white">
        <div class="max-w-[1400px] mx-auto">
            <div class="flex justify-between items-end mb-12">
                <p class="text-lg text-gray-600 max-w-xl">Real students, real success stories. See how U.S. News helped them find their perfect match.</p>
                <div class="flex gap-2">
                    <button class="w-10 h-10 rounded-full border border-gray-200 flex items-center justify-center hover:bg-gray-50">
                        ←
                    </button>
                    <button class="w-10 h-10 rounded-full bg-black text-white flex items-center justify-center hover:bg-gray-800">
                        →
                    </button>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <!-- Card 1 -->
                <div class="aspect-[4/5] relative rounded-2xl overflow-hidden group cursor-pointer">
                    <div class="absolute inset-0 bg-gray-900">
                        <!-- Mock Background Image -->
                        <div class="absolute inset-0 opacity-50 bg-gradient-to-t from-black via-transparent to-transparent"></div>
                        <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1549317661-bd32c8ce0db2?q=80&w=2070&auto=format&fit=crop')] bg-cover bg-center mix-blend-overlay opacity-40"></div>
                    </div>
                    <div class="absolute inset-0 p-8 flex flex-col justify-between text-white">
                        <div>
                            <h3 class="font-serif text-3xl leading-tight mb-4">From 50 schools to the perfect fit in just weeks</h3>
                            <div class="text-xs text-gray-300 uppercase tracking-wider">Student: Sarah M. <br/> Now at: UC Berkeley</div>
                        </div>
                        <div class="font-bold text-xl">Engineering Major</div>
                    </div>
                </div>

                <!-- Card 2 -->
                <div class="aspect-[4/5] relative rounded-2xl overflow-hidden group cursor-pointer">
                    <div class="absolute inset-0 bg-gray-900">
                         <div class="absolute inset-0 opacity-50 bg-gradient-to-t from-black via-transparent to-transparent"></div>
                         <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1542744173-8e7e53415bb0?q=80&w=2070&auto=format&fit=crop')] bg-cover bg-center mix-blend-overlay opacity-40"></div>
                    </div>
                    <div class="absolute inset-0 p-8 flex flex-col justify-between text-white">
                        <div>
                            <h3 class="font-serif text-3xl leading-tight mb-4">Found $40K in scholarships using the scholarship finder</h3>
                            <div class="text-xs text-gray-300 uppercase tracking-wider">Student: Marcus W. <br/> Now at: Georgia Tech</div>
                        </div>
                        <div class="font-bold text-xl">Computer Science</div>
                    </div>
                </div>

                <!-- Card 3 -->
                <div class="aspect-[4/5] relative rounded-2xl overflow-hidden group cursor-pointer">
                    <div class="absolute inset-0 bg-gray-900">
                         <div class="absolute inset-0 opacity-50 bg-gradient-to-t from-black via-transparent to-transparent"></div>
                         <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1581091226825-a6a2a5aee158?q=80&w=2070&auto=format&fit=crop')] bg-cover bg-center mix-blend-overlay opacity-40"></div>
                    </div>
                    <div class="absolute inset-0 p-8 flex flex-col justify-between text-white">
                        <div>
                            <h3 class="font-serif text-3xl leading-tight mb-4">Helped 200+ students find their dream schools</h3>
                            <div class="text-xs text-gray-300 uppercase tracking-wider">Counselor: Michael C. <br/> School: Lincoln High</div>
                        </div>
                        <div class="font-bold text-xl">Guidance Counselor</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Comparison Section -->
    <section class="py-24 px-6 bg-white">
        <div class="max-w-[1400px] mx-auto">
             <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Why U.S. News <br/> stands apart</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    Not all college rankings are created equal. See how our rigorous methodology <br/> and transparent approach set us apart from the competition.
                </p>
            </div>

            <div class="border-t border-gray-100">
                <div class="grid grid-cols-3 py-4 text-xs text-gray-400 uppercase tracking-wider border-b border-gray-100">
                    <div>Other Rankings</div>
                    <div class="text-center">→</div>
                    <div>U.S. News</div>
                </div>
                {#each comparisons as item}
                    <div class="grid grid-cols-1 md:grid-cols-[1fr_auto_1fr] gap-8 py-12 border-b border-gray-100 items-center group hover:bg-gray-50 transition-colors px-4 -mx-4 rounded-xl">
                        <div class="text-gray-500 leading-relaxed md:pr-8">
                            {item.left}
                        </div>
                        <div class="flex justify-center">
                            <span class="bg-primary-100 text-primary-800 text-[10px] font-bold tracking-wider px-2 py-1 rounded uppercase whitespace-nowrap">
                                {item.tag}
                            </span>
                        </div>
                        <div class="text-black font-medium leading-relaxed md:pl-8">
                            {item.right}
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Integrations & Security Section -->
    <section class="py-24 px-6 bg-white">
        <div class="max-w-[1400px] mx-auto">
             <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Comprehensive data <br/> from trusted sources</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    Our rankings are built on verified data from institutions and rigorous analysis.
                </p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-16">
                <!-- Data Sources -->
                <div>
                    <div class="text-center mb-8">
                        <span class="bg-primary-100 text-primary-800 text-[10px] font-bold tracking-wider px-2 py-1 rounded uppercase">
                            17 RANKING FACTORS ANALYZED
                        </span>
                    </div>
                    <div class="grid grid-cols-4 gap-6">
                        {#each ['Graduation rates', 'Faculty resources', 'Student excellence', 'Financial resources', 'Alumni giving', 'Peer assessment', 'Retention rates', 'Class size', 'SAT/ACT scores', 'Acceptance rate', 'Graduate outcomes', 'Social mobility'] as tool}
                            <div class="aspect-square bg-gray-50 rounded-xl flex flex-col items-center justify-center p-4 hover:bg-gray-100 transition-colors">
                                <div class="w-8 h-8 bg-primary-200 rounded-full mb-2"></div> <!-- Icon Placeholder -->
                                <span class="text-[10px] text-center text-gray-600 font-medium">{tool}</span>
                            </div>
                        {/each}
                    </div>
                </div>

                <!-- Resources -->
                <div>
                    <div class="text-center mb-8">
                        <span class="bg-primary-100 text-primary-800 text-[10px] font-bold tracking-wider px-2 py-1 rounded uppercase">
                            RESOURCES FOR YOUR JOURNEY
                        </span>
                    </div>
                    <div class="grid grid-cols-4 gap-6">
                         {#each ['College search', 'Compare schools', 'Scholarship finder', 'Admissions advice', 'Financial aid guide', 'Major explorer', 'Campus life info', 'Application tips', 'Essay guidance', 'Test prep resources', 'Career outcomes', 'Student reviews'] as item}
                            <div class="aspect-square bg-gray-50 rounded-xl flex flex-col items-center justify-center p-2 hover:bg-gray-100 transition-colors">
                                <div class="w-6 h-6 border-2 border-primary-300 rounded mb-2"></div> <!-- Icon Placeholder -->
                                <span class="text-[10px] text-center text-gray-600 font-medium leading-tight">{item}</span>
                            </div>
                        {/each}
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Mission Section -->
    <section class="py-24 px-6">
        <div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-2 min-h-[600px]">
            <div class="bg-white relative flex items-center justify-center p-12 overflow-hidden">
                <div class="flex gap-4 transform -rotate-6 scale-90">
                    <div class="w-64 h-80 bg-gray-800 flex items-center justify-center text-white font-bold text-4xl shadow-2xl">THE WALL STREET JOURNAL</div>
                    <div class="w-64 h-80 bg-primary-600 flex items-center justify-center text-white font-bold text-4xl shadow-2xl z-10 -mt-12">U.S. NEWS</div>
                    <div class="w-64 h-80 bg-gray-900 flex items-center justify-center text-white font-bold text-4xl shadow-2xl">THE NEW YORK TIMES</div>
                </div>
            </div>
            <div class="bg-primary-50 p-12 lg:p-24 flex flex-col justify-center">
                <p class="font-serif text-3xl md:text-4xl leading-tight mb-8">
                    For over 40 years, U.S. News has been the trusted source for college rankings and educational guidance.
                </p>
                <p class="font-serif text-3xl md:text-4xl leading-tight">
                    We've helped millions of students find their perfect college match through comprehensive data analysis, transparent methodology, and expert insights. Our commitment to accuracy and trust continues to guide families through one of life's most important decisions.
                </p>
            </div>
        </div>
    </section>

    <!-- Bottom CTA -->
    <section class="py-32 px-6 text-center bg-white">
        <div class="max-w-4xl mx-auto">
            <h2 class="font-serif text-6xl md:text-7xl mb-6">Your college journey <br/> starts here.</h2>
            <p class="text-xl text-gray-600 mb-10">Join 40 million students finding their perfect match.</p>
            <button class="bg-primary-600 text-white px-8 py-3 rounded-full text-base font-medium hover:bg-primary-700 transition-colors">
                Explore Rankings
            </button>
        </div>
    </section>

    <!-- FAQ Section -->
    <section class="py-24 px-6 bg-white border-t border-gray-100">
        <div class="max-w-[1400px] mx-auto">
            <h2 class="font-serif text-5xl mb-16">FAQ</h2>
            <div class="space-y-4">
                {#each faqs as faq}
                    <div class="border-b border-gray-100 py-6 flex justify-between items-center cursor-pointer group hover:bg-gray-50 px-4 -mx-4 rounded-lg transition-colors">
                        <span class="text-lg font-medium">{faq}</span>
                        <div class="w-8 h-8 rounded-full bg-black text-white flex items-center justify-center group-hover:bg-gray-800 transition-colors">
                            <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg>
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="py-24 px-6 bg-white border-t border-gray-100">
        <div class="max-w-[1400px] mx-auto grid grid-cols-1 md:grid-cols-4 gap-12">
            <div class="col-span-1 md:col-span-1">
                <div class="flex items-center gap-2 mb-8">
                     <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="text-primary-600">
                        <path opacity="0.5" d="M16.6765 3.05148C18.9425 3.05148 20.7794 4.88843 20.7794 7.15442C20.7794 9.42043 18.9425 11.2574 16.6765 11.2574H12.5735V7.15442C12.5735 4.88843 14.4105 3.05148 16.6765 3.05148Z" fill="currentColor"/>
                        <path d="M3 7.15442C3 4.88843 4.83695 3.05148 7.10294 3.05148C9.36895 3.05148 11.2059 4.88843 11.2059 7.15442V11.2574H7.10294C4.83695 11.2574 3 9.42043 3 7.15442Z" fill="currentColor"/>
                        <path d="M7.10294 20.8309C4.83695 20.8309 3 18.9939 3 16.7279C3 14.4619 4.83695 12.625 7.10294 12.625H11.2059V16.7279C11.2059 18.9939 9.36895 20.8309 7.10294 20.8309Z" fill="currentColor"/>
                        <path d="M20.7794 16.7279C20.7794 18.9939 18.9425 20.8309 16.6765 20.8309C14.4105 20.8309 12.5735 18.9939 12.5735 16.7279V12.625H16.6765C18.9425 12.625 20.7794 14.4619 20.7794 16.7279Z" fill="currentColor"/>
                    </svg>
                    <span class="font-medium text-xl tracking-tight">U.S. News</span>
                </div>
                <div class="text-sm text-gray-500 mb-4">Get college insights delivered</div>
                <div class="flex gap-2 border-b border-gray-200 pb-2 mb-8">
                    <input type="email" placeholder="Email address" class="w-full outline-none text-sm" />
                    <button class="text-gray-400 hover:text-black">→</button>
                </div>
                <div class="text-xs text-gray-400">© U.S. News & World Report 2025</div>
            </div>

            <div class="grid grid-cols-2 md:grid-cols-3 gap-8 col-span-1 md:col-span-3">
                <div>
                    <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider mb-6">Rankings</h4>
                    <ul class="space-y-3 text-sm text-gray-600">
                        <li><a href="#" class="hover:text-black">Best Colleges</a></li>
                        <li><a href="#" class="hover:text-black">National Universities</a></li>
                        <li><a href="#" class="hover:text-black">Liberal Arts Colleges</a></li>
                        <li><a href="#" class="hover:text-black">Regional Universities</a></li>
                        <li><a href="#" class="hover:text-black">Best Value Schools</a></li>
                        <li><a href="#" class="hover:text-black">Online Programs</a></li>
                        <li><a href="#" class="hover:text-black">Graduate Schools</a></li>
                        <li><a href="#" class="hover:text-black">Business Schools</a></li>
                        <li><a href="#" class="hover:text-black">Medical Schools</a></li>
                        <li><a href="#" class="hover:text-black">Law Schools</a></li>
                        <li><a href="#" class="hover:text-black">Methodology</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider mb-6">Resources</h4>
                    <ul class="space-y-3 text-sm text-gray-600">
                        <li><a href="#" class="hover:text-black">College Search</a></li>
                        <li><a href="#" class="hover:text-black">Compare Schools</a></li>
                        <li><a href="#" class="hover:text-black">Scholarship Finder</a></li>
                        <li><a href="#" class="hover:text-black">Financial Aid Guide</a></li>
                        <li><a href="#" class="hover:text-black">Admissions Calculator</a></li>
                        <li><a href="#" class="hover:text-black">Major Explorer</a></li>
                        <li><a href="#" class="hover:text-black">Campus Tours</a></li>
                        <li><a href="#" class="hover:text-black">Student Reviews</a></li>
                        <li><a href="#" class="hover:text-black">Application Tips</a></li>
                        <li><a href="#" class="hover:text-black">Test Prep</a></li>
                        <li><a href="#" class="hover:text-black">Career Outcomes</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider mb-6">About</h4>
                    <ul class="space-y-3 text-sm text-gray-600">
                        <li><a href="#" class="hover:text-black">About U.S. News</a></li>
                        <li><a href="#" class="hover:text-black">Editorial Guidelines</a></li>
                        <li><a href="#" class="hover:text-black">Education Team</a></li>
                        <li><a href="#" class="hover:text-black">Advertise</a></li>
                        <li><a href="#" class="hover:text-black">Careers</a></li>
                        <li><a href="#" class="hover:text-black">Press</a></li>
                        <li><a href="#" class="hover:text-black">Contact Us</a></li>
                        <li><a href="#" class="hover:text-black">Privacy Policy</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>

</div>

