<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NutriNudge</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Bodoni+Moda:ital,opsz,wght@0,6..96,400..900;1,6..96,400..900&family=Fredoka:wght@400;500;600;700&family=Quicksand:wght@400;500;600;700&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        'sage-bg': '#DCE5B8',
                        'sage-bg-light': '#E5ECC5',
                        'lime-btn': '#C5DB68',
                        'lime-btn-hover': '#B6CC5B',
                        'dark-green': '#537D28',
                        'dark-green-hover': '#456B1F',
                        'dark-green-card': '#558028',
                        'title-dark': '#1A230A',
                    },
                    fontFamily: {
                        'serif-logo': ['"Bodoni Moda"', 'serif'],
                        'rounded': ['"Fredoka"', '"Quicksand"', 'sans-serif'],
                        'body': ['"Quicksand"', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background-color: #DCE5B8;
            font-family: 'Quicksand', sans-serif;
            color: #1A230A;
            overflow-x: hidden;
        }

        .figma-title {
            font-family: 'Italiana', serif;
            letter-spacing: -0.5px;
        }

        .figma-pill-nav {
            background-color: #B9CF5E;
            color: #FFFFFF;
            font-family: 'Fredoka', sans-serif;
            font-weight: 600;
            border-radius: 9999px;
            transition: all 0.2s ease-in-out;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
        }
        .figma-pill-nav:hover {
            background-color: #B2C953;
            transform: translateY(-1px);
        }
        .figma-pill-nav.active {
            background-color: #A3BA42;
            box-shadow: inset 0 2px 4px rgba(0,0,0,0.15);
        }

        .figma-menu-btn {
            background-color: #628B2C;
            color: #FFFFFF;
            font-family: 'Fredoka', sans-serif;
            font-weight: 500;
            border-radius: 9999px;
            transition: all 0.2s ease;
            box-shadow: 0 4px 6px rgba(0,0,0,0.08);
        }
        .figma-menu-btn:hover {
            background-color: #43671F;
            transform: scale(1.02);
            box-shadow: 0 6px 12px rgba(0,0,0,0.12);
        }

        .figma-card {
            background-color: #558028;
            border-radius: 24px;
            color: #FFFFFF;
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }

        .text-outline-style {
            color: #FFFFFF;
            font-weight: 600;
            text-shadow: 
                0px 0px 3px rgba(0, 0, 0, 0.4),
                1px 1px 2px rgba(0, 0, 0, 0.5);
        }

        .food-thumb {
            width: 140px;
            height: 140px;
            object-fit: cover;
            border-radius: 28px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.15);
            flex-shrink: 0;
        }
        /* Tablet (Screens 768px and up) */
            @media (min-width: 768px) {
            .food-thumb {
            width: 140px;
             height: 140px;
            }
        }

        /* Desktop (Screens 1024px and up) */
            @media (min-width: 1024px) {
            .food-thumb {
            width: 180px;
            height: 180px;
            }
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #DCE5B8;
        }
        ::-webkit-scrollbar-thumb {
            background: #558028;
            border-radius: 4px;
        }

    </style>
