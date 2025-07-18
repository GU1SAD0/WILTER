<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WILTER Comercializadora y Servicios Integrales</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts - Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0B0C10; /* Fondo principal casi negro elegante */
            color: #FFFFFF; /* Texto principal blanco */
        }
        /* Custom styles for smooth transitions */
        .transition-all-ease {
            transition: all 0.3s ease-in-out;
        }
        .animate-fade-in {
            animation: fadeIn 1s ease-out forwards;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        /* Style for active navigation link */
        .nav-link.active {
            font-weight: 600;
            color: #00CFFF; /* Color de acento para enlaces activos */
            border-bottom: 2px solid #00CFFF;
        }

        /* Estilos para el menú móvil */
        .mobile-menu-button {
            display: none; /* Oculto por defecto en pantallas grandes */
        }
        .mobile-menu-hidden {
            display: none;
        }
        .mobile-menu-visible {
            display: flex; /* Mostrar como flex para apilar elementos */
            flex-direction: column;
            width: 100%;
        }

        /* Responsive adjustments for mobile menu button */
        @media (max-width: 767px) { /* Para pantallas pequeñas (móviles) */
            .mobile-menu-button {
                display: block; /* Mostrar el botón en móviles */
            }
            .nav-links-desktop { /* Ocultar los enlaces de escritorio en móviles */
                display: none;
            }
            /* La clase .mobile-menu-visible se aplicará/quitará con JS */
        }

        /* Estilos específicos para el carrusel de la galería */
        .carousel-container {
            position: relative;
            overflow: hidden;
        }
        .carousel-images {
            display: flex;
            overflow-x: scroll; /* Habilitar el scroll horizontal */
            scroll-behavior: smooth; /* Para una animación de scroll suave */
            -webkit-overflow-scrolling: touch; /* Para un scroll más suave en iOS */
            scroll-snap-type: x mandatory; /* Para que las imágenes se ajusten al centro */
        }
        .carousel-image-wrapper {
            flex: 0 0 auto; /* No crecer, no encoger, base auto */
            width: 100%; /* Una imagen por vista en móviles */
            scroll-snap-align: center;
            padding: 0.5rem; /* Espacio entre imágenes */
            box-sizing: border-box; /* Incluir padding en el ancho */
        }
        @media (min-width: 640px) { /* sm */
            .carousel-image-wrapper {
                width: 50%; /* Dos imágenes por vista en tabletas */
            }
        }
        @media (min-width: 1024px) { /* lg */
            .carousel-image-wrapper {
                width: 33.3333%; /* Tres imágenes por vista en escritorios */
            }
        }
        .carousel-image-wrapper img {
            width: 100%;
            height: 250px; /* Altura fija para las imágenes del carrusel */
            object-fit: cover;
            border-radius: 0.5rem; /* rounded-lg */
        }
        .carousel-button {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(0, 0, 0, 0.5);
            color: white;
            padding: 0.75rem;
            border-radius: 9999px; /* rounded-full */
            cursor: pointer;
            z-index: 10;
            transition: background-color 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
        }
        .carousel-button:hover {
            background-color: rgba(0, 0, 0, 0.7);
        }
        .carousel-button-left {
            left: 1rem;
        }
        .carousel-button-right {
            right: 1rem;
        }

        /* Estilos para el degradado de acento */
        .bg-gradient-accent {
            background-image: linear-gradient(to right, #00CFFF, #4AE4B0);
        }
    </style>
</head>
<body class="overflow-x-hidden antialiased">

    <!-- Header Section -->
    <header class="bg-[#0B0C10] shadow-sm py-4 sticky top-0 z-50">
        <nav class="container mx-auto px-4 flex justify-between items-center">
            <!-- Logo de WILTER -->
            <a href="#" class="flex items-center gap-2">
                <img src="[file:///C:/Users/tehac/Downloads/logo%20wilter%20puro%20logo.jpg](https://www.google.com/search?q=Mascarillas+con+Reservorio+ilustracion&sca_esv=edb9f998570affa4&udm=2&biw=1536&bih=730&ei=y154aJzUMf23qtsPuJv3iA8&ved=0ahUKEwjc5eWj68KOAxX9m2oFHbjNHfEQ4dUDCBE&uact=5&oq=Mascarillas+con+Reservorio+ilustracion&gs_lp=EgNpbWciJk1hc2NhcmlsbGFzIGNvbiBSZXNlcnZvcmlvIGlsdXN0cmFjaW9uSK8qULgEWKomcAF4AJABAJgBdaABsAmqAQM1Lje4AQPIAQD4AQGYAgKgAn7CAgoQABiABBhDGIoFwgIGEAAYBxgewgIFEAAYgATCAgQQABgewgIGEAAYCBgemAMAiAYBkgcDMS4xoAf5CbIHAzAuMbgHdsIHAzItMsgHDA&sclient=img&safe=active&ssui=on#vhid=LfM3y3ETGg1wJM&vssid=mosaic)" class="h-10 w-auto">
            </a>

            <!-- Desktop Navigation -->
            <ul class="hidden md:flex space-x-8 nav-links-desktop" id="nav-links-desktop">
                <li><a href="#inicio" class="nav-link text-[#B0BEC5] hover:text-[#00CFFF] transition-all-ease py-2">Inicio</a></li>
                <li><a href="#quienes-somos" class="nav-link text-[#B0BEC5] hover:text-[#00CFFF] transition-all-ease py-2">Quiénes Somos</a></li>
                <li><a href="#servicios" class="nav-link text-[#B0BEC5] hover:text-[#00CFFF] transition-all-ease py-2">Servicios</a></li>
                <li><a href="#productos" class="nav-link text-[#B0BEC5] hover:text-[#00CFFF] transition-all-ease py-2">Productos</a></li>
                <li><a href="#laparoscopia" class="nav-link text-[#B0BEC5] hover:text-[#00CFFF] transition-all-ease py-2">Equipo Laparoscopía</a></li>
                <li><a href="#galeria" class="nav-link text-[#B0BEC5] hover:text-[#00CFFF] transition-all-ease py-2">Galería</a></li>
                <li><a href="#clientes" class="nav-link text-[#B0BEC5] hover:text-[#00CFFF] transition-all-ease py-2">Clientes</a></li>
                <li><a href="#contacto" class="nav-link text-[#B0BEC5] hover:text-[#00CFFF] transition-all-ease py-2">Contacto</a></li>
            </ul>

            <!-- Mobile Menu Button -->
            <button id="mobile-menu-button" class="md:hidden p-2 rounded-md text-[#B0BEC5] hover:bg-[#1B1F27] focus:outline-none focus:ring-2 focus:ring-[#00CFFF]">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16" />
                </svg>
            </button>
        </nav>

        <!-- Mobile Navigation (Hidden by default) -->
        <div id="nav-links" class="hidden md:hidden bg-[#0B0C10] py-2 shadow-lg">
            <ul class="flex flex-col items-center space-y-4">
                <li><a href="#inicio" class="mobile-nav-link block text-[#B0BEC5] hover:text-[#00CFFF] py-2">Inicio</a></li>
                <li><a href="#quienes-somos" class="mobile-nav-link block text-[#B0BEC5] hover:text-[#00CFFF] py-2">Quiénes Somos</a></li>
                <li><a href="#servicios" class="mobile-nav-link block text-[#B0BEC5] hover:text-[#00CFFF] py-2">Servicios</a></li>
                <li><a href="#productos" class="mobile-nav-link block text-[#B0BEC5] hover:text-[#00CFFF] py-2">Productos</a></li>
                <li><a href="#laparoscopia" class="mobile-nav-link block text-[#B0BEC5] hover:text-[#00CFFF] py-2">Equipo Laparoscopía</a></li>
                <li><a href="#galeria" class="mobile-nav-link block text-[#B0BEC5] hover:text-[#00CFFF] py-2">Galería</a></li>
                <li><a href="#clientes" class="mobile-nav-link block text-[#B0BEC5] hover:text-[#00CFFF] py-2">Clientes</a></li>
                <li><a href="#contacto" class="mobile-nav-link block text-[#B0BEC5] hover:text-[#00CFFF] py-2">Contacto</a></li>
            </ul>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="inicio" class="relative bg-gradient-to-r from-[#00CFFF] to-[#4AE4B0] text-white py-20 md:py-32 flex items-center justify-center overflow-hidden">
        <!-- Background Image/Overlay -->
        <div class="absolute inset-0 bg-cover bg-center opacity-30" style="background-image: url('https://placehold.co/1920x1080/0A2342/FFFFFF?text=Soluciones+Integrales');"></div>
        <div class="absolute inset-0 bg-black opacity-40"></div>

        <div class="container mx-auto px-4 text-center relative z-10 animate-fade-in">
            <h1 class="text-4xl md:text-6xl font-extrabold leading-tight mb-4 drop-shadow-lg">
                WILTER: Tu Socio Estratégico en Soluciones Integrales
            </h1>
            <p class="text-lg md:text-xl mb-8 max-w-3xl mx-auto opacity-90 text-[#B0BEC5]">
                Excelencia en productos y servicios de mantenimiento, limpieza, instalaciones eléctricas y más.
                Construyendo confianza, un proyecto a la vez.
            </p>
            <a href="https://wa.me/524432009926" target="_blank" class="inline-flex items-center bg-[#00CFFF] hover:bg-[#4AE4B0] text-white font-bold py-3 px-8 rounded-full shadow-lg text-lg transition-all-ease transform hover:scale-105">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.11C6.23 15.414 4 13.736 4 12c0-4.418 4.03-8 9-8s9 3.582 9 8z" />
                </svg>
                Cotiza por WhatsApp
            </a>
        </div>
    </section>

    <!-- About Us Section -->
    <section id="quienes-somos" class="py-16 md:py-24 bg-[#101219] text-white">
        <div class="container mx-auto px-4">
            <h2 class="text-3xl md:text-4xl font-bold text-center text-[#00CFFF] mb-12 animate-fade-in">Quiénes Somos</h2>
            <div class="flex flex-col md:flex-row items-center gap-12">
                <div class="md:w-1/2 animate-fade-in">
                    <img src="C:\Users\tehac\Downloads\PROYECTOS visual studio code\1ra imagen.jpg" alt="Equipo WILTER" class="rounded-xl shadow-lg w-full h-auto object-cover">
                </div>
                <div class="md:w-1/2 text-[#B0BEC5] animate-fade-in">
                    <h3 class="text-2xl font-semibold text-[#4AE4B0] mb-4">Comercializadora y Servicios Integrales WILTER</h3>
                    <p class="mb-4 leading-relaxed">
                        Somos una empresa ubicada en Morelia, Michoacán, con operaciones desde septiembre de 2021. Nos destacamos en brindar productos y servicios de calidad excepcional en áreas como mantenimiento, limpieza, instalaciones eléctricas, reparación de maquinaria, venta de equipo médico y organización de eventos.
                    </p>
                    <p class="mb-4 leading-relaxed">
                        Valoramos la responsabilidad, el trabajo en equipo, la calidad y la rentabilidad, y nos esforzamos por satisfacer las necesidades de nuestros clientes con soluciones innovadoras y transparentes.
                    </p>

                    <h3 class="text-2xl font-semibold text-[#4AE4B0] mb-4 mt-8">Nuestra Misión</h3>
                    <p class="mb-4 leading-relaxed">
                        Nuestro objetivo es destacar como una empresa altamente competitiva, enfocada en brindar productos y servicios de calidad excepcional para satisfacer las necesidades de nuestros clientes tanto en el sector público como privado.
                    </p>

                    <h3 class="text-2xl font-semibold text-[#4AE4B0] mb-4 mt-8">Nuestra Visión</h3>
                    <p class="mb-4 leading-relaxed">
                        Nuestra visión es convertirnos en líderes indiscutibles en la comercialización de productos y servicios empresariales y médicos en el Estado de Michoacán para el año 2026. Nos comprometemos a estar siempre atentos a las necesidades de nuestros clientes y ofrecerles soluciones excepcionales.
                    </p>

                    <h3 class="2xl font-semibold text-[#4AE4B0] mb-4 mt-8">Nuestros Valores</h3>
                    <ul class="list-disc list-inside space-y-2 leading-relaxed">
                        <li>**Responsabilidad y Trabajo en Equipo:** Fomentamos la colaboración y el compromiso.</li>
                        <li>**Competitividad:** Buscamos la mejora constante para ofrecer lo mejor.</li>
                        <li>**Innovación:** Adaptamos y aplicamos las mejores prácticas y tecnologías.</li>
                        <li>**Calidad y Rentabilidad:** Garantizamos resultados óptimos y eficientes.</li>
                        <li>**Compromiso e Integridad:** Actuamos con ética y dedicación en cada proyecto.</li>
                        <li>**Honestidad y Transparencia:** Construimos relaciones basadas en la confianza mutua.</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="servicios" class="py-16 md:py-24 bg-[#1B1F27] text-white">
        <div class="container mx-auto px-4">
            <h2 class="text-3xl md:text-4xl font-bold text-center text-[#00CFFF] mb-12 animate-fade-in">Nuestros Servicios Integrales</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-8">
                <!-- Servicio: Mantenimiento General -->
                <div class="bg-[#101219] rounded-xl shadow-lg p-6 flex flex-col items-center text-center hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <div class="bg-gradient-accent p-4 rounded-full mb-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-3">Mantenimiento General</h3>
                    <p class="text-[#B0BEC5]">Servicio de mantenimiento en general para todo tipo de inmuebles y sistemas.</p>
                </div>

                <!-- Servicio: Limpieza de Inmuebles -->
                <div class="bg-[#101219] rounded-xl shadow-lg p-6 flex flex-col items-center text-center hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <div class="bg-gradient-accent p-4 rounded-full mb-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-3">Limpieza Profesional</h3>
                    <p class="text-[#B0BEC5]">Limpieza de inmuebles y limpieza profunda, garantizando ambientes impecables.</p>
                </div>

                <!-- Servicio: Instalaciones Eléctricas -->
                <div class="bg-[#101219] rounded-xl shadow-lg p-6 flex flex-col items-center text-center hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <div class="bg-gradient-accent p-4 rounded-full mb-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M13 10V3L4 14h7v7l9-11h-7z" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-3">Instalaciones Eléctricas</h3>
                    <p class="text-[#B0BEC5]">Servicios completos de instalaciones eléctricas y mantenimiento especializado.</p>
                </div>

                <!-- Servicio: Supervisión de personal de limpieza, seguridad y albañilería. -->
                <div class="bg-[#101219] rounded-xl shadow-lg p-6 flex flex-col items-center text-center hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <div class="bg-gradient-accent p-4 rounded-full mb-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M17 20h2a2 2 0 002-2V7a2 2 0 00-2-2h-2M8 10h.01M12 10h.01M16 10h.01M9 16H5a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v8a2 2 0 01-2 2h-5l-5 5v-5z" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-3">Supervisión de Personal</h3>
                    <p class="text-[#B0BEC5]">Supervisión experta de personal de limpieza, seguridad y albañilería.</p>
                </div>

                <!-- Servicio: Venta y mantenimiento de aires acondicionados -->
                <div class="bg-[#101219] rounded-xl shadow-lg p-6 flex flex-col items-center text-center hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <div class="bg-gradient-accent p-4 rounded-full mb-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M14.828 14.828a4 4 0 01-5.656 0M9 10h.01M15 10h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-3">Aires Acondicionados</h3>
                    <p class="text-[#B0BEC5]">Venta y mantenimiento profesional de sistemas de aires acondicionados.</p>
                </div>

                <!-- Servicio: Mantenimiento de edificios, pintura y remodelaciones -->
                <div class="bg-[#101219] rounded-xl shadow-lg p-6 flex flex-col items-center text-center hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <div class="bg-gradient-accent p-4 rounded-full mb-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-3">Edificios y Remodelaciones</h3>
                    <p class="text-[#B0BEC5]">Mantenimiento integral de edificios, pintura y remodelaciones de espacios.</p>
                </div>

                <!-- Servicio: Servicio de impermeabilización y mantenimiento de azoteas -->
                <div class="bg-[#101219] rounded-xl shadow-lg p-6 flex flex-col items-center text-center hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <div class="bg-gradient-accent p-4 rounded-full mb-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M13 10V3L4 14h7v7l9-11h-7z" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-3">Impermeabilización</h3>
                    <p class="text-[#B0BEC5]">Servicio de impermeabilización y mantenimiento de azoteas para protección duradera.</p>
                </div>

                <!-- Servicio: Comercialización y venta de productos de infraestructura educativa -->
                <div class="bg-[#101219] rounded-xl shadow-lg p-6 flex flex-col items-center text-center hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <div class="bg-gradient-accent p-4 rounded-full mb-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M8 14v3m4-3v3m4-3v3M3 21h18M3 10h18M3 7l9-4 9 4M4 10h16v11H4V10z" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-3">Infraestructura Educativa</h3>
                    <p class="text-[#B0BEC5]">Comercialización y venta de productos de infraestructura educativa (computadoras, mesabancos, escritorios, libreros, papelería).</p>
                </div>

                <!-- Servicio: Mantenimiento de cámaras de refrigeración y casa de maquinas -->
                <div class="bg-[#101219] rounded-xl shadow-lg p-6 flex flex-col items-center text-center hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <div class="bg-gradient-accent p-4 rounded-full mb-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M9 17v-2m3 2v-4m3 2v-6m2 8H7m6 1l4 2v3H6v-3l4-2m-2-4h.01M12 7h.01" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-3">Refrigeración y Maquinaria</h3>
                    <p class="text-[#B0BEC5]">Mantenimiento de cámaras de refrigeración y casas de máquinas.</p>
                </div>

                <!-- Servicio: Equipamiento especializado para infraestructuras educativas -->
                <div class="bg-[#101219] rounded-xl shadow-lg p-6 flex flex-col items-center text-center hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <div class="bg-gradient-accent p-4 rounded-full mb-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-3">Equipamiento Educativo</h3>
                    <p class="text-[#B0BEC5]">Equipamiento especializado para infraestructuras educativas.</p>
                </div>

                <!-- Servicio: Adaptación y remodelación de espacios educativos -->
                <div class="bg-[#101219] rounded-xl shadow-lg p-6 flex flex-col items-center text-center hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <div class="bg-gradient-accent p-4 rounded-full mb-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1.09l-1.09 10h-1.09L9 7z" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-3">Remodelación de Espacios Educativos</h3>
                    <p class="text-[#B0BEC5]">Adaptación y remodelación de espacios educativos (aulas, laboratorios, oficinas administrativas, auditorios, etc.).</p>
                </div>

                <!-- Servicio: Capacitación para el uso de equipamiento especializado en laboratorios educativos -->
                <div class="bg-[#101219] rounded-xl shadow-lg p-6 flex flex-col items-center text-center hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <div class="bg-gradient-accent p-4 rounded-full mb-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5s3.332.477 4.5 1.253v13C19.832 18.477 18.246 18 16.5 18s3.332.477-4.5 1.253" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-3">Capacitación Especializada</h3>
                    <p class="text-[#B0BEC5]">Servicios completos de capacitación para el uso de equipamiento especializado en laboratorios educativos.</p>
                </div>

                <!-- Servicio: Remodelación, mantenimiento y equipamiento de consultorios médicos. -->
                <div class="bg-[#101219] rounded-xl shadow-lg p-6 flex flex-col items-center text-center hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <div class="bg-gradient-accent p-4 rounded-full mb-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M4 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2V6zM14 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2V6zM4 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2v-2zM14 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2v-2z" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-3">Consultorios Médicos</h3>
                    <p class="text-[#B0BEC5]">Remodelación, mantenimiento y equipamiento de consultorios médicos.</p>
                </div>

                <!-- Servicio: Mantenimiento de pozos de agua -->
                <div class="bg-[#101219] rounded-xl shadow-lg p-6 flex flex-col items-center text-center hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <div class="bg-gradient-accent p-4 rounded-full mb-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.592 1L19 18H5l1.408-2.008c.513-.736 1.482-1.008 2.592-1.008H12z" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-3">Mantenimiento de Pozos de Agua</h3>
                    <p class="text-[#B0BEC5]">Servicios especializados para el mantenimiento y optimización de pozos de agua.</p>
                </div>

                <!-- NUEVO SERVICIO: Venta y mantenimiento de equipo dental -->
                <div class="bg-[#101219] rounded-xl shadow-lg p-6 flex flex-col items-center text-center hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <div class="bg-gradient-accent p-4 rounded-full mb-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2m-3 7h3m-3 4h3m-6-4h.01M9 16h.01" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-3">Equipo Dental</h3>
                    <p class="text-[#B0BEC5]">Venta y mantenimiento de equipo dental de última generación.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section id="productos" class="py-16 md:py-24 bg-[#0B0C10] text-white">
        <div class="container mx-auto px-4">
            <h2 class="text-3xl md:text-4xl font-bold text-center text-[#00CFFF] mb-12 animate-fade-in">Venta de Insumos Médicos y Equipo Especializado</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-8">
                <!-- Producto: Cubrebocas -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="C:\Users\tehac\Downloads\PROYECTOS visual studio code\imagen 2 cubre.jpeg" alt="Cubrebocas" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Cubrebocas</h3>
                    <p class="text-[#B0BEC5]">Protección esencial para ambientes de salud y seguridad.</p>
                </div>

                <!-- Producto: Concentradores de O2 -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="C:\Users\tehac\Downloads\PROYECTOS visual studio code\imagen 22222.jpeg" alt="Concentrador de Oxígeno" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Concentradores de O2</h3>
                    <p class="text-[#B0BEC5]">Equipos para suministro de oxígeno, alta eficiencia y fiabilidad.</p>
                </div>

                <!-- Producto: Narices -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="C:\Users\tehac\Downloads\PROYECTOS visual studio code\imagen 3 narizzzces.jpeg" alt="Narices" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Narices</h3>
                    <p class="text-[#B0BEC5]">Insumos médicos especializados para diversas aplicaciones.</p>
                </div>

                <!-- Producto: Filtros HEPA -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="C:\Users\tehac\Downloads\PROYECTOS visual studio code\imagen 4 hepa.jpeg" alt="Filtros HEPA" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Filtros HEPA</h3>
                    <p class="text-[#B0BEC5]">Filtros de alta eficiencia para purificación de aire en entornos críticos.</p>
                </div>

                <!-- Producto: Filtros para ventiladores -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="C:\Users\tehac\Downloads\PROYECTOS visual studio code\imagen 5 filtro vent.png" alt="Filtros para Ventiladores" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Filtros para Ventiladores</h3>
                    <p class="text-[#B0BEC5]">Componentes esenciales para el correcto funcionamiento de ventiladores médicos.</p>
                </div>

                <!-- Producto: Mascarillas con reservorio -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="C:\Users\tehac\Downloads\PROYECTOS visual studio code\imagen 777 ma.png" alt="Mascarillas con Reservorio" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Mascarillas con Reservorio</h3>
                    <p class="text-[#B0BEC5]">Dispositivos para administración de oxígeno con alta concentración.</p>
                </div>

                <!-- Producto: Vasos -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="C:\Users\tehac\Downloads\PROYECTOS visual studio code\imagen 6 vasos.jpg" alt="Vasos" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Vasos</h3>
                    <p class="text-[#B0BEC5]">Consumibles médicos de uso general y especializado.</p>
                </div>

                <!-- Producto: Puntas de alto flujo -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="https://placehold.co/150x150/101219/00CFFF?text=Puntas+Alto+Flujo" alt="Puntas de Alto Flujo" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Puntas de Alto Flujo</h3>
                    <p class="text-[#B0BEC5]">Para terapia respiratoria, garantizando un flujo constante y preciso.</p>
                </div>

                <!-- Producto: Cánulas nasales -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="https://placehold.co/150x150/101219/00CFFF?text=Canulas+Nasales" alt="Cánulas Nasales" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Cánulas Nasales</h3>
                    <p class="text-[#B0BEC5]">Para administración de oxígeno, cómodas y seguras.</p>
                </div>

                <!-- NUEVO: Todo tipo de cables para monitor DCG -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="https://placehold.co/150x150/101219/00CFFF?text=Cables+Monitor+DCG" alt="Cables para Monitor DCG" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Cables para Monitor DCG</h3>
                    <p class="text-[#B0BEC5]">Variedad de cables para monitores de electrocardiograma (DCG) de alta calidad.</p>
                </div>

                <!-- NUEVO: Sensores de oxígeno -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="https://placehold.co/150x150/101219/00CFFF?text=Sensores+Oxígeno" alt="Sensores de Oxígeno" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Sensores de Oxígeno</h3>
                    <p class="text-[#B0BEC5]">Sensores de oxígeno precisos y fiables para monitoreo de saturación.</p>
                </div>

                <!-- NUEVO: Circuitos ventilatorios ídem Medical y Fisher & Paykel -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="https://placehold.co/150x150/101219/00CFFF?text=Circuitos+Ventilatorios" alt="Circuitos Ventilatorios" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Circuitos Ventilatorios</h3>
                    <p class="text-[#B0BEC5]">Circuitos compatibles con equipos ídem Medical y Fisher & Paykel para ventilación asistida.</p>
                </div>

                <!-- NUEVO: Equipo médico -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="https://placehold.co/150x150/101219/00CFFF?text=Equipo+Médico" alt="Equipo Médico" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Equipo Médico</h3>
                    <p class="text-[#B0BEC5]">Amplia gama de equipo médico general para diversas especialidades.</p>
                </div>

                <!-- NUEVO: Ventiladores pulmonares -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="https://placehold.co/150x150/101219/00CFFF?text=Ventiladores+Pulmonares" alt="Ventiladores Pulmonares" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Ventiladores Pulmonares</h3>
                    <p class="text-[#B0BEC5]">Ventiladores de última generación para soporte respiratorio crítico.</p>
                </div>

                <!-- NUEVO: Máquinas de anestesia -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="https://placehold.co/150x150/101219/00CFFF?text=Maquinas+Anestesia" alt="Máquinas de Anestesia" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Máquinas de Anestesia</h3>
                    <p class="text-[#B0BEC5]">Equipos avanzados para la administración segura y controlada de anestesia.</p>
                </div>

                <!-- NUEVO: Desfibriladores -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="https://placehold.co/150x150/101219/00CFFF?text=Desfibriladores" alt="Desfibriladores" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Desfibriladores</h3>
                    <p class="text-[#B0BEC5]">Dispositivos esenciales para la reanimación cardíaca en situaciones de emergencia.</p>
                </div>

                <!-- NUEVO: Monitores de signos vitales -->
                <div class="bg-[#1B1F27] rounded-xl shadow-md p-6 flex flex-col items-center text-center hover:shadow-lg transform hover:-translate-y-1 transition-all-ease animate-fade-in">
                    <img src="https://placehold.co/150x150/101219/00CFFF?text=Monitores+Signos+Vitales" alt="Monitores de Signos Vitales" class="rounded-lg mb-4 w-32 h-32 object-cover">
                    <h3 class="text-xl font-semibold text-[#00CFFF] mb-2">Monitores de Signos Vitales</h3>
                    <p class="text-[#B0BEC5]">Monitores multiparamétricos para el seguimiento continuo de la salud del paciente.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Sección Renta de Equipo de Laparoscopía -->
    <section id="laparoscopia" class="py-16 md:py-24 bg-[#101219] text-white">
        <div class="container mx-auto px-4">
            <h2 class="text-3xl md:text-4xl font-bold text-center text-[#00CFFF] mb-12 animate-fade-in">Renta de Equipo de Laparoscopía</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Cirugía General -->
                <div class="bg-[#1B1F27] rounded-xl shadow-lg p-6 hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <h3 class="text-2xl font-semibold text-[#4AE4B0] mb-4">Cirugía General</h3>
                    <ul class="list-disc list-inside space-y-2 text-[#B0BEC5]">
                        <li>Colecistectomía Laparoscópica</li>
                        <li>Apendicectomía Laparoscópica</li>
                        <li>Funduplicatura Laparoscópica</li>
                        <li>Laparoscopía Diagnóstica</li>
                        <li>LigaSure</li>
                    </ul>
                </div>

                <!-- Ginecología -->
                <div class="bg-[#1B1F27] rounded-xl shadow-lg p-6 hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <h3 class="text-2xl font-semibold text-[#4AE4B0] mb-4">Ginecología</h3>
                    <ul class="list-disc list-inside space-y-2 text-[#B0BEC5]">
                        <li>Histerectomía Laparoscópica</li>
                        <li>Miomectomía Laparoscópica</li>
                        <li>Quiste de Ovario Laparoscópico</li>
                        <li>OTB Laparoscópica</li>
                        <li>Laparoscopía Diagnóstica</li>
                        <li>Histeroscopia</li>
                    </ul>
                </div>

                <!-- Urología - RTUP / UTI -->
                <div class="bg-[#1B1F27] rounded-xl shadow-lg p-6 hover:shadow-xl transform hover:-translate-y-2 transition-all-ease animate-fade-in">
                    <h3 class="text-2xl font-semibold text-[#4AE4B0] mb-4">Urología - RTUP / UTI</h3>
                    <ul class="list-disc list-inside space-y-2 text-[#B0BEC5]">
                        <li>RTUP Bipolar</li>
                        <li>Ureteroscopia, Ureterolitotripcia, Ureterorrenoscopia, Cistolitotripcia.</li>
                        <li>Ureterolitotripcia y Cistolitotripcia Láser</li>
                        <li>Percutánea de Riñón</li>
                        <li>Retiro de Catéter Doble J</li>
                        <li>Colocación de Catéter Doble J más Catéter.</li>
                        <li>Nefrectomía Laparoscópica</li>
                        <li>Quiste Renal por Laparoscopía</li>
                        <li>Orquidopexia Laparoscópica</li>
                        <li>Catéter Doble J</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Sección de Galería con Carrusel -->
    <section id="galeria" class="container mx-auto my-8 p-6 bg-[#0B0C10] rounded-lg shadow-md">
        <h2 class="text-3xl md:text-4xl font-bold text-center text-[#00CFFF] mb-6 animate-fade-in">Nuestra Galería de Servicios y Proyectos</h2>
        <p class="text-lg text-[#B0BEC5] leading-relaxed text-center mb-8">
            Explora algunas de nuestras mejores fotos de servicios y proyectos de comercialización.
        </p>

        <div class="carousel-container relative w-full max-w-6xl mx-auto">
            <div id="carousel-images" class="carousel-images flex overflow-x-auto rounded-lg shadow-xl">
                <div class="carousel-image-wrapper p-2">
                    <img src="https://placehold.co/600x400/1B1F27/00CFFF?text=Servicio+1" alt="Servicio 1" class="rounded-lg">
                    <p class="text-center text-[#B0BEC5] text-sm mt-2">Equipo de soporte al cliente</p>
                </div>
                <div class="carousel-image-wrapper p-2">
                    <img src="https://placehold.co/600x400/1B1F27/00CFFF?text=Proyecto+2" alt="Proyecto 2" class="rounded-lg">
                    <p class="text-center text-[#B0BEC5] text-sm mt-2">Colaboración en proyectos</p>
                </div>
                <div class="carousel-image-wrapper p-2">
                    <img src="https://placehold.co/600x400/1B1F27/00CFFF?text=Comercializacion+3" alt="Comercialización 3" class="rounded-lg">
                    <p class="text-center text-[#B0BEC5] text-sm mt-2">Sesión de estrategia de marketing</p>
                </div>
                <div class="carousel-image-wrapper p-2">
                    <img src="https://placehold.co/600x400/1B1F27/00CFFF?text=Instalacion+4" alt="Instalación 4" class="rounded-lg">
                    <p class="text-center text-[#B0BEC5] text-sm mt-2">Instalación de equipos tecnológicos</p>
                </div>
                <div class="carousel-image-wrapper p-2">
                    <img src="https://placehold.co/600x400/1B1F27/00CFFF?text=Presentacion+5" alt="Presentación 5" class="rounded-lg">
                    <p class="text-center text-[#B0BEC5] text-sm mt-2">Presentación de soluciones a clientes</p>
                </div>
                <div class="carousel-image-wrapper p-2">
                    <img src="https://placehold.co/600x400/1B1F27/00CFFF?text=Evento+6" alt="Evento 6" class="rounded-lg">
                    <p class="text-center text-[#B0BEC5] text-sm mt-2">Participación en eventos</p>
                </div>
                <div class="carousel-image-wrapper p-2">
                    <img src="https://placehold.co/600x400/1B1F27/00CFFF?text=Desarrollo+7" alt="Desarrollo 7" class="rounded-lg">
                    <p class="text-center text-[#B0BEC5] text-sm mt-2">Fase de desarrollo de producto</p>
                </div>
                <div class="carousel-image-wrapper p-2">
                    <img src="https://placehold.co/600x400/1B1F27/00CFFF?text=Oficina+8" alt="Oficina 8" class="rounded-lg">
                    <p class="text-center text-[#B0BEC5] text-sm mt-2">Nuestras modernas instalaciones</p>
                </div>
            </div>

            <!-- Botones de navegación del carrusel -->
            <button id="prev-button" class="carousel-button carousel-button-left">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M15 19l-7-7 7-7" />
                </svg>
            </button>
            <button id="next-button" class="carousel-button carousel-button-right">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7" />
                </svg>
            </button>
        </div>
    </section>

    <!-- Sección de Clientes -->
    <section id="clientes" class="py-16 md:py-24 bg-[#1B1F27] text-white">
        <div class="container mx-auto px-4 text-center animate-fade-in">
            <h2 class="text-3xl md:text-4xl font-bold text-[#00CFFF] mb-12">Nuestros Clientes</h2>
            <p class="text-lg text-[#B0BEC5] mb-8">
                Hemos tenido el honor de servir a una amplia gama de clientes satisfechos. Aquí algunos de ellos:
            </p>
            <div class="flex flex-wrap justify-center items-center gap-8">
                <img src="https://placehold.co/150x80/101219/00CFFF?text=Cliente+A" alt="Logo Cliente A" class="h-20 object-contain grayscale hover:grayscale-0 transition-all-ease">
                <img src="https://placehold.co/150x80/101219/00CFFF?text=Cliente+B" alt="Logo Cliente B" class="h-20 object-contain grayscale hover:grayscale-0 transition-all-ease">
                <img src="https://placehold.co/150x80/101219/00CFFF?text=Cliente+C" alt="Logo Cliente C" class="h-20 object-contain grayscale hover:grayscale-0 transition-all-ease">
                <img src="https://placehold.co/150x80/101219/00CFFF?text=Cliente+D" alt="Logo Cliente D" class="h-20 object-contain grayscale hover:grayscale-0 transition-all-ease">
            </div>
            <div class="mt-12">
                <h3 class="text-2xl font-semibold text-[#4AE4B0] mb-6">Distribuidores Autorizados</h3>
                <div class="flex flex-wrap justify-center items-center gap-8 text-[#B0BEC5] text-xl font-medium">
                    <span class="bg-[#101219] p-3 rounded-lg shadow-sm">Magnamed</span>
                    <span class="bg-[#101219] p-3 rounded-lg shadow-sm">Lorma</span>
                    <span class="bg-[#101219] p-3 rounded-lg shadow-sm">Idem Medical</span>
                    <span class="bg-[#101219] p-3 rounded-lg shadow-sm">Hergon</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contacto" class="py-16 md:py-24 bg-[#0B0C10] text-white">
        <div class="container mx-auto px-4 text-center animate-fade-in">
            <h2 class="text-3xl md:text-4xl font-bold mb-8 text-[#00CFFF]">Contáctanos</h2>
            <p class="text-lg md:text-xl mb-8 max-w-2xl mx-auto opacity-90 text-[#B0BEC5]">
                ¿Listo para transformar tus espacios o encontrar los insumos que necesitas?
                Contáctanos directamente para una cotización o consulta.
            </p>
            <a href="https://wa.me/524432009926" target="_blank" class="inline-flex items-center bg-[#00CFFF] hover:bg-[#4AE4B0] text-white font-bold py-4 px-10 rounded-full shadow-lg text-xl transition-all-ease transform hover:scale-105">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-7 w-7 mr-3" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.11C6.23 15.414 4 13.736 4 12c0-4.418 4.03-8 9-8s9 3.582 9 8z" />
                </svg>
                Chatea con Nosotros en WhatsApp
            </a>
            <p class="mt-8 text-lg opacity-80 text-[#B0BEC5]">
                También puedes encontrarnos en: <br>
                <span class="font-semibold">Aristeo Mercado #1172, Nueva Chapultepec, C.P. 58280, Morelia, Michoacán.</span>
            </p>

            <!-- Google Map Embed -->
            <div class="mt-12 w-full max-w-4xl mx-auto rounded-lg shadow-xl overflow-hidden">
                <iframe
                    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3756.241584879541!2d-101.2180807!3d19.923485!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x842d0e1b1d7d0a2d%3A0x6b7c2a7e7b7e7b7e!2sAristeo%20Mercado%201172%2C%20Nueva%20Chapultepec%2C%2058280%20Morelia%2C%20Mich.!5e0!3m2!1ses-419!2smx!4v1700000000000!5m2!1ses-419!2smx"
                    width="100%"
                    height="450"
                    style="border:0;"
                    allowfullscreen=""
                    loading="lazy"
                    referrerpolicy="no-referrer-when-downgrade"
                    class="rounded-lg"
                ></iframe>
            </div>
        </div>
    </section>

    <!-- Footer Section -->
    <footer class="bg-[#0B0C10] text-[#B0BEC5] py-8">
        <div class="container mx-auto px-4 text-center">
            <p class="mb-4">&copy; 2025 WILTER Comercializadora y Servicios Integrales. Todos los derechos reservados.</p>
            <div class="flex justify-center space-x-6">
                <!-- Social Media Icons (Placeholders) -->
                <a href="#" class="text-[#B0BEC5] hover:text-[#00CFFF] transition-all-ease">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.774 1.65 4.912 4.912.058 1.265.07 1.646.07 4.85s-.012 3.584-.07 4.85c-.148 3.252-1.65 4.774-4.912 4.912-1.265.058-1.646.07-4.85.07s-3.584-.012-4.85-.07c-3.252-.148-4.774-1.65-4.912-4.912-.058-1.265-.07-1.646-.07-4.85s.012-3.584.07-4.85c.148-3.252 1.65-4.774 4.912-4.912 1.265-.058 1.646-.07 4.85-.07zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.058 1.28-.072 1.689-.072 4.948s.014 3.668.072 4.948c.2 4.358 2.618 6.78 6.98 6.98 1.28.058 1.689.072 4.948.072s3.668-.014 4.948-.072c4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948s-.014-3.668-.072-4.947c-.2-4.359-2.622-6.78-6.981-6.981-1.28-.058-1.689-.072-4.947-.072zm0 7.378c-2.71 0-4.902 2.192-4.902 4.902s2.192 4.902 4.902 4.902 4.902-2.192 4.902-4.902-2.192-4.902-4.902-4.902zm0 8.007c-1.769 0-3.204-1.435-3.204-3.204s1.435-3.204 3.204-3.204 3.204 1.435 3.204 3.204-1.435 3.204-3.204 3.204zm5.325-7.878c-.964 0-1.745.78-1.745 1.746s.78 1.745 1.745 1.745 1.745-.78 1.745-1.745-.78-1.746-1.745-1.746z"/></svg>
                </a>
                <a href="#" class="text-[#B0BEC5] hover:text-[#00CFFF] transition-all-ease">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24"><path d="M22.675 0h-21.35c-.732 0-1.325.593-1.325 1.325v21.351c0 .732.593 1.325 1.325 1.325h21.35c.732 0 1.325-.593 1.325-1.325v-21.351c0-.732-.593-1.325-1.325-1.325zm-11.447 20.457h-3.33v-10.998h3.33v10.998zm-1.666-12.448c-.991 0-1.796-.805-1.796-1.796s.805-1.796 1.796-1.796 1.796.805 1.796 1.796-.805 1.796-1.796 1.796zm13.114 12.448h-3.33v-5.91c0-1.405-.027-3.219-1.958-3.219-1.961 0-2.261 1.532-2.261 3.119v6.01h-3.33s.045-9.872 0-10.998h3.33v1.576c.437-.745 1.56-1.53 3.288-1.53 3.518 0 4.167 2.307 4.167 6.684v6.268z"/></svg>
                </a>
                <a href="#" class="text-[#B0BEC5] hover:text-[#00CFFF] transition-all-ease">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24"><path d="M12 0c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm6.064 17.514c-.035.08-.094.148-.172.198-.079.05-.166.075-.262.075-.095 0-.18-.024-.256-.073-.075-.048-.133-.116-.17-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1-275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.362.273-.688.619-.978 1.037-.29.418-.539.86-.747 1.328-.037.078-.095.146-.17.194-.076.049-.161.073-.256.073-.096 0-.183-.025-.262-.075-.078-.05-.137-.118-.172-.194-.207-.468-.456-.91-.747-1.328-.29-.418-.616-.764-.978-1.037-.362-.273-.787-.41-1.275-.41-.487 0-.912.137-1.275.41-.
