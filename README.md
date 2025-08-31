<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TravelAdvisors - Your Ultimate Travel Companion</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Poppins', sans-serif; }
        .hero-bg { background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%); }
        .glass-effect { backdrop-filter: blur(10px); background: rgba(255, 255, 255, 0.1); }
        .card-3d { transform-style: preserve-3d; transition: transform 0.6s; }
        .card-3d:hover { transform: rotateY(10deg) rotateX(5deg); }
        .floating { animation: float 6s ease-in-out infinite; }
        @keyframes float { 0%, 100% { transform: translateY(0px); } 50% { transform: translateY(-20px); } }
        .gradient-text { background: linear-gradient(135deg, #667eea, #764ba2); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        .pulse-glow { animation: pulse-glow 2s infinite; }
        @keyframes pulse-glow { 0%, 100% { box-shadow: 0 0 20px rgba(102, 126, 234, 0.4); } 50% { box-shadow: 0 0 40px rgba(102, 126, 234, 0.8); } }
        .parallax { transform: translateZ(0); }
        .service-icon { transition: all 0.3s ease; }
        .service-icon:hover { transform: scale(1.2) rotate(5deg); }
        .mobile-menu { transform: translateX(-100%); transition: transform 0.3s ease; }
        .mobile-menu.active { transform: translateX(0); }
        .loading-spinner { animation: spin 1s linear infinite; }
        @keyframes spin { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
        .fade-in { opacity: 0; transform: translateY(30px); transition: all 0.6s ease; }
        .fade-in.visible { opacity: 1; transform: translateY(0); }
        .testimonial-slider { scroll-behavior: smooth; }
        .chat-widget { bottom: 20px; right: 20px; }
        .chat-bubble { animation: bounce 2s infinite; }
        @keyframes bounce { 0%, 20%, 50%, 80%, 100% { transform: translateY(0); } 40% { transform: translateY(-10px); } 60% { transform: translateY(-5px); } }
    </style>
</head>
<body class="bg-gray-50 overflow-x-hidden">
    <!-- Navigation -->
    <nav class="fixed w-full z-50 glass-effect border-b border-white border-opacity-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <div class="flex items-center space-x-3">
                    <div class="w-12 h-12 bg-gradient-to-r from-blue-500 to-purple-600 rounded-xl flex items-center justify-center">
                        <span class="text-2xl">🌍</span>
                    </div>
                    <div class="text-2xl font-bold gradient-text">TravelAdvisors</div>
                </div>
                <div class="hidden md:flex items-center space-x-8">
                    <a href="#home" class="text-white hover:text-blue-200 font-medium transition-colors">Home</a>
                    <a href="#destinations" class="text-white hover:text-blue-200 font-medium transition-colors">Destinations</a>
                    <a href="#services" class="text-white hover:text-blue-200 font-medium transition-colors">Services</a>
                    <a href="#packages" class="text-white hover:text-blue-200 font-medium transition-colors">Packages</a>
                    <a href="#about" class="text-white hover:text-blue-200 font-medium transition-colors">About</a>
                    <a href="#contact" class="text-white hover:text-blue-200 font-medium transition-colors">Contact</a>
                    <button id="loginBtn" class="bg-white bg-opacity-20 text-white px-6 py-2 rounded-full hover:bg-opacity-30 transition-all">
                        Sign In
                    </button>
                </div>
                <!-- Mobile Menu Button -->
                <button id="mobileMenuBtn" class="md:hidden text-white">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
                    </svg>
                </button>
            </div>
        </div>
        <!-- Mobile Menu -->
        <div id="mobileMenu" class="mobile-menu md:hidden fixed inset-y-0 left-0 w-64 glass-effect z-50">
            <div class="p-6">
                <div class="flex items-center justify-between mb-8">
                    <div class="text-xl font-bold text-white">Menu</div>
                    <button id="closeMobileMenu" class="text-white">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
                        </svg>
                    </button>
                </div>
                <div class="space-y-4">
                    <a href="#home" class="block text-white hover:text-blue-200 font-medium">Home</a>
                    <a href="#destinations" class="block text-white hover:text-blue-200 font-medium">Destinations</a>
                    <a href="#services" class="block text-white hover:text-blue-200 font-medium">Services</a>
                    <a href="#packages" class="block text-white hover:text-blue-200 font-medium">Packages</a>
                    <a href="#about" class="block text-white hover:text-blue-200 font-medium">About</a>
                    <a href="#contact" class="block text-white hover:text-blue-200 font-medium">Contact</a>
                </div>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero-bg min-h-screen flex items-center justify-center relative overflow-hidden">
        <div class="absolute inset-0 bg-black bg-opacity-20"></div>
        <div class="relative z-10 text-center text-white px-4 max-w-4xl mx-auto">
            <div class="floating mb-8">
                <h1 class="text-5xl md:text-7xl font-bold mb-6 leading-tight">
                    Discover Your Next
                    <span class="block gradient-text">Adventure</span>
                </h1>
            </div>
            <p class="text-xl md:text-2xl mb-8 opacity-90">
                Explore breathtaking destinations, create unforgettable memories, and let us guide your journey around the world.
            </p>
            <div class="flex flex-col sm:flex-row gap-4 justify-center">
                <button class="pulse-glow bg-white text-purple-600 px-8 py-4 rounded-full font-semibold text-lg hover:bg-opacity-90 transition-all">
                    Start Planning
                </button>
                <button class="glass-effect border border-white border-opacity-30 text-white px-8 py-4 rounded-full font-semibold text-lg hover:bg-white hover:bg-opacity-10 transition-all">
                    Watch Video
                </button>
            </div>
        </div>
        <!-- Floating Elements -->
        <div class="absolute top-20 left-10 floating text-6xl opacity-20">✈️</div>
        <div class="absolute bottom-20 right-10 floating text-4xl opacity-20" style="animation-delay: -2s;">🏔️</div>
        <div class="absolute top-1/2 left-20 floating text-5xl opacity-20" style="animation-delay: -4s;">🏖️</div>
    </section>

    <!-- Destinations Section -->
    <section id="destinations" class="py-20 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16 fade-in">
                <h2 class="text-4xl md:text-5xl font-bold gradient-text mb-4">Popular Destinations</h2>
                <p class="text-xl text-gray-600 max-w-2xl mx-auto">Discover the world's most amazing places with our curated selection of destinations</p>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Destination Card 1 -->
                <div class="card-3d bg-white rounded-2xl shadow-xl overflow-hidden fade-in">
                    <div class="h-64 bg-gradient-to-br from-blue-400 to-blue-600 flex items-center justify-center">
                        <span class="text-8xl">🏝️</span>
                    </div>
                    <div class="p-6">
                        <h3 class="text-2xl font-bold mb-2">Maldives</h3>
                        <p class="text-gray-600 mb-4">Crystal clear waters and pristine beaches await you in this tropical paradise.</p>
                        <div class="flex justify-between items-center">
                            <span class="text-2xl font-bold text-purple-600">$2,499</span>
                            <button class="bg-gradient-to-r from-purple-500 to-blue-500 text-white px-6 py-2 rounded-full hover:shadow-lg transition-all">
                                Explore
                            </button>
                        </div>
                    </div>
                </div>
                <!-- Destination Card 2 -->
                <div class="card-3d bg-white rounded-2xl shadow-xl overflow-hidden fade-in">
                    <div class="h-64 bg-gradient-to-br from-green-400 to-green-600 flex items-center justify-center">
                        <span class="text-8xl">🗻</span>
                    </div>
                    <div class="p-6">
                        <h3 class="text-2xl font-bold mb-2">Swiss Alps</h3>
                        <p class="text-gray-600 mb-4">Breathtaking mountain views and world-class skiing in the heart of Europe.</p>
                        <div class="flex justify-between items-center">
                            <span class="text-2xl font-bold text-purple-600">$3,299</span>
                            <button class="bg-gradient-to-r from-purple-500 to-blue-500 text-white px-6 py-2 rounded-full hover:shadow-lg transition-all">
                                Explore
                            </button>
                        </div>
                    </div>
                </div>
                <!-- Destination Card 3 -->
                <div class="card-3d bg-white rounded-2xl shadow-xl overflow-hidden fade-in">
                    <div class="h-64 bg-gradient-to-br from-orange-400 to-red-500 flex items-center justify-center">
                        <span class="text-8xl">🏛️</span>
                    </div>
                    <div class="p-6">
                        <h3 class="text-2xl font-bold mb-2">Greece</h3>
                        <p class="text-gray-600 mb-4">Ancient history meets stunning islands in this Mediterranean gem.</p>
                        <div class="flex justify-between items-center">
                            <span class="text-2xl font-bold text-purple-600">$1,899</span>
                            <button class="bg-gradient-to-r from-purple-500 to-blue-500 text-white px-6 py-2 rounded-full hover:shadow-lg transition-all">
                                Explore
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="py-20 bg-gray-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16 fade-in">
                <h2 class="text-4xl md:text-5xl font-bold gradient-text mb-4">Our Services</h2>
                <p class="text-xl text-gray-600 max-w-2xl mx-auto">We provide comprehensive travel services to make your journey seamless and memorable</p>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                <!-- Service 1 -->
                <div class="text-center fade-in">
                    <div class="service-icon w-20 h-20 bg-gradient-to-r from-blue-500 to-purple-600 rounded-full flex items-center justify-center mx-auto mb-6">
                        <span class="text-3xl">✈️</span>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Flight Booking</h3>
                    <p class="text-gray-600">Find the best flight deals and book with confidence</p>
                </div>
                <!-- Service 2 -->
                <div class="text-center fade-in">
                    <div class="service-icon w-20 h-20 bg-gradient-to-r from-green-500 to-teal-600 rounded-full flex items-center justify-center mx-auto mb-6">
                        <span class="text-3xl">🏨</span>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Hotel Reservations</h3>
                    <p class="text-gray-600">Luxury accommodations at unbeatable prices</p>
                </div>
                <!-- Service 3 -->
                <div class="text-center fade-in">
                    <div class="service-icon w-20 h-20 bg-gradient-to-r from-orange-500 to-red-600 rounded-full flex items-center justify-center mx-auto mb-6">
                        <span class="text-3xl">🗺️</span>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Tour Planning</h3>
                    <p class="text-gray-600">Customized itineraries tailored to your preferences</p>
                </div>
                <!-- Service 4 -->
                <div class="text-center fade-in">
                    <div class="service-icon w-20 h-20 bg-gradient-to-r from-purple-500 to-pink-600 rounded-full flex items-center justify-center mx-auto mb-6">
                        <span class="text-3xl">🎫</span>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Activity Booking</h3>
                    <p class="text-gray-600">Exciting experiences and adventures await</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Packages Section -->
    <section id="packages" class="py-20 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16 fade-in">
                <h2 class="text-4xl md:text-5xl font-bold gradient-text mb-4">Travel Packages</h2>
                <p class="text-xl text-gray-600 max-w-2xl mx-auto">Choose from our carefully crafted travel packages for the perfect getaway</p>
            </div>
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
                <!-- Package 1 -->
                <div class="bg-white rounded-2xl shadow-xl p-8 border-2 border-gray-100 hover:border-purple-300 transition-all fade-in">
                    <div class="text-center mb-6">
                        <div class="text-4xl mb-4">🌟</div>
                        <h3 class="text-2xl font-bold mb-2">Basic Explorer</h3>
                        <div class="text-4xl font-bold gradient-text">$999</div>
                        <p class="text-gray-500">per person</p>
                    </div>
                    <ul class="space-y-3 mb-8">
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> 5 Days / 4 Nights</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> 3-Star Hotel</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> Breakfast Included</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> Airport Transfer</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> City Tour</li>
                    </ul>
                    <button class="w-full bg-gradient-to-r from-purple-500 to-blue-500 text-white py-3 rounded-full font-semibold hover:shadow-lg transition-all">
                        Choose Package
                    </button>
                </div>
                <!-- Package 2 -->
                <div class="bg-white rounded-2xl shadow-xl p-8 border-2 border-purple-300 hover:border-purple-400 transition-all fade-in transform scale-105">
                    <div class="text-center mb-6">
                        <div class="bg-gradient-to-r from-purple-500 to-blue-500 text-white px-4 py-1 rounded-full text-sm font-semibold mb-4">Most Popular</div>
                        <div class="text-4xl mb-4">⭐</div>
                        <h3 class="text-2xl font-bold mb-2">Premium Adventure</h3>
                        <div class="text-4xl font-bold gradient-text">$1,999</div>
                        <p class="text-gray-500">per person</p>
                    </div>
                    <ul class="space-y-3 mb-8">
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> 7 Days / 6 Nights</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> 4-Star Hotel</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> All Meals Included</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> Private Transfer</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> Adventure Activities</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> Tour Guide</li>
                    </ul>
                    <button class="w-full bg-gradient-to-r from-purple-500 to-blue-500 text-white py-3 rounded-full font-semibold hover:shadow-lg transition-all pulse-glow">
                        Choose Package
                    </button>
                </div>
                <!-- Package 3 -->
                <div class="bg-white rounded-2xl shadow-xl p-8 border-2 border-gray-100 hover:border-purple-300 transition-all fade-in">
                    <div class="text-center mb-6">
                        <div class="text-4xl mb-4">💎</div>
                        <h3 class="text-2xl font-bold mb-2">Luxury Escape</h3>
                        <div class="text-4xl font-bold gradient-text">$3,999</div>
                        <p class="text-gray-500">per person</p>
                    </div>
                    <ul class="space-y-3 mb-8">
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> 10 Days / 9 Nights</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> 5-Star Resort</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> Gourmet Dining</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> Luxury Transfer</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> Spa & Wellness</li>
                        <li class="flex items-center"><span class="text-green-500 mr-2">✓</span> Personal Concierge</li>
                    </ul>
                    <button class="w-full bg-gradient-to-r from-purple-500 to-blue-500 text-white py-3 rounded-full font-semibold hover:shadow-lg transition-all">
                        Choose Package
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-20 bg-gray-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                <div class="fade-in">
                    <h2 class="text-4xl md:text-5xl font-bold gradient-text mb-6">About TravelAdvisors</h2>
                    <p class="text-xl text-gray-600 mb-6">
                        With over 15 years of experience in the travel industry, we've helped thousands of travelers create unforgettable memories around the world.
                    </p>
                    <p class="text-lg text-gray-600 mb-8">
                        Our team of expert travel advisors is passionate about crafting personalized experiences that exceed your expectations. From exotic destinations to cultural immersions, we make your dream trips a reality.
                    </p>
                    <div class="grid grid-cols-2 gap-6">
                        <div class="text-center">
                            <div class="text-3xl font-bold gradient-text">15+</div>
                            <div class="text-gray-600">Years Experience</div>
                        </div>
                        <div class="text-center">
                            <div class="text-3xl font-bold gradient-text">50K+</div>
                            <div class="text-gray-600">Happy Travelers</div>
                        </div>
                        <div class="text-center">
                            <div class="text-3xl font-bold gradient-text">200+</div>
                            <div class="text-gray-600">Destinations</div>
                        </div>
                        <div class="text-center">
                            <div class="text-3xl font-bold gradient-text">24/7</div>
                            <div class="text-gray-600">Support</div>
                        </div>
                    </div>
                </div>
                <div class="fade-in">
                    <div class="bg-gradient-to-br from-purple-400 to-blue-500 rounded-2xl p-8 text-white">
                        <div class="text-center">
                            <div class="text-8xl mb-6">🌎</div>
                            <h3 class="text-2xl font-bold mb-4">Ready to Explore?</h3>
                            <p class="mb-6">Join thousands of satisfied travelers who trust us with their adventures.</p>
                            <button class="bg-white text-purple-600 px-8 py-3 rounded-full font-semibold hover:bg-opacity-90 transition-all">
                                Start Your Journey
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-20 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16 fade-in">
                <h2 class="text-4xl md:text-5xl font-bold gradient-text mb-4">Get In Touch</h2>
                <p class="text-xl text-gray-600 max-w-2xl mx-auto">Ready to plan your next adventure? Contact our travel experts today!</p>
            </div>
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
                <div class="fade-in">
                    <div class="space-y-8">
                        <div class="flex items-center space-x-4">
                            <div class="w-12 h-12 bg-gradient-to-r from-purple-500 to-blue-500 rounded-full flex items-center justify-center">
                                <span class="text-white text-xl">📍</span>
                            </div>
                            <div>
                                <h3 class="font-semibold text-lg">Visit Us</h3>
                                <p class="text-gray-600">123 Travel Street, Adventure City, AC 12345</p>
                            </div>
                        </div>
                        <div class="flex items-center space-x-4">
                            <div class="w-12 h-12 bg-gradient-to-r from-purple-500 to-blue-500 rounded-full flex items-center justify-center">
                                <span class="text-white text-xl">📞</span>
                            </div>
                            <div>
                                <h3 class="font-semibold text-lg">Call Us</h3>
                                <p class="text-gray-600">+1 (555) 123-4567</p>
                            </div>
                        </div>
                        <div class="flex items-center space-x-4">
                            <div class="w-12 h-12 bg-gradient-to-r from-purple-500 to-blue-500 rounded-full flex items-center justify-center">
                                <span class="text-white text-xl">✉️</span>
                            </div>
                            <div>
                                <h3 class="font-semibold text-lg">Email Us</h3>
                                <p class="text-gray-600">info@traveladvisors.com</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="fade-in">
                    <form class="space-y-6" id="contactForm">
                        <div>
                            <input type="text" placeholder="Your Name" class="w-full px-4 py-3 rounded-lg border border-gray-300 focus:border-purple-500 focus:outline-none transition-colors">
                        </div>
                        <div>
                            <input type="email" placeholder="Your Email" class="w-full px-4 py-3 rounded-lg border border-gray-300 focus:border-purple-500 focus:outline-none transition-colors">
                        </div>
                        <div>
                            <input type="text" placeholder="Subject" class="w-full px-4 py-3 rounded-lg border border-gray-300 focus:border-purple-500 focus:outline-none transition-colors">
                        </div>
                        <div>
                            <textarea rows="5" placeholder="Your Message" class="w-full px-4 py-3 rounded-lg border border-gray-300 focus:border-purple-500 focus:outline-none transition-colors resize-none"></textarea>
                        </div>
                        <button type="submit" class="w-full bg-gradient-to-r from-purple-500 to-blue-500 text-white py-3 rounded-lg font-semibold hover:shadow-lg transition-all">
                            Send Message
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-12">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
                <div>
                    <div class="flex items-center space-x-3 mb-4">
                        <div class="w-10 h-10 bg-gradient-to-r from-blue-500 to-purple-600 rounded-lg flex items-center justify-center">
                            <span class="text-xl">🌍</span>
                        </div>
                        <div class="text-xl font-bold">TravelAdvisors</div>
                    </div>
                    <p class="text-gray-400">Your ultimate travel companion for unforgettable adventures around the world.</p>
                </div>
                <div>
                    <h3 class="font-semibold mb-4">Quick Links</h3>
                    <ul class="space-y-2 text-gray-400">
                        <li><a href="#home" class="hover:text-white transition-colors">Home</a></li>
                        <li><a href="#destinations" class="hover:text-white transition-colors">Destinations</a></li>
                        <li><a href="#services" class="hover:text-white transition-colors">Services</a></li>
                        <li><a href="#packages" class="hover:text-white transition-colors">Packages</a></li>
                    </ul>
                </div>
                <div>
                    <h3 class="font-semibold mb-4">Support</h3>
                    <ul class="space-y-2 text-gray-400">
                        <li><a href="#" class="hover:text-white transition-colors">Help Center</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Privacy Policy</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Terms of Service</a></li>
                        <li><a href="#contact" class="hover:text-white transition-colors">Contact Us</a></li>
                    </ul>
                </div>
                <div>
                    <h3 class="font-semibold mb-4">Follow Us</h3>
                    <div class="flex space-x-4">
                        <a href="#" class="w-10 h-10 bg-blue-600 rounded-full flex items-center justify-center hover:bg-blue-700 transition-colors">
                            <span>📘</span>
                        </a>
                        <a href="#" class="w-10 h-10 bg-blue-400 rounded-full flex items-center justify-center hover:bg-blue-500 transition-colors">
                            <span>🐦</span>
                        </a>
                        <a href="#" class="w-10 h-10 bg-pink-600 rounded-full flex items-center justify-center hover:bg-pink-700 transition-colors">
                            <span>📷</span>
                        </a>
                    </div>
                </div>
            </div>
            <div class="border-t border-gray-800 mt-8 pt-8 text-center text-gray-400">
                <p>&copy; 2024 TravelAdvisors. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Chat Widget -->
    <div class="fixed chat-widget z-50">
        <button id="chatBtn" class="chat-bubble w-16 h-16 bg-gradient-to-r from-purple-500 to-blue-500 rounded-full flex items-center justify-center text-white text-2xl shadow-lg hover:shadow-xl transition-all">
            💬
        </button>
    </div>

    <!-- Login Modal -->
    <div id="loginModal" class="fixed inset-0 bg-black bg-opacity-50 z-50 hidden flex items-center justify-center">
        <div class="bg-white rounded-2xl p-8 max-w-md w-full mx-4">
            <div class="text-center mb-6">
                <h2 class="text-2xl font-bold gradient-text">Welcome Back</h2>
                <p class="text-gray-600">Sign in to your account</p>
            </div>
            <form class="space-y-4">
                <div>
                    <input type="email" placeholder="Email Address" class="w-full px-4 py-3 rounded-lg border border-gray-300 focus:border-purple-500 focus:outline-none transition-colors">
                </div>
                <div>
                    <input type="password" placeholder="Password" class="w-full px-4 py-3 rounded-lg border border-gray-300 focus:border-purple-500 focus:outline-none transition-colors">
                </div>
                <button type="submit" class="w-full bg-gradient-to-r from-purple-500 to-blue-500 text-white py-3 rounded-lg font-semibold hover:shadow-lg transition-all">
                    Sign In
                </button>
            </form>
            <div class="text-center mt-4">
                <button id="closeModal" class="text-gray-500 hover:text-gray-700">Close</button>
            </div>
        </div>
    </div>

    <script>
        // Mobile Menu Toggle
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const mobileMenu = document.getElementById('mobileMenu');
        const closeMobileMenu = document.getElementById('closeMobileMenu');

        mobileMenuBtn.addEventListener('click', () => {
            mobileMenu.classList.add('active');
        });

        closeMobileMenu.addEventListener('click', () => {
            mobileMenu.classList.remove('active');
        });

        // Login Modal
        const loginBtn = document.getElementById('loginBtn');
        const loginModal = document.getElementById('loginModal');
        const closeModal = document.getElementById('closeModal');

        loginBtn.addEventListener('click', () => {
            loginModal.classList.remove('hidden');
        });

        closeModal.addEventListener('click', () => {
            loginModal.classList.add('hidden');
        });

        loginModal.addEventListener('click', (e) => {
            if (e.target === loginModal) {
                loginModal.classList.add('hidden');
            }
        });

        // Chat Widget
        const chatBtn = document.getElementById('chatBtn');
        chatBtn.addEventListener('click', () => {
            alert('Chat feature coming soon! Contact us at info@traveladvisors.com');
        });

        // Smooth Scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                    // Close mobile menu if open
                    mobileMenu.classList.remove('active');
                }
            });
        });

        // Fade in animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Contact Form
        const contactForm = document.getElementById('contactForm');
        contactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            alert('Thank you for your message! We will get back to you soon.');
            contactForm.reset();
        });

        // Package buttons
        document.querySelectorAll('button').forEach(button => {
            if (button.textContent.includes('Choose Package') || button.textContent.includes('Explore')) {
                button.addEventListener('click', () => {
                    alert('Package booking feature coming soon! Contact us for more information.');
                });
            }
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'977b0af0b7a2c869',t:'MTc1NjYyNzczNS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>

 
