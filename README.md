<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AeroTradeHub - Aviation Marketplace</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        .product-card {
            transition: all 0.3s ease;
            height: 100%;
        }
        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }
        .search-filter {
            transition: all 0.3s ease;
        }
        .search-filter:hover {
            background-color: #f1f5f9;
        }
        .gdpr-text {
            font-size: 0.75rem;
            line-height: 1.3;
        }
        .category-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, #003366, #0066cc);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
        }
        .tab-button {
            padding: 12px 24px;
            font-weight: 600;
            border-bottom: 3px solid transparent;
            transition: all 0.3s ease;
        }
        .tab-button.active {
            border-bottom-color: #0066cc;
            color: #0066cc;
        }
        .tab-content {
            display: none;
        }
        .tab-content.active {
            display: block;
        }
    </style>
</head>
<body class="bg-gray-50">
    <!-- Header -->
    <header class="bg-white shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <div class="flex items-center">
                    <i class="fas fa-plane-departure text-2xl text-blue-900 mr-2"></i>
                    <span class="font-bold text-xl text-blue-900">AeroTradeHub</span>
                </div>
                <nav class="hidden md:flex space-x-8">
                    <a href="#simulators" class="text-gray-700 hover:text-blue-900">Simulators</a>
                    <a href="#parts" class="text-gray-700 hover:text-blue-900">Aviation Parts</a>
                    <a href="#how-it-works" class="text-gray-700 hover:text-blue-900">How It Works</a>
                    <a href="#contact" class="text-gray-700 hover:text-blue-900">Contact</a>
                    <button onclick="openModal('loginModal')" class="bg-blue-900 text-white px-4 py-2 rounded hover:bg-blue-800">Sign In</button>
                </nav>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="bg-gradient-to-r from-blue-900 to-blue-700 text-white py-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col md:flex-row items-center">
                <div class="md:w-1/2 mb-10 md:mb-0">
                    <h1 class="text-4xl md:text-5xl font-bold mb-4">Aircraft Simulators & Aviation Parts Marketplace</h1>
                    <p class="text-xl mb-6 opacity-90">Buy, sell, and trade full-flight simulators and genuine aviation parts with trusted professionals worldwide.</p>
                    <div class="flex flex-col sm:flex-row gap-4">
                        <button onclick="openModal('signupModal')" class="bg-orange-500 hover:bg-orange-600 text-white font-semibold px-6 py-3 rounded transition">
                            List Your Equipment
                        </button>
                        <button onclick="document.getElementById('simulators').scrollIntoView({behavior: 'smooth'})" class="border-2 border-white text-white hover:bg-white hover:text-blue-900 font-semibold px-6 py-3 rounded transition">
                            Browse Inventory
                        </button>
                    </div>
                </div>
                <div class="md:w-1/2">
                    <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Boeing 737 Full Flight Simulator" class="rounded-lg shadow-xl w-full">
                </div>
            </div>
        </div>
    </section>

    <!-- Categories -->
    <section class="py-16 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <h2 class="text-3xl font-bold text-center mb-12">Equipment Categories</h2>
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8">
                <div class="text-center p-6">
                    <div class="category-icon mx-auto mb-4">
                        <i class="fas fa-plane"></i>
                    </div>
                    <h3 class="text-xl font-semibold mb-2">Full Flight Simulators</h3>
                    <p class="text-gray-600">FAA/EASA certified simulators for commercial, military, and business aviation.</p>
                </div>
                <div class="text-center p-6">
                    <div class="category-icon mx-auto mb-4">
                        <i class="fas fa-microchip"></i>
                    </div>
                    <h3 class="text-xl font-semibold mb-2">Avionics Components</h3>
                    <p class="text-gray-600">Radios, transponders, flight instruments, and electronic systems.</p>
                </div>
                <div class="text-center p-6">
                    <div class="category-icon mx-auto mb-4">
                        <i class="fas fa-cogs"></i>
                    </div>
                    <h3 class="text-xl font-semibold mb-2">Mechanical Parts</h3>
                    <p class="text-gray-600">Control systems, hydraulics, landing gear components, and structural parts.</p>
                </div>
                <div class="text-center p-6">
                    <div class="category-icon mx-auto mb-4">
                        <i class="fas fa-laptop"></i>
                    </div>
                    <h3 class="text-xl font-semibold mb-2">Software & Licenses</h3>
                    <p class="text-gray-600">Simulation software, databases, and licensing for flight training devices.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Simulators Marketplace -->
    <section id="simulators" class="py-16 bg-gray-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <h2 class="text-3xl font-bold text-center mb-8">Full Flight Simulators</h2>
            
            <!-- Search & Filters -->
            <div class="bg-white p-6 rounded-lg shadow mb-8">
                <div class="grid grid-cols-1 md:grid-cols-5 gap-4 mb-4">
                    <input type="text" placeholder="Search simulators..." class="col-span-2 px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                    <select class="px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                        <option>All Aircraft Types</option>
                        <option>Boeing 737</option>
                        <option>Airbus A320</option>
                        <option>Boeing 777</option>
                        <option>Cessna Citation</option>
                    </select>
                    <select class="px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                        <option>All Locations</option>
                        <option>North America</option>
                        <option>Europe</option>
                        <option>Asia</option>
                        <option>Australia</option>
                    </select>
                    <button class="bg-blue-900 hover:bg-blue-800 text-white font-semibold px-4 py-2 rounded transition">
                        <i class="fas fa-search"></i> Search
                    </button>
                </div>
                <div class="flex flex-wrap gap-2">
                    <span class="bg-blue-700 text-white text-sm px-3 py-1 rounded-full">Used</span>
                    <span class="bg-green-500 text-white text-sm px-3 py-1 rounded-full">New</span>
                    <span class="bg-orange-500 text-white text-sm px-3 py-1 rounded-full">For Sale</span>
                    <span class="bg-blue-500 text-white text-sm px-3 py-1 rounded-full">For Rent</span>
                </div>
            </div>

            <!-- Simulators Grid -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Simulator Listing 1 -->
                <div class="bg-white rounded-lg shadow product-card">
                    <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Boeing 737 Full Flight Simulator" class="w-full h-48 object-cover rounded-t-lg">
                    <div class="p-6">
                        <div class="flex justify-between items-start mb-2">
                            <h3 class="text-xl font-semibold">Boeing 737 MAX FFS Level D</h3>
                            <span class="bg-orange-500 text-white text-xs px-2 py-1 rounded">For Sale</span>
                        </div>
                        <p class="text-gray-600 text-sm mb-3">FAA/EASA Certified | Complete with 6-DOF motion system</p>
                        <div class="grid grid-cols-2 gap-4 mb-4 text-sm">
                            <div>
                                <span class="font-semibold">Aircraft:</span> Boeing 737 MAX
                            </div>
                            <div>
                                <span class="font-semibold">Certification:</span> Level D
                            </div>
                            <div>
                                <span class="font-semibold">Motion:</span> 6-DOF Electric
                            </div>
                            <div>
                                <span class="font-semibold">Location:</span> Miami, FL
                            </div>
                        </div>
                        <p class="text-gray-800 font-bold text-lg mb-4">$1,250,000</p>
                        <button onclick="openListingModal('simulator', 'Boeing 737 MAX FFS Level D', '1,250,000', 'Miami, FL', 'Complete Boeing 737 MAX Full Flight Simulator with FAA and EASA Level D certification. This turnkey solution includes the full-motion platform, collimated visual system, instructor operating station, and all necessary software licenses. The simulator has been maintained to the highest standards with regular inspections and updates. All systems are fully operational and ready for immediate deployment. Includes complete documentation, maintenance records, and training materials. Located in our climate-controlled facility in Miami with easy access to shipping and transportation. Willing to assist with disassembly, packaging, and logistics for international buyers.')" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-2 px-4 rounded transition">
                            View Details
                        </button>
                    </div>
                </div>

                <!-- Simulator Listing 2 -->
                <div class="bg-white rounded-lg shadow product-card">
                    <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Airbus A320 Full Flight Simulator" class="w-full h-48 object-cover rounded-t-lg">
                    <div class="p-6">
                        <div class="flex justify-between items-start mb-2">
                            <h3 class="text-xl font-semibold">Airbus A320neo FFS Level D</h3>
                            <span class="bg-green-500 text-white text-xs px-2 py-1 rounded">New</span>
                        </div>
                        <p class="text-gray-600 text-sm mb-3">Brand new delivery | Complete with EASA certification</p>
                        <div class="grid grid-cols-2 gap-4 mb-4 text-sm">
                            <div>
                                <span class="font-semibold">Aircraft:</span> Airbus A320neo
                            </div>
                            <div>
                                <span class="font-semibold">Certification:</span> Level D
                            </div>
                            <div>
                                <span class="font-semibold">Motion:</span> 6-DOF Hydraulic
                            </div>
                            <div>
                                <span class="font-semibold">Location:</span> Frankfurt, Germany
                            </div>
                        </div>
                        <p class="text-gray-800 font-bold text-lg mb-4">$1,420,000</p>
                        <button onclick="openListingModal('simulator', 'Airbus A320neo FFS Level D', '1,420,000', 'Frankfurt, Germany', 'Brand new Airbus A320neo Full Flight Simulator with EASA Level D certification. This state-of-the-art simulator features the latest generation 6-DOF hydraulic motion system, 200° field-of-view collimated visual display, and complete aircraft systems modeling. Includes instructor operating station with scenario management, performance monitoring, and debriefing capabilities. Factory warranty included with comprehensive maintenance package. Available for immediate delivery with professional installation and commissioning services available worldwide. Ideal for major airlines or large flight training organizations expanding their training capacity.')" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-2 px-4 rounded transition">
                            View Details
                        </button>
                    </div>
                </div>

                <!-- Simulator Listing 3 -->
                <div class="bg-white rounded-lg shadow product-card">
                    <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Boeing 777 Full Flight Simulator" class="w-full h-48 object-cover rounded-t-lg">
                    <div class="p-6">
                        <div class="flex justify-between items-start mb-2">
                            <h3 class="text-xl font-semibold">Boeing 777-300ER FFS Level D</h3>
                            <span class="bg-orange-500 text-white text-xs px-2 py-1 rounded">For Sale</span>
                        </div>
                        <p class="text-gray-600 text-sm mb-3">FAA Certified | Complete with maintenance records</p>
                        <div class="grid grid-cols-2 gap-4 mb-4 text-sm">
                            <div>
                                <span class="font-semibold">Aircraft:</span> Boeing 777-300ER
                            </div>
                            <div>
                                <span class="font-semibold">Certification:</span> Level D
                            </div>
                            <div>
                                <span class="font-semibold">Motion:</span> 6-DOF Electric
                            </div>
                            <div>
                                <span class="font-semibold">Location:</span> Vancouver, Canada
                            </div>
                        </div>
                        <p class="text-gray-800 font-bold text-lg mb-4">$1,850,000</p>
                        <button onclick="openListingModal('simulator', 'Boeing 777-300ER FFS Level D', '1,850,000', 'Vancouver, Canada', 'Complete Boeing 777-300ER Full Flight Simulator with FAA Level D certification. This high-fidelity simulator includes advanced aircraft systems modeling, realistic handling qualities, and comprehensive failure simulation capabilities. Features a 6-DOF electric motion system and wide-angle collimated visual system with global database. The simulator has been operated by a major airline training department with meticulous maintenance records available. All software is current with the latest aircraft configuration. Includes instructor operating station, maintenance training aids, and complete documentation package. Located in climate-controlled facility with loading dock access.')" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-2 px-4 rounded transition">
                            View Details
                        </button>
                    </div>
                </div>
            </div>

            <div class="text-center mt-12">
                <button onclick="document.getElementById('parts').scrollIntoView({behavior: 'smooth'})" class="bg-blue-900 hover:bg-blue-800 text-white font-semibold px-8 py-3 rounded transition mr-4">
                    View Aviation Parts
                </button>
                <button class="border-2 border-blue-900 text-blue-900 hover:bg-blue-900 hover:text-white font-semibold px-8 py-3 rounded transition">
                    View All Simulators
                </button>
            </div>
        </div>
    </section>

    <!-- Aviation Parts Marketplace -->
    <section id="parts" class="py-16 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <h2 class="text-3xl font-bold text-center mb-8">Aviation Parts</h2>
            
            <!-- Tabs for Part Categories -->
            <div class="flex flex-wrap justify-center mb-8 border-b border-gray-200">
                <button class="tab-button active mr-2" onclick="switchTab('all')">All Parts</button>
                <button class="tab-button" onclick="switchTab('avionics')">Avionics</button>
                <button class="tab-button" onclick="switchTab('controls')">Control Systems</button>
                <button class="tab-button" onclick="switchTab('instruments')">Flight Instruments</button>
            </div>
            
            <!-- Search & Filters -->
            <div class="bg-gray-50 p-6 rounded-lg shadow mb-8">
                <div class="grid grid-cols-1 md:grid-cols-5 gap-4 mb-4">
                    <input type="text" placeholder="Search parts..." class="col-span-2 px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                    <select class="px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                        <option>All Manufacturers</option>
                        <option>Garmin</option>
                        <option>Honeywell</option>
                        <option>Collins</option>
                        <option>Thales</option>
                    </select>
                    <select class="px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                        <option>All Locations</option>
                        <option>North America</option>
                        <option>Europe</option>
                        <option>Asia</option>
                        <option>Australia</option>
                    </select>
                    <button class="bg-blue-900 hover:bg-blue-800 text-white font-semibold px-4 py-2 rounded transition">
                        <i class="fas fa-search"></i> Search
                    </button>
                </div>
                <div class="flex flex-wrap gap-2">
                    <span class="bg-green-500 text-white text-sm px-3 py-1 rounded-full">New</span>
                    <span class="bg-blue-700 text-white text-sm px-3 py-1 rounded-full">Used</span>
                    <span class="bg-purple-500 text-white text-sm px-3 py-1 rounded-full">Refurbished</span>
                    <span class="bg-orange-500 text-white text-sm px-3 py-1 rounded-full">For Sale</span>
                </div>
            </div>

            <!-- Parts Grid -->
            <div id="partsContainer">
                <!-- All Parts Tab -->
                <div id="tab-all" class="tab-content active">
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                        <!-- Part 1 -->
                        <div class="bg-white rounded-lg shadow product-card">
                            <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Garmin G500 Avionics System" class="w-full h-48 object-cover rounded-t-lg">
                            <div class="p-6">
                                <div class="flex justify-between items-start mb-2">
                                    <h3 class="text-xl font-semibold">Garmin G500 Avionics Suite</h3>
                                    <span class="bg-orange-500 text-white text-xs px-2 py-1 rounded">For Sale</span>
                                </div>
                                <p class="text-gray-600 text-sm mb-3">Complete PFD, MFD, and GEA 71 Engine Indication System</p>
                                <div class="grid grid-cols-2 gap-4 mb-4 text-sm">
                                    <div>
                                        <span class="font-semibold">Manufacturer:</span> Garmin
                                    </div>
                                    <div>
                                        <span class="font-semibold">Condition:</span> Used
                                    </div>
                                    <div>
                                        <span class="font-semibold">Compatibility:</span> GA Aircraft
                                    </div>
                                    <div>
                                        <span class="font-semibold">Location:</span> Chicago, IL
                                    </div>
                                </div>
                                <p class="text-gray-800 font-bold text-lg mb-4">$18,500</p>
                                <button onclick="openListingModal('part', 'Garmin G500 Avionics Suite', '18,500', 'Chicago, IL', 'Complete Garmin G500 avionics suite including Primary Flight Display (PFD), Multi-Function Display (MFD), GEA 71 Engine Indication System, and all necessary sensors and wiring. System has been recently overhauled with updated software. Includes installation manual and wiring diagrams. Perfect for aircraft upgrades, simulator builds, or as replacement units for existing installations. All units are bench-tested and fully functional.')" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-2 px-4 rounded transition">
                                    View Details
                                </button>
                            </div>
                        </div>

                        <!-- Part 2 -->
                        <div class="bg-white rounded-lg shadow product-card">
                            <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Boeing 737 Control Yoke" class="w-full h-48 object-cover rounded-t-lg">
                            <div class="p-6">
                                <div class="flex justify-between items-start mb-2">
                                    <h3 class="text-xl font-semibold">Boeing 737 Control Yoke Assembly</h3>
                                    <span class="bg-purple-500 text-white text-xs px-2 py-1 rounded">Refurbished</span>
                                </div>
                                <p class="text-gray-600 text-sm mb-3">Complete with force feedback and trim controls</p>
                                <div class="grid grid-cols-2 gap-4 mb-4 text-sm">
                                    <div>
                                        <span class="font-semibold">Aircraft:</span> Boeing 737
                                    </div>
                                    <div>
                                        <span class="font-semibold">Condition:</span> Refurbished
                                    </div>
                                    <div>
                                        <span class="font-semibold">Type:</span> Control System
                                    </div>
                                    <div>
                                        <span class="font-semibold">Location:</span> Seattle, WA
                                    </div>
                                </div>
                                <p class="text-gray-800 font-bold text-lg mb-4">$6,200</p>
                                <button onclick="openListingModal('part', 'Boeing 737 Control Yoke Assembly', '6,200', 'Seattle, WA', 'Complete Boeing 737 control yoke assembly professionally refurbished to meet OEM specifications. Includes force feedback system, trim controls, autopilot disconnect, and all necessary sensors. Unit has been completely disassembled, inspected, and rebuilt with all worn components replaced. Tested for proper operation and force characteristics. Includes mounting hardware and installation documentation. Ideal for flight simulator builders or as a replacement unit for training devices. Comes with 1-year warranty on workmanship.')" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-2 px-4 rounded transition">
                                    View Details
                                </button>
                            </div>
                        </div>

                        <!-- Part 3 -->
                        <div class="bg-white rounded-lg shadow product-card">
                            <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Airbus A320 Instrument Panel" class="w-full h-48 object-cover rounded-t-lg">
                            <div class="p-6">
                                <div class="flex justify-between items-start mb-2">
                                    <h3 class="text-xl font-semibold">Airbus A320 Glass Cockpit Panel</h3>
                                    <span class="bg-green-500 text-white text-xs px-2 py-1 rounded">New</span>
                                </div>
                                <p class="text-gray-600 text-sm mb-3">Complete with PFD, ND, ECAM, and overhead panel</p>
                                <div class="grid grid-cols-2 gap-4 mb-4 text-sm">
                                    <div>
                                        <span class="font-semibold">Aircraft:</span> Airbus A320
                                    </div>
                                    <div>
                                        <span class="font-semibold">Condition:</span> New
                                    </div>
                                    <div>
                                        <span class="font-semibold">Type:</span> Instrument Panel
                                    </div>
                                    <div>
                                        <span class="font-semibold">Location:</span> Toulouse, France
                                    </div>
                                </div>
                                <p class="text-gray-800 font-bold text-lg mb-4">$28,900</p>
                                <button onclick="openListingModal('part', 'Airbus A320 Glass Cockpit Panel', '28,900', 'Toulouse, France', 'Brand new Airbus A320 glass cockpit panel set including Primary Flight Displays (PFD), Navigation Displays (ND), Engine and Crew Alerting System (ECAM), and complete overhead panel with backlit switches. Panels are genuine surplus units that have never been installed, complete with protective covers still in place. Includes all necessary connectors, mounting hardware, and documentation. Perfect for high-fidelity simulator builds or as display pieces for aviation enthusiasts. Units are stored in climate-controlled environment and available for immediate shipment.')" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-2 px-4 rounded transition">
                                    View Details
                                </button>
                            </div>
                        </div>

                        <!-- Part 4 -->
                        <div class="bg-white rounded-lg shadow product-card">
                            <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Honeywell Flight Control Computer" class="w-full h-48 object-cover rounded-t-lg">
                            <div class="p-6">
                                <div class="flex justify-between items-start mb-2">
                                    <h3 class="text-xl font-semibold">Honeywell Flight Control Computer</h3>
                                    <span class="bg-blue-700 text-white text-xs px-2 py-1 rounded">Used</span>
                                </div>
                                <p class="text-gray-600 text-sm mb-3">FCC-700 model with complete documentation</p>
                                <div class="grid grid-cols-2 gap-4 mb-4 text-sm">
                                    <div>
                                        <span class="font-semibold">Manufacturer:</span> Honeywell
                                    </div>
                                    <div>
                                        <span class="font-semibold">Model:</span> FCC-700
                                    </div>
                                    <div>
                                        <span class="font-semibold">Condition:</span> Used
                                    </div>
                                    <div>
                                        <span class="font-semibold">Location:</span> Phoenix, AZ
                                    </div>
                                </div>
                                <p class="text-gray-800 font-bold text-lg mb-4">$4,800</p>
                                <button onclick="openListingModal('part', 'Honeywell Flight Control Computer', '4,800', 'Phoenix, AZ', 'Genuine Honeywell Flight Control Computer (FCC-700) removed from service during scheduled maintenance. Unit has complete maintenance history and has been bench-tested to verify full functionality. Includes all documentation, software load information, and interface specifications. Ideal for simulator builders creating high-fidelity fly-by-wire systems or for educational institutions studying flight control systems. Unit is clean, properly packaged, and ready for immediate integration into your project.')" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-2 px-4 rounded transition">
                                    View Details
                                </button>
                            </div>
                        </div>

                        <!-- Part 5 -->
                        <div class="bg-white rounded-lg shadow product-card">
                            <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Boeing 747 Rudder Pedals" class="w-full h-48 object-cover rounded-t-lg">
                            <div class="p-6">
                                <div class="flex justify-between items-start mb-2">
                                    <h3 class="text-xl font-semibold">Boeing 747 Rudder Pedal Assembly</h3>
                                    <span class="bg-purple-500 text-white text-xs px-2 py-1 rounded">Refurbished</span>
                                </div>
                                <p class="text-gray-600 text-sm mb-3">Complete with toe brakes and position sensors</p>
                                <div class="grid grid-cols-2 gap-4 mb-4 text-sm">
                                    <div>
                                        <span class="font-semibold">Aircraft:</span> Boeing 747
                                    </div>
                                    <div>
                                        <span class="font-semibold">Condition:</span> Refurbished
                                    </div>
                                    <div>
                                        <span class="font-semibold">Type:</span> Control System
                                    </div>
                                    <div>
                                        <span class="font-semibold">Location:</span> Anchorage, AK
                                    </div>
                                </div>
                                <p class="text-gray-800 font-bold text-lg mb-4">$3,800</p>
                                <button onclick="openListingModal('part', 'Boeing 747 Rudder Pedal Assembly', '3,800', 'Anchorage, AK', 'Complete Boeing 747 rudder pedal assembly professionally refurbished to meet OEM specifications. Includes toe brake functionality, position sensors, and all necessary linkages. Unit has been completely disassembled, inspected, and rebuilt with all worn components replaced. Tested for proper operation and force characteristics. Includes mounting hardware and installation documentation. Ideal for flight simulator builders or as a replacement unit for training devices. Comes with 1-year warranty on workmanship.')" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-2 px-4 rounded transition">
                                    View Details
                                </button>
                            </div>
                        </div>

                        <!-- Part 6 -->
                        <div class="bg-white rounded-lg shadow product-card">
                            <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Collins Radio Stack" class="w-full h-48 object-cover rounded-t-lg">
                            <div class="p-6">
                                <div class="flex justify-between items-start mb-2">
                                    <h3 class="text-xl font-semibold">Collins Pro Line 21 Radio Stack</h3>
                                    <span class="bg-green-500 text-white text-xs px-2 py-1 rounded">New</span>
                                </div>
                                <p class="text-gray-600 text-sm mb-3">Complete COMM/NAV, Transponder, and Audio Panel</p>
                                <div class="grid grid-cols-2 gap-4 mb-4 text-sm">
                                    <div>
                                        <span class="font-semibold">Manufacturer:</span> Collins
                                    </div>
                                    <div>
                                        <span class="font-semibold">Condition:</span> New
                                    </div>
                                    <div>
                                        <span class="font-semibold">Compatibility:</span> Business Jets
                                    </div>
                                    <div>
                                        <span class="font-semibold">Location:</span> Melbourne, FL
                                    </div>
                                </div>
                                <p class="text-gray-800 font-bold text-lg mb-4">$12,500</p>
                                <button onclick="openListingModal('part', 'Collins Pro Line 21 Radio Stack', '12,500', 'Melbourne, FL', 'Brand new Collins Pro Line 21 radio stack including dual COMM/NAV units, Mode S transponder, and integrated audio control panel. Units are genuine surplus that have never been installed, complete with protective covers still in place. Includes all necessary connectors, mounting hardware, and documentation. Perfect for high-fidelity simulator builds or as display pieces for aviation enthusiasts. Units are stored in climate-controlled environment and available for immediate shipment. Technical specifications and interface documentation available upon request.')" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-2 px-4 rounded transition">
                                    View Details
                                </button>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Avionics Tab -->
                <div id="tab-avionics" class="tab-content">
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                        <div class="bg-white rounded-lg shadow product-card">
                            <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Garmin G500 Avionics System" class="w-full h-48 object-cover rounded-t-lg">
                            <div class="p-6">
                                <div class="flex justify-between items-start mb-2">
                                    <h3 class="text-xl font-semibold">Garmin G500 Avionics Suite</h3>
                                    <span class="bg-orange-500 text-white text-xs px-2 py-1 rounded">For Sale</span>
                                </div>
                                <p class="text-gray-600 text-sm mb-3">Complete PFD, MFD, and GEA 71 Engine Indication System</p>
                                <div class="grid grid-cols-2 gap-4 mb-4 text-sm">
                                    <div>
                                        <span class="font-semibold">Manufacturer:</span> Garmin
                                    </div>
                                    <div>
                                        <span class="font-semibold">Condition:</span> Used
                                    </div>
                                    <div>
                                        <span class="font-semibold">Compatibility:</span> GA Aircraft
                                    </div>
                                    <div>
                                        <span class="font-semibold">Location:</span> Chicago, IL
                                    </div>
                                </div>
                                <p class="text-gray-800 font-bold text-lg mb-4">$18,500</p>
                                <button onclick="openListingModal('part', 'Garmin G500 Avionics Suite', '18,500', 'Chicago, IL', 'Complete Garmin G500 avionics suite including Primary Flight Display (PFD), Multi-Function Display (MFD), GEA 71 Engine Indication System, and all necessary sensors and wiring. System has been recently overhauled with updated software. Includes installation manual and wiring diagrams. Perfect for aircraft upgrades, simulator builds, or as replacement units for existing installations. All units are bench-tested and fully functional.')" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-2 px-4 rounded transition">
                                    View Details
                                </button>
                            </div>
                        </div>
                        <div class="bg-white rounded-lg shadow product-card">
                            <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Collins Radio Stack" class="w-full h-48 object-cover rounded-t-lg">
                            <div class="p-6">
                                <div class="flex justify-between items-start mb-2">
                                    <h3 class="text-xl font-semibold">Collins Pro Line 21 Radio Stack</h3>
                                    <span class="bg-green-500 text-white text-xs px-2 py-1 rounded">New</span>
                                </div>
                                <p class="text-gray-600 text-sm mb-3">Complete COMM/NAV, Transponder, and Audio Panel</p>
                                <div class="grid grid-cols-2 gap-4 mb-4 text-sm">
                                    <div>
                                        <span class="font-semibold">Manufacturer:</span> Collins
                                    </div>
                                    <div>
                                        <span class="font-semibold">Condition:</span> New
                                    </div>
                                    <div>
                                        <span class="font-semibold">Compatibility:</span> Business Jets
                                    </div>
                                    <div>
                                        <span class="font-semibold">Location:</span> Melbourne, FL
                                    </div>
                                </div>
                                <p class="text-gray-800 font-bold text-lg mb-4">$12,500</p>
                                <button onclick="openListingModal('part', 'Collins Pro Line 21 Radio Stack', '12,500', 'Melbourne, FL', 'Brand new Collins Pro Line 21 radio stack including dual COMM/NAV units, Mode S transponder, and integrated audio control panel. Units are genuine surplus that have never been installed, complete with protective covers still in place. Includes all necessary connectors, mounting hardware, and documentation. Perfect for high-fidelity simulator builds or as display pieces for aviation enthusiasts. Units are stored in climate-controlled environment and available for immediate shipment. Technical specifications and interface documentation available upon request.')" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-2 px-4 rounded transition">
                                    View Details
                                </button>
                            </div>
                        </div>
                        <div class="bg-white rounded-lg shadow product-card">
                            <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Honeywell Flight Control Computer" class="w-full h-48 object-cover rounded-t-lg">
                            <div class="p-6">
                                <div class="flex justify-between items-start mb-2">
                                    <h3 class="text-xl font-semibold">Honeywell Flight Control Computer</h3>
                                    <span class="bg-blue-700 text-white text-xs px-2 py-1 rounded">Used</span>
                                </div>
                                <p class="text-gray-600 text-sm mb-3">FCC-700 model with complete documentation</p>
                                <div class="grid grid-cols-2 gap-4 mb-4 text-sm">
                                    <div>
                                        <span class="font-semibold">Manufacturer:</span> Honeywell
                                    </div>
                                    <div>
                                        <span class="font-semibold">Model:</span> FCC-700
                                    </div>
                                    <div>
                                        <span class="font-semibold">Condition:</span> Used
                                    </div>
                                    <div>
                                        <span class="font-semibold">Location:</span> Phoenix, AZ
                                    </div>
                                </div>
                                <p class="text-gray-800 font-bold text-lg mb-4">$4,800</p>
                                <button onclick="openListingModal('part', 'Honeywell Flight Control Computer', '4,800', 'Phoenix, AZ', 'Genuine Honeywell Flight Control Computer (FCC-700) removed from service during scheduled maintenance. Unit has complete maintenance history and has been bench-tested to verify full functionality. Includes all documentation, software load information, and interface specifications. Ideal for simulator builders creating high-fidelity fly-by-wire systems or for educational institutions studying flight control systems. Unit is clean, properly packaged, and ready for immediate integration into your project.')" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-2 px-4 rounded transition">
                                    View Details
                                </button>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Controls Tab -->
                <div id="tab-controls" class="tab-content">
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                        <div class="bg-white rounded-lg shadow product-card">
                            <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Boeing 737 Control Yoke" class="w-full h-48 object-cover rounded-t-lg">
                            <div class="p-6">
                                <div class="flex justify-between items-start mb-2">
                                    <h3 class="text-xl font-semibold">Boeing 737 Control Yoke Assembly</h3>
                                    <span class="bg-purple-500 text-white text-xs px-2 py-1 rounded">Refurbished</span>
                                </div>
                                <p class="text-gray-600 text-sm mb-3">Complete with force feedback and trim controls</p>
                                <div class="grid grid-cols-2 gap-4 mb-4 text-sm">
                                    <div>
                                        <span class="font-semibold">Aircraft:</span> Boeing 737
                                    </div>
                                    <div>
                                        <span class="font-semibold">Condition:</span> Refurbished
                                    </div>
                                    <div>
                                        <span class="font-semibold">Type:</span> Control System
                                    </div>
                                    <div>
                                        <span class="font-semibold">Location:</span> Seattle, WA
                                    </div>
                                </div>
                                <p class="text-gray-800 font-bold text-lg mb-4">$6,200</p>
                                <button onclick="openListingModal('part', 'Boeing 737 Control Yoke Assembly', '6,200', 'Seattle, WA', 'Complete Boeing 737 control yoke assembly professionally refurbished to meet OEM specifications. Includes force feedback system, trim controls, autopilot disconnect, and all necessary sensors. Unit has been completely disassembled, inspected, and rebuilt with all worn components replaced. Tested for proper operation and force characteristics. Includes mounting hardware and installation documentation. Ideal for flight simulator builders or as a replacement unit for training devices. Comes with 1-year warranty on workmanship.')" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-2 px-4 rounded transition">
                                    View Details
                                </button>
                            </div>
                        </div>
                        <div class="bg-white rounded-lg shadow product-card">
                            <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Boeing 747 Rudder Pedals" class="w-full h-48 object-cover rounded-t-lg">
                            <div class="p-6">
                                <div class="flex justify-between items-start mb-2">
                                    <h3 class="text-xl font-semibold">Boeing 747 Rudder Pedal Assembly</h3>
                                    <span class="bg-purple-500 text-white text-xs px-2 py-1 rounded">Refurbished</span>
                                </div>
                                <p class="text-gray-600 text-sm mb-3">Complete with toe brakes and position sensors</p>
                                <div class="grid grid-cols-2 gap-4 mb-4 text-sm">
                                    <div>
                                        <span class="font-semibold">Aircraft:</span> Boeing 747
                                    </div>
                                    <div>
                                        <span class="font-semibold">Condition:</span> Refurbished
                                    </div>
                                    <div>
                                        <span class="font-semibold">Type:</span> Control System
                                    </div>
                                    <div>
                                        <span class="font-semibold">Location:</span> Anchorage, AK
                                    </div>
                                </div>
                                <p class="text-gray-800 font-bold text-lg mb-4">$3,800</p>
                                <button onclick="openListingModal('part', 'Boeing 747 Rudder Pedal Assembly', '3,800', 'Anchorage, AK', 'Complete Boeing 747 rudder pedal assembly professionally refurbished to meet OEM specifications. Includes toe brake functionality, position sensors, and all necessary linkages. Unit has been completely disassembled, inspected, and rebuilt with all worn components replaced. Tested for proper operation and force characteristics. Includes mounting hardware and installation documentation. Ideal for flight simulator builders or as a replacement unit for training devices. Comes with 1-year warranty on workmanship.')" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-2 px-4 rounded transition">
                                    View Details
                                </button>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Instruments Tab -->
                <div id="tab-instruments" class="tab-content">
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                        <div class="bg-white rounded-lg shadow product-card">
                            <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Honeywell Flight Control Computer" class="w-full h-48 object-cover rounded-t-lg">
                            <div class="p-6">
                                <div class="flex justify-between items-start mb-2">
                                    <h3 class="text-xl font-semibold">Honeywell Flight Control Computer</h3>
                                    <span class="bg-blue-700 text-white text-xs px-2 py-1 rounded">Used</span>
                                </div>
                                <p class="text-gray-600 text-sm mb-3">FCC-700 model with complete documentation</p>
                                <div class="grid grid-cols-2 gap-4 mb-4 text-sm">
                                    <div>
                                        <span class="font-semibold">Manufacturer:</span> Honeywell
                                    </div>
                                    <div>
                                        <span class="font-semibold">Model:</span> FCC-700
                                    </div>
                                    <div>
                                        <span class="font-semibold">Condition:</span> Used
                                    </div>
                                    <div>
                                        <span class="font-semibold">Location:</span> Phoenix, AZ
                                    </div>
                                </div>
                                <p class="text-gray-800 font-bold text-lg mb-4">$4,800</p>
                                <button onclick="openListingModal('part', 'Honeywell Flight Control Computer', '4,800', 'Phoenix, AZ', 'Genuine Honeywell Flight Control Computer (FCC-700) removed from service during scheduled maintenance. Unit has complete maintenance history and has been bench-tested to verify full functionality. Includes all documentation, software load information, and interface specifications. Ideal for simulator builders creating high-fidelity fly-by-wire systems or for educational institutions studying flight control systems. Unit is clean, properly packaged, and ready for immediate integration into your project.')" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-2 px-4 rounded transition">
                                    View Details
                                </button>
                            </div>
                        </div>
                        <div class="bg-white rounded-lg shadow product-card">
                            <img src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Airbus A320 Instrument Panel" class="w-full h-48 object-cover rounded-t-lg">
                            <div class="p-6">
                                <div class="flex justify-between items-start mb-2">
                                    <h3 class="text-xl font-semibold">Airbus A320 Glass Cockpit Panel</h3>
                                    <span class="bg-green-500 text-white text-xs px-2 py-1 rounded">New</span>
                                </div>
                                <p class="text-gray-600 text-sm mb-3">Complete with PFD, ND, ECAM, and overhead panel</p>
                                <div class="grid grid-cols-2 gap-4 mb-4 text-sm">
                                    <div>
                                        <span class="font-semibold">Aircraft:</span> Airbus A320
                                    </div>
                                    <div>
                                        <span class="font-semibold">Condition:</span> New
                                    </div>
                                    <div>
                                        <span class="font-semibold">Type:</span> Instrument Panel
                                    </div>
                                    <div>
                                        <span class="font-semibold">Location:</span> Toulouse, France
                                    </div>
                                </div>
                                <p class="text-gray-800 font-bold text-lg mb-4">$28,900</p>
                                <button onclick="openListingModal('part', 'Airbus A320 Glass Cockpit Panel', '28,900', 'Toulouse, France', 'Brand new Airbus A320 glass cockpit panel set including Primary Flight Displays (PFD), Navigation Displays (ND), Engine and Crew Alerting System (ECAM), and complete overhead panel with backlit switches. Panels are genuine surplus units that have never been installed, complete with protective covers still in place. Includes all necessary connectors, mounting hardware, and documentation. Perfect for high-fidelity simulator builds or as display pieces for aviation enthusiasts. Units are stored in climate-controlled environment and available for immediate shipment.')" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-2 px-4 rounded transition">
                                    View Details
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="text-center mt-12">
                <button class="bg-blue-900 hover:bg-blue-800 text-white font-semibold px-8 py-3 rounded transition">
                    View All 89 Parts
                </button>
            </div>
        </div>
    </section>

    <!-- How It Works -->
    <section id="how-it-works" class="py-16 bg-gray-50">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
            <h2 class="text-3xl font-bold text-center mb-12">How AeroTradeHub Works</h2>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="text-center">
                    <div class="w-16 h-16 bg-blue-900 text-white rounded-full flex items-center justify-center text-2xl font-bold mx-auto mb-4">1</div>
                    <h3 class="text-xl font-semibold mb-3">Create Your Account</h3>
                    <p class="text-gray-600">Sign up as a seller or buyer with your professional information. Include your company details, location, and areas of expertise in aviation equipment.</p>
                </div>
                <div class="text-center">
                    <div class="w-16 h-16 bg-blue-900 text-white rounded-full flex items-center justify-center text-2xl font-bold mx-auto mb-4">2</div>
                    <h3 class="text-xl font-semibold mb-3">List or Find Equipment</h3>
                    <p class="text-gray-600">Sellers can list simulators and spare parts with detailed specifications. Buyers can search and filter by aircraft type, part category, price, and location.</p>
                </div>
                <div class="text-center">
                    <div class="w-16 h-16 bg-blue-900 text-white rounded-full flex items-center justify-center text-2xl font-bold mx-auto mb-4">3</div>
                    <h3 class="text-xl font-semibold mb-3">Connect & Negotiate</h3>
                    <p class="text-gray-600">Message sellers directly through our secure messaging system, make offers, and arrange details for your aviation equipment transactions.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-16 bg-white">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <h2 class="text-3xl font-bold text-center mb-12">Contact a Seller</h2>
            <div class="bg-gray-50 p-8 rounded-lg shadow">
                <form id="contactForm">
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Your Full Name *</label>
                            <input type="text" required class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                        </div>
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Your Email *</label>
                            <input type="email" required class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                        </div>
                    </div>
                    <div class="mb-6">
                        <label class="block text-sm font-medium text-gray-700 mb-2">Subject</label>
                        <input type="text" value="Inquiry about your equipment" class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                    </div>
                    <div class="mb-6">
                        <label class="block text-sm font-medium text-gray-700 mb-2">Your Message *</label>
                        <textarea rows="6" required class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900" placeholder="Hello, I'm interested in your aviation equipment and would like to know more details..."></textarea>
                    </div>
                    <div class="mb-6 gdpr-text">
                        <input type="checkbox" id="gdpr" required class="mr-2">
                        <label for="gdpr">I agree to the processing of my personal data as described in the Privacy Policy. Your information will only be used to respond to your inquiry and will not be shared with third parties without your consent. (GDPR compliant)</label>
                    </div>
                    <button type="submit" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-3 px-6 rounded transition">
                        Send Message
                    </button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white pt-12 pb-6">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-8 mb-8">
                <div>
                    <h3 class="text-xl font-bold mb-4 flex items-center">
                        <i class="fas fa-plane-departure mr-2"></i> AeroTradeHub
                    </h3>
                    <p class="mb-4 text-gray-300">The trusted marketplace for aviation professionals to buy, sell, and trade flight simulators and aviation parts worldwide.</p>
                    <div class="flex space-x-4">
                        <a href="#" class="text-gray-300 hover:text-white transition"><i class="fab fa-facebook-f"></i></a>
                        <a href="#" class="text-gray-300 hover:text-white transition"><i class="fab fa-twitter"></i></a>
                        <a href="#" class="text-gray-300 hover:text-white transition"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#" class="text-gray-300 hover:text-white transition"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
                <div>
                    <h4 class="font-semibold mb-4">Quick Links</h4>
                    <ul class="space-y-2 text-gray-300">
                        <li><a href="#simulators" class="hover:text-white transition">Simulators</a></li>
                        <li><a href="#parts" class="hover:text-white transition">Aviation Parts</a></li>
                        <li><a href="#how-it-works" class="hover:text-white transition">How It Works</a></li>
                        <li><a href="#" class="hover:text-white transition">Pricing</a></li>
                        <li><a href="#contact" class="hover:text-white transition">Contact</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="font-semibold mb-4">Equipment Types</h4>
                    <ul class="space-y-2 text-gray-300">
                        <li><a href="#" class="hover:text-white transition">Full Flight Simulators</a></li>
                        <li><a href="#" class="hover:text-white transition">Avionics Components</a></li>
                        <li><a href="#" class="hover:text-white transition">Control Systems</a></li>
                        <li><a href="#" class="hover:text-white transition">Flight Instruments</a></li>
                        <li><a href="#" class="hover:text-white transition">Hardware & Components</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="font-semibold mb-4">Stay Updated</h4>
                    <p class="text-gray-300 mb-4">Subscribe to receive alerts about new equipment listings.</p>
                    <form class="flex">
                        <input type="email" placeholder="Your email" class="px-4 py-2 w-full rounded-l focus:outline-none">
                        <button type="submit" class="bg-orange-500 hover:bg-orange-600 text-white px-4 py-2 rounded-r transition">
                            <i class="fas fa-paper-plane"></i>
                        </button>
                    </form>
                </div>
            </div>
            <div class="pt-8 border-t border-gray-700 text-center text-gray-400 text-sm">
                <p>&copy; 2023 AeroTradeHub. All rights reserved. | <a href="#" class="hover:text-white transition">Privacy Policy</a> | <a href="#" class="hover:text-white transition">Terms of Service</a></p>
                <p class="mt-2 gdpr-text">This website complies with GDPR regulations. We do not store personal data beyond what is necessary to facilitate inquiries between buyers and sellers. All communications are encrypted and protected.</p>
            </div>
        </div>
    </footer>

    <!-- Login Modal -->
    <div id="loginModal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 hidden">
        <div class="bg-white rounded-lg p-8 max-w-md w-full mx-4">
            <div class="flex justify-between items-center mb-6">
                <h3 class="text-2xl font-bold">Welcome Back</h3>
                <button onclick="closeModal('loginModal')" class="text-gray-500 hover:text-gray-700">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <form>
                <div class="mb-4">
                    <label class="block text-sm font-medium text-gray-700 mb-1">Email Address</label>
                    <input type="email" required class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                </div>
                <div class="mb-6">
                    <label class="block text-sm font-medium text-gray-700 mb-1">Password</label>
                    <input type="password" required class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                    <div class="flex justify-between mt-2">
                        <div>
                            <input type="checkbox" id="remember" class="mr-2">
                            <label for="remember" class="text-sm">Remember me</label>
                        </div>
                        <a href="#" class="text-blue-900 text-sm hover:underline">Forgot password?</a>
                    </div>
                </div>
                <button type="submit" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-3 px-6 rounded transition mb-4">
                    Sign In
                </button>
                <div class="text-center">
                    <p class="text-gray-600">Don't have an account? <button onclick="switchToModal('loginModal', 'signupModal')" class="text-blue-900 hover:underline">Register now</button></p>
                </div>
            </form>
        </div>
    </div>

    <!-- Signup Modal -->
    <div id="signupModal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 hidden">
        <div class="bg-white rounded-lg p-8 max-w-md w-full mx-4">
            <div class="flex justify-between items-center mb-6">
                <h3 class="text-2xl font-bold">Create Your Account</h3>
                <button onclick="closeModal('signupModal')" class="text-gray-500 hover:text-gray-700">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <form>
                <div class="grid grid-cols-2 gap-4 mb-4">
                    <div>
                        <label class="block text-sm font-medium text-gray-700 mb-1">First Name *</label>
                        <input type="text" required class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                    </div>
                    <div>
                        <label class="block text-sm font-medium text-gray-700 mb-1">Last Name *</label>
                        <input type="text" required class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                    </div>
                </div>
                <div class="mb-4">
                    <label class="block text-sm font-medium text-gray-700 mb-1">Job Title</label>
                    <input type="text" class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                </div>
                <div class="mb-4">
                    <label class="block text-sm font-medium text-gray-700 mb-1">Company Name</label>
                    <input type="text" class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                </div>
                <div class="mb-4">
                    <label class="block text-sm font-medium text-gray-700 mb-1">Business Email *</label>
                    <input type="email" required class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                </div>
                <div class="grid grid-cols-2 gap-4 mb-4">
                    <div>
                        <label class="block text-sm font-medium text-gray-700 mb-1">Password *</label>
                        <input type="password" required minlength="8" class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                    </div>
                    <div>
                        <label class="block text-sm font-medium text-gray-700 mb-1">Confirm Password *</label>
                        <input type="password" required class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                    </div>
                </div>
                <div class="mb-6 gdpr-text">
                    <input type="checkbox" id="terms" required class="mr-2">
                    <label for="terms">I agree to the <a href="#" class="text-blue-900 hover:underline">Terms of Service</a> and <a href="#" class="text-blue-900 hover:underline">Privacy Policy</a>. I understand that my information will be processed in accordance with GDPR regulations for the purpose of creating and maintaining my marketplace account.</label>
                </div>
                <button type="submit" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-3 px-6 rounded transition mb-4">
                    Create Account
                </button>
                <div class="text-center">
                    <p class="text-gray-600">Already have an account? <button onclick="switchToModal('signupModal', 'loginModal')" class="text-blue-900 hover:underline">Sign in</button></p>
                </div>
            </form>
        </div>
    </div>

    <!-- Listing Modal -->
    <div id="listingModal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 hidden">
        <div class="bg-white rounded-lg p-8 max-w-4xl w-full mx-4 max-h-screen overflow-y-auto">
            <div class="flex justify-between items-center mb-6">
                <h3 id="modalTitle" class="text-2xl font-bold">Equipment Details</h3>
                <button onclick="closeModal('listingModal')" class="text-gray-500 hover:text-gray-700">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div>
                    <img id="modalImage" src="https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg" alt="Equipment" class="w-full rounded-lg">
                </div>
                <div>
                    <div class="bg-orange-500 text-white text-sm px-3 py-1 rounded inline-block mb-3" id="modalStatus">For Sale</div>
                    <p class="text-gray-600 mb-2"><i class="fas fa-map-marker-alt mr-1"></i> <span id="modalLocation">Miami, FL</span></p>
                    
                    <div class="bg-gray-50 p-4 rounded-lg mb-6">
                        <div class="flex justify-between mb-2">
                            <span class="font-semibold">Price:</span>
                            <span class="text-2xl font-bold text-blue-900" id="modalPrice">$1,250,000</span>
                        </div>
                    </div>
                    
                    <div class="mb-6">
                        <h4 class="text-xl font-semibold mb-3">Description</h4>
                        <p id="modalDescription" class="text-gray-700"></p>
                    </div>
                    
                    <button onclick="openContactModal()" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-3 px-6 rounded transition mb-3">
                        <i class="fas fa-envelope mr-2"></i> Contact Seller
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Contact Modal -->
    <div id="contactModal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 hidden">
        <div class="bg-white rounded-lg p-8 max-w-md w-full mx-4">
            <div class="flex justify-between items-center mb-6">
                <h3 class="text-2xl font-bold">Send Message to Seller</h3>
                <button onclick="closeModal('contactModal')" class="text-gray-500 hover:text-gray-700">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <form id="modalContactForm">
                <div class="mb-4">
                    <label class="block text-sm font-medium text-gray-700 mb-1">Your Name</label>
                    <input type="text" required class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                </div>
                <div class="mb-4">
                    <label class="block text-sm font-medium text-gray-700 mb-1">Your Email</label>
                    <input type="email" required class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                </div>
                <div class="mb-4">
                    <label class="block text-sm font-medium text-gray-700 mb-1">Subject</label>
                    <input type="text" id="contactSubject" class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900">
                </div>
                <div class="mb-6">
                    <label class="block text-sm font-medium text-gray-700 mb-1">Your Message</label>
                    <textarea rows="5" required class="w-full px-4 py-2 border border-gray-300 rounded focus:ring-2 focus:ring-blue-900 focus:border-blue-900" placeholder="Hello, I'm interested in your equipment..."></textarea>
                </div>
                <div class="mb-6 gdpr-text">
                    <input type="checkbox" id="contactGdpr" required class="mr-2">
                    <label for="contactGdpr">I consent to the processing of my personal data for the purpose of this inquiry, in accordance with GDPR regulations.</label>
                </div>
                <button type="submit" class="w-full bg-blue-900 hover:bg-blue-800 text-white font-semibold py-3 px-6 rounded transition">
                    Send Message
                </button>
            </form>
        </div>
    </div>

    <script>
        // Modal Functions
        function openModal(modalId) {
            document.getElementById(modalId).classList.remove('hidden');
            document.body.style.overflow = 'hidden';
        }

        function closeModal(modalId) {
            document.getElementById(modalId).classList.add('hidden');
            document.body.style.overflow = 'auto';
        }

        function switchToModal(closeId, openId) {
            closeModal(closeId);
            openModal(openId);
        }

        // Tab switching for spare parts
        function switchTab(tabName) {
            // Hide all tabs
            document.querySelectorAll('.tab-content').forEach(tab => {
                tab.classList.remove('active');
            });
            // Remove active class from all buttons
            document.querySelectorAll('.tab-button').forEach(button => {
                button.classList.remove('active');
            });
            // Show selected tab
            document.getElementById('tab-' + tabName).classList.add('active');
            // Add active class to clicked button
            event.currentTarget.classList.add('active');
        }

        // Open listing modal with specific data
        function openListingModal(type, title, price, location, description) {
            document.getElementById('modalTitle').textContent = title;
            document.getElementById('modalPrice').textContent = '$' + price;
            document.getElementById('modalLocation').textContent = location;
            document.getElementById('modalDescription').textContent = description;
            
            // Set status badge based on price format
            const statusBadge = document.getElementById('modalStatus');
            if (price.includes('month')) {
                statusBadge.textContent = 'For Rent';
                statusBadge.className = 'bg-blue-500 text-white text-sm px-3 py-1 rounded inline-block mb-3';
            } else if (type === 'part') {
                // Extract condition from description or set default
                if (description.includes('New')) {
                    statusBadge.textContent = 'New';
                    statusBadge.className = 'bg-green-500 text-white text-sm px-3 py-1 rounded inline-block mb-3';
                } else if (description.includes('Refurbished')) {
                    statusBadge.textContent = 'Refurbished';
                    statusBadge.className = 'bg-purple-500 text-white text-sm px-3 py-1 rounded inline-block mb-3';
                } else {
                    statusBadge.textContent = 'Used';
                    statusBadge.className = 'bg-blue-700 text-white text-sm px-3 py-1 rounded inline-block mb-3';
                }
            } else {
                statusBadge.textContent = 'For Sale';
                statusBadge.className = 'bg-orange-500 text-white text-sm px-3 py-1 rounded inline-block mb-3';
            }
            
            // All images use the same free-to-use image from Pixabay
            document.getElementById('modalImage').src = 'https://cdn.pixabay.com/photo/2016/04/17/16/33/airplane-1335241_1280.jpg';
            
            document.getElementById('contactSubject').value = 'Inquiry: ' + title;
            
            openModal('listingModal');
        }

        // Open contact modal
        function openContactModal() {
            closeModal('listingModal');
            openModal('contactModal');
        }

        // Close modals when clicking outside
        document.querySelectorAll('.fixed.inset-0').forEach(modal => {
            modal.addEventListener('click', function(e) {
                if (e.target === this) {
                    this.classList.add('hidden');
                    document.body.style.overflow = 'auto';
                }
            });
        });

        // Form submission handlers
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Message sent successfully! In a real application, this would send your inquiry to the seller. The seller will contact you via email within 24 hours.');
            this.reset();
        });

        document.getElementById('modalContactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Message sent successfully! In a real application, this would send your inquiry to the seller. The seller will contact you via email within 24 hours.');
            closeModal('contactModal');
        });

        // Update GDPR text throughout the site
        document.addEventListener('DOMContentLoaded', function() {
            const gdprElements = document.querySelectorAll('.gdpr-text');
            gdprElements.forEach(el => {
                el.innerHTML = el.innerHTML.replace('GDPR compliant', '<strong>GDPR compliant</strong>') + ' This website adheres to General Data Protection Regulation (GDPR) requirements. We only collect the minimum personal data necessary to facilitate transactions between buyers and sellers, and all data is stored securely with encryption. You have the right to access, correct, or delete your personal information at any time.';
            });
        });
    </script>
</body>
</html>