</head>
<body class="min-h-screen flex flex-col justify-between selection:bg-dark-green selection:text-white">
    <div class="max-w-6xl w-full mx-auto p-4 md:p-8 flex-grow flex flex-col">
        
        <!-- HEADER TOP BAR -->
        <header class="w-full text-center mb-4 md:mb-6">
            <!-- NutriNudge Main Title -->
            <h1 onclick="navigateTo('home')" class="figma-title text-5xl md:text-7xl lg:text-8xl text-title-dark font-normal cursor-pointer select-none inline-block hover:opacity-90 transition-opacity">
                NutriNudge
            </h1>
            <div class="w-full h-1 bg-white mt-3 md:mt-4 opacity-80 rounded-full"></div>
        </header>

        <!-- TOP NAVIGATION BAR -->
        <nav class="flex justify-center items-center gap-3 md:gap-8 mb-6 md:mb-10 px-2" id="top-nav">
            <button onclick="navigateTo('home')" id="nav-home" class="figma-pill-nav text-base md:text-2xl px-6 md:px-12 py-2 md:py-3 cursor-pointer">
                Home
            </button>
            <button onclick="navigateTo('about')" id="nav-about" class="figma-pill-nav text-base md:text-2xl px-6 md:px-12 py-2 md:py-3 cursor-pointer">
                About Us
            </button>
            <button onclick="navigateTo('contact')" id="nav-contact" class="figma-pill-nav text-base md:text-2xl px-6 md:px-12 py-2 md:py-3 cursor-pointer">
                Contact
            </button>
        </nav>

        <!-- MAIN VIEW -->
        <main class="flex-grow flex flex-col justify-center">

            <!-- HOME -->
            <section id="view-home" class="page-fade w-full my-auto py-4">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center min-h-[380px]">
                    
                    <!-- Left Buttons -->
                    <div class="flex flex-col gap-4 md:gap-6 items-start max-w-md w-full mx-auto md:mx-0">
                        <button onclick="startFoodSection('fruits-info')" class="figma-menu-btn text-xl md:text-3xl py-3 md:py-4 px-8 md:px-12 w-full sm:w-80 text-left flex items-center justify-between group">
                            <span>Fruits</span>
                            <span class="group-hover:translate-x-1 transition-transform"></span>
                        </button>
                        
                        <button onclick="startFoodSection('vegetables-info')" class="figma-menu-btn text-xl md:text-3xl py-3 md:py-4 px-8 md:px-12 w-full sm:w-80 text-left flex items-center justify-between group">
                            <span>Vegetables</span>
                            <span class="group-hover:translate-x-1 transition-transform"></span>
                        </button>
                        
                        <button onclick="startFoodSection('fruits-recipe')" class="figma-menu-btn text-xl md:text-3xl py-3 md:py-4 px-8 md:px-12 w-full sm:w-80 text-left flex items-center justify-between group">
                            <span>Recipe for Fruits</span>
                            <span class="group-hover:translate-x-1 transition-transform"></span>
                        </button>
                        
                        <button onclick="startFoodSection('vegetables-recipe')" class="figma-menu-btn text-xl md:text-3xl py-3 md:py-4 px-8 md:px-12 w-full sm:w-80 text-left flex items-center justify-between group">
                            <span>Recipe for Vegetables</span>
                            <span class="group-hover:translate-x-1 transition-transform"></span>
                        </button>
                    </div>

                    <!-- Logo-->
                    <img src="img/NutriNudgeLogo .png" class="rounded-full shadow-lg border-4 border-white w-72 h-72 object-cover" alt="NutriNudge Salad">
                    

                            </svg>
                            </div>
                        </div>
                    </div>

                </div>
            </section>

            <!-- ABOUT US -->
            <section id="view-about" class="page-fade hidden w-full my-auto py-2">
                <div class="figma-card p-6 md:p-10 max-w-4xl mx-auto">
                    <h2 class="font-rounded text-xl md:text-2xl font-bold mb-4 text-white">
                        Welcome to NutriNudge!
                    </h2>
                    
                    <div class="space-y-4 text-sm md:text-base leading-relaxed text-white/95 font-medium">
                        <p>
                            NutriNudge is a website dedicated to helping you discover delicious and nutritious fruit and vegetable salad recipes. We believe that eating healthy doesn't have to be boring or complicated. With simple ingredients, easy recipes, and helpful information, we make it easier to add more fruits and vegetables to your everyday meals.
                        </p>
                        <p>
                            Our website provides a variety of salad recipes, along with information about their health benefits, nutrients, and ingredients. Whether you're looking for a refreshing fruit salad, a colorful vegetable salad, or a healthy combination of both, NutriNudge has something for you.
                        </p>
                        <p>
                            Our goal is to inspire better food choices, one salad at a time. We want to make healthy eating enjoyable, accessible, and easy for everyone.
                        </p>
                        <p class="font-bold pt-2 text-white text-base md:text-lg">
                            NutriNudge — A little nudge toward a healthier you!
                        </p>
                    </div>
                </div>
            </section>

            <!-- CONTACT -->
            <section id="view-contact" class="page-fade hidden w-full my-auto py-2">
                <div class="figma-card p-6 md:p-10 max-w-4xl mx-auto">
                    <p class="text-sm md:text-base leading-relaxed mb-6 text-white/95 font-medium">
                        Have a question, suggestion, or just want to share your favorite salad recipe? We'd love to hear from you!<br>
                        At NutriNudge, we're always happy to receive feedback and ideas that can help make healthy eating easier and more enjoyable.
                    </p>

                    <div class="mb-6 space-y-2">
                        <h3 class="font-rounded text-lg md:text-xl font-bold text-white mb-2">Get in Touch</h3>
                        <p class="text-sm md:text-base">
                            <span class="font-semibold">Email:</span> 
                            <a href="mailto:nutrinudge@gmail.com" class="underline hover:text-lime-200 transition-colors">nutrinudge@gmail.com</a>
                        </p>
                        <p class="text-sm md:text-base"><span class="font-semibold">Phone:</span> +63 912 345 6789</p>
                        <p class="text-sm md:text-base"><span class="font-semibold">Facebook:</span> Nutri Nudge Ph</p>
                    </div>

                    <div class="pt-4 border-t border-white/20">
                        <p class="font-medium text-sm md:text-base">Thank you for checking NutriNudge!</p>
                        <p class="font-bold text-base md:text-lg mt-1">Let's make healthy choices one delicious salad at a time.</p>
                    </div>
                </div>
            </section>

            <!--RECIPE -->
            <section id="view-food-slider" class="page-fade hidden w-full my-auto py-2">
                
                <!-- Back & Next  -->
                <div class="flex justify-between items-center mb-6 max-w-5xl mx-auto px-2">
                    <button onclick="prevSlide()" id="btn-back" class="figma-pill-nav text-lg md:text-2xl px-8 md:px-14 py-2 cursor-pointer disabled:opacity-40 disabled:cursor-not-allowed">
                        Back
                    </button>
                
                    <span id="slider-category-title" class="font-rounded font-bold text-xl md:text-2xl text-dark-green hidden sm:inline-block">
                        Fruits Benefits
                    </span>

                    <button onclick="nextSlide()" id="btn-next" class="figma-pill-nav text-lg md:text-2xl px-8 md:px-14 py-2 cursor-pointer disabled:opacity-40 disabled:cursor-not-allowed">
                        Next
                    </button>
                </div>

                <!-- SLIDE -->
                <div id="slide-cards-content" class="max-w-5xl mx-auto">
                </div>

            </section>

        </main>

        <!-- FOOTER -->
        <footer class="text-center py-4 text-xs md:text-sm text-dark-green/80 font-medium">
            <p>&copy; 2026 NutriNudge. Navarro. </p>
        </footer>

    </div>
    <script src="script.js"></script>
</body>
</html>
