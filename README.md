
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Network Equipment Gallery | Enterprise Networking</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
            padding-top: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.85), rgba(0, 0, 0, 0.8)), url('https://images.unsplash.com/photo-1558494949-ef010cbdcc31?ixlib=rb-4.0.3&auto=format&fit=crop&w=2069&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            text-align: center;
            padding: 3rem 1rem;
            margin-bottom: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .hero h1 {
            font-size: 2.2rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            color: #ffffff;
        }
        
        .hero p {
            font-size: 1.1rem;
            max-width: 700px;
            margin: 0 auto 1.5rem;
            opacity: 0.95;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
            color: #f0f0f0;
        }
        
        .hero-actions {
            display: flex;
            justify-content: center;
            gap: 1rem;
            flex-wrap: wrap;
        }
        
        .hero-btn {
            background-color: #3498db;
            color: white;
            padding: 0.7rem 1.5rem;
            border-radius: 4px;
            border: none;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            display: inline-block;
            text-decoration: none;
        }
        
        .hero-btn:hover {
            background-color: #2980b9;
            transform: translateY(-2px);
        }
        
        .btn-previous {
            background-color: #f39c12;
            color: white;
            padding: 0.7rem 1.5rem;
            border-radius: 4px;
            border: none;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            display: inline-block;
            text-decoration: none;
        }
        
        .btn-previous:hover {
            background-color: #d68910;
            transform: translateY(-2px);
        }
        
        .filter-section {
            background-color: white;
            padding: 1.2rem;
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
            margin-bottom: 2rem;
        }
        
        .filter-group {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
            margin-bottom: 1rem;
            justify-content: center;
        }
        
        .filter-btn {
            background-color: #ecf0f1;
            border: none;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s;
            font-size: 0.9rem;
        }
        
        .filter-btn:hover {
            background-color: #d5dbdd;
        }
        
        .filter-btn.active {
            background-color: #3498db;
            color: white;
        }
        
        .search-box {
            position: relative;
            width: 100%;
            max-width: 500px;
            margin: 0 auto;
        }
        
        .search-box input {
            padding: 0.6rem 1rem 0.6rem 2.5rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            width: 100%;
            font-size: 0.95rem;
        }
        
        .search-box i {
            position: absolute;
            left: 10px;
            top: 50%;
            transform: translateY(-50%);
            color: #7f8c8d;
        }
        
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.5rem;
            margin-bottom: 3rem;
        }
        
        .equipment-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s, box-shadow 0.3s;
            display: flex;
            flex-direction: column;
        }
        
        .equipment-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.12);
        }
        
        .equipment-img {
            height: 200px;
            width: 100%;
            object-fit: cover;
            border-bottom: 3px solid #3498db;
            background-color: #f8f9fa;
        }
        
        .equipment-info {
            padding: 1.2rem;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }
        
        .equipment-info h3 {
            font-size: 1.2rem;
            margin-bottom: 0.8rem;
            color: #2c3e50;
        }
        
        .equipment-specs {
            margin: 0.8rem 0;
            font-size: 0.9rem;
            color: #555;
            flex-grow: 1;
        }
        
        .spec-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.4rem;
            padding-bottom: 0.3rem;
            border-bottom: 1px solid #f0f0f0;
        }
        
        .spec-label {
            font-weight: 600;
            color: #2c3e50;
        }
        
        .equipment-actions {
            margin-top: 1rem;
            display: flex;
            justify-content: center;
        }
        
        .btn-details {
            background-color: #3498db;
            color: white;
            padding: 0.7rem 1.5rem;
            border-radius: 4px;
            border: none;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            width: 100%;
            text-align: center;
        }
        
        .btn-details:hover {
            background-color: #2980b9;
        }
        
        /* Modal Styles - Side-by-side layout */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.9);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            padding: 1rem;
        }
        
        .modal-content {
            background-color: white;
            border-radius: 8px;
            max-width: 1200px;
            width: 95%;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
            display: flex;
            flex-direction: column;
        }
        
        .close-modal {
            position: absolute;
            top: 10px;
            right: 15px;
            font-size: 2rem;
            color: white;
            cursor: pointer;
            z-index: 1001;
            background: rgba(0, 0, 0, 0.7);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .modal-body {
            display: flex;
            flex-direction: column;
            padding: 1.5rem;
        }
        
        @media (min-width: 992px) {
            .modal-body {
                flex-direction: row;
                gap: 2rem;
            }
        }
        
        .modal-images {
            flex: 1;
            min-width: 0;
        }
        
        .main-image-container {
            margin-bottom: 1rem;
        }
        
        .main-image {
            width: 100%;
            height: 350px;
            object-fit: cover;
            border-radius: 6px;
            background-color: #f8f9fa;
        }
        
        .thumbnail-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 0.5rem;
        }
        
        .thumbnail {
            width: 100%;
            height: 100px;
            object-fit: cover;
            border-radius: 4px;
            cursor: pointer;
            transition: all 0.3s;
            border: 2px solid transparent;
        }
        
        .thumbnail:hover {
            transform: scale(1.05);
            border-color: #3498db;
        }
        
        .thumbnail.active {
            border-color: #3498db;
            transform: scale(1.05);
        }
        
        .modal-details {
            flex: 1;
            min-width: 0;
        }
        
        .modal-details h2 {
            color: #2c3e50;
            margin-bottom: 1rem;
            font-size: 1.5rem;
        }
        
        .modal-specs {
            margin: 1rem 0;
        }
        
        .modal-actions {
            display: flex;
            gap: 1rem;
            margin-top: 1.5rem;
        }
        
        .btn-shop {
            background-color: #27ae60;
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 4px;
            border: none;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            text-decoration: none;
            display: inline-block;
            text-align: center;
            flex: 1;
        }
        
        .btn-shop:hover {
            background-color: #219653;
        }
        
        .btn-close-modal {
            background-color: #e74c3c;
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 4px;
            border: none;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            flex: 1;
        }
        
        .btn-close-modal:hover {
            background-color: #c0392b;
        }
        
        /* Mobile Responsive Styles */
        @media (max-width: 768px) {
            .hero {
                padding: 2rem 1rem;
                margin-bottom: 1.5rem;
            }
            
            .hero h1 {
                font-size: 1.8rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .hero-actions {
                flex-direction: column;
                align-items: center;
            }
            
            .gallery {
                grid-template-columns: 1fr;
                gap: 1.2rem;
            }
            
            .modal-body {
                flex-direction: column;
            }
            
            .modal-actions {
                flex-direction: column;
            }
            
            .thumbnail-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        @media (min-width: 768px) and (max-width: 1024px) {
            .gallery {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .thumbnail-grid {
                grid-template-columns: repeat(3, 1fr);
            }
        }
        
        /* No results message */
        .no-results {
            grid-column: 1 / -1;
            text-align: center;
            padding: 3rem;
            color: #7f8c8d;
        }
        
        .no-results i {
            font-size: 3rem;
            margin-bottom: 1rem;
            display: block;
        }
        
        /* Image counter */
        .image-counter {
            text-align: center;
            margin-top: 0.5rem;
            font-size: 0.9rem;
            color: #7f8c8d;
        }
        
        /* Network-specific colors */
        .network-badge {
            display: inline-block;
            padding: 0.2rem 0.5rem;
            background-color: #9b59b6;
            color: white;
            border-radius: 3px;
            font-size: 0.8rem;
            font-weight: 600;
            margin-left: 0.5rem;
        }
    </style>
</head>
<body>
    <section class="hero">
        <div class="container">
            <h1>Network Equipment Gallery</h1>
            <p>Browse our extensive collection of certified refurbished networking equipment. All equipment is thoroughly tested, cleaned, and comes with a warranty.</p>
            <div class="hero-actions">
                <button class="hero-btn" id="viewAllBtn">View All Equipment</button>
                <a href="https://snopitechstore.online/more-products/" class="btn-previous" target="_blank">
                    <i class="fas fa-arrow-left"></i> Back to Featured Products
                </a>
            </div>
        </div>
    </section>

    <main class="container">
        <section class="filter-section">
            <div class="filter-group">
                <button class="filter-btn active" data-filter="all">All Equipment</button>
                <button class="filter-btn" data-filter="cisco">Cisco</button>
                <button class="filter-btn" data-filter="juniper">Juniper</button>
                <button class="filter-btn" data-filter="aruba">Aruba</button>
                <button class="filter-btn" data-filter="dell">Dell</button>
                <button class="filter-btn" data-filter="hp">HP</button>
                <button class="filter-btn" data-filter="switch">Switches</button>
                <button class="filter-btn" data-filter="router">Routers</button>
                <button class="filter-btn" data-filter="firewall">Firewalls</button>
                <button class="filter-btn" data-filter="wireless">Wireless</button>
                <button class="filter-btn" data-filter="patch">Patch Panels</button>
            </div>
            <div class="search-box">
                <i class="fas fa-search"></i>
                <input type="text" id="searchInput" placeholder="Search equipment by model or spec...">
            </div>
        </section>

        <section class="gallery" id="equipmentGallery">
            <!-- Equipment cards will be generated by JavaScript -->
        </section>
    </main>

    <!-- Modal for equipment details -->
    <div class="modal" id="equipmentModal">
        <div class="close-modal" id="closeModal">&times;</div>
        <div class="modal-content">
            <div class="modal-body">
                <div class="modal-images">
                    <div class="main-image-container">
                        <img id="mainImage" class="main-image" src="" alt="Network Equipment Main View">
                    </div>
                    <div class="thumbnail-grid" id="thumbnailGrid">
                        <!-- Thumbnails will be generated by JavaScript -->
                    </div>
                    <div class="image-counter" id="imageCounter">Image 1 of 6</div>
                </div>
                <div class="modal-details">
                    <h2 id="modalTitle">Cisco Catalyst 9300 Switch <span class="network-badge">Switch</span></h2>
                    <div class="modal-specs" id="modalSpecs">
                        <!-- Specifications will be filled by JavaScript -->
                    </div>
                    <p id="modalDescription">This certified refurbished Cisco Catalyst 9300 switch offers enterprise-grade performance and security for modern networks.</p>
                    <div class="modal-actions">
                        <a href="https://snopitechstore.online/8-2/" target="_blank" class="btn-shop" id="shopNowBtn">
                            <i class="fas fa-shopping-cart"></i> Shop Now
                        </a>
                        <button class="btn-close-modal" id="closeModalBtn">Close</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Network equipment data with 18 products and 6 images each
        const networkEquipment = [
            {
                id: 1,
                brand: "cisco",
                type: "switch",
                name: "Cisco Catalyst 9300 Switch",
                images: [
                    "https://snopitechstore.online/public-images/C9300 pg1.png",
                    "https://snopitechstore.online/public-images/C9300 pg2.png",
                    "https://snopitechstore.online/public-images/C9300 pg3.png",
                    "https://snopitechstore.online/public-images/C9300 pg4.png",
                    "https://snopitechstore.online/public-images/C9300 pg5.png",
                    "https://snopitechstore.online/public-images/C9300 pg6.png"
                ],
                specs: {
                    ports: "48x 1G + 4x 10G SFP+",
                    throughput: "176 Gbps",
                    switching: "Stackable",
                    power: "Dual PSU",
                    management: "Cisco IOS XE",
                    condition: "Certified Refurbished"
                },
                description: "This certified refurbished Cisco Catalyst 9300 switch offers enterprise-grade performance and security for modern networks. Perfect for campus and branch deployments."
            },
            {
                id: 2,
                brand: "juniper",
                type: "router",
                name: "Juniper MX204 Router",
                images: [
                    "https://snopitechstore.online/public-images/Juniper MX204 Router1.png",
                    "https://snopitechstore.online/public-images/Juniper MX204 Router2.png",
                    "https://snopitechstore.online/public-images/Juniper MX204 Router3.png",
                    "https://snopitechstore.online/public-images/Juniper MX204 Router4.png",
                    "https://snopitechstore.online/public-images/Juniper MX204 Router5.png",
                    "https://snopitechstore.online/public-images/Juniper MX204 Router6.png"
                ],
                specs: {
                    ports: "8x 10/100G QSFP28",
                    throughput: "400 Gbps",
                    routing: "MPLS, BGP, OSPF",
                    power: "Dual PSU",
                    management: "Junos OS",
                    condition: "Grade A Refurbished"
                },
                description: "High-performance edge router designed for service provider and enterprise edge deployments. Features advanced routing capabilities."
            },
            {
                id: 3,
                brand: "aruba",
                type: "wireless",
                name: "Aruba 515 Access Point",
                images: [
                    "https://snopitechstore.online/public-images/aruba1.png",
                    "https://snopitechstore.online/public-images/aruba2.jpg",
                    "https://snopitechstore.online/public-images/aruba4.jpg",
                    "https://snopitechstore.online/public-images/aruba4-1.png",
                    "https://snopitechstore.online/public-images/aruba5.png",
                    "https://snopitechstore.online/public-images/aruba6.png"
                ],
                specs: {
                    standard: "Wi-Fi 6 (802.11ax)",
                    speed: "2.4 Gbps",
                    antennas: "Internal",
                    power: "PoE+",
                    management: "Aruba Central",
                    condition: "Certified Refurbished"
                },
                description: "Wi-Fi 6 access point with advanced RF management and security features. Ideal for high-density environments."
            },
            {
                id: 4,
                brand: "cisco",
                type: "firewall",
                name: "Cisco ASA 5525-X Firewall",
                images: [
                    "https://snopitechstore.online/wp-content/uploads/2026/01/Cisco-ASA-5525-X-Firewall-pg1.png",
                    "https://snopitechstore.online/public-images/Cisco ASA 5525-X Firewall pg2.png",
                    "https://snopitechstore.online/public-images/Cisco ASA 5525-X Firewall pg3.png",
                    "https://snopitechstore.online/public-images/Cisco ASA 5525-X Firewall pg4.png",
                    "https://snopitechstore.online/public-images/Cisco ASA 5525-X Firewall pg5.jpg",
                    "https://snopitechstore.online/public-images/Cisco ASA 5525-X Firewall pg6.png"
                ],
                specs: {
                    throughput: "4 Gbps",
                    vpn: "2 Gbps",
                    interfaces: "8x 1G + 2x 10G",
                    power: "Dual PSU",
                    features: "IPS, VPN, Threat Defense",
                    condition: "Grade A Refurbished"
                },
                description: "Next-generation firewall with advanced threat protection and VPN capabilities. Suitable for medium to large enterprises."
            },
            {
                id: 5,
                brand: "dell",
                type: "switch",
                name: "Dell PowerSwitch N3248",
                images: [
                    "https://snopitechstore.online/public-images/Dell PowerSwitch N3248 1.png",
                    "https://snopitechstore.online/public-images/Dell PowerSwitch N3248 2.png",
                    "https://snopitechstore.online/public-images/Dell PowerSwitch N3248 3.png",
                    "https://snopitechstore.online/public-images/Dell PowerSwitch N3248 4.jpg",
                    "https://snopitechstore.online/public-images/Dell PowerSwitch N3248 5.png",
                    "https://snopitechstore.online/public-images/Dell PowerSwitch N3248 6.png"
                ],
                specs: {
                    ports: "48x 1G + 4x 10G SFP+",
                    throughput: "176 Gbps",
                    switching: "Layer 3",
                    power: "Single PSU",
                    management: "Dell OS10",
                    condition: "Certified Refurbished"
                },
                description: "Enterprise-grade Layer 3 switch with high-performance switching and routing capabilities. Great value for money."
            },
            {
                id: 6,
                brand: "hp",
                type: "switch",
                name: "HP Aruba 2930F Switch",
                images: [
                    "https://snopitechstore.online/public-images/HP Aruba 2930F Switch1.png",
                    "https://snopitechstore.online/public-images/HP Aruba 2930F Switch2.png",
                    "https://snopitechstore.online/public-images/HP Aruba 2930F Switch3.png",
                    "https://snopitechstore.online/public-images/HP Aruba 2930F Switch4.png",
                    "https://snopitechstore.online/public-images/HP Aruba 2930F Switch5.png",
                    "https://snopitechstore.online/public-images/HP Aruba 2930F Switch6.png"
                ],
                specs: {
                    ports: "48x 1G + 4x 10G SFP+",
                    throughput: "176 Gbps",
                    switching: "Layer 3 Lite",
                    power: "Dual PSU",
                    management: "ArubaOS-Switch",
                    condition: "Grade A Refurbished"
                },
                description: "Advanced Layer 3 switch with Aruba's intelligent edge capabilities. Perfect for campus and branch networks."
            },
            {
                id: 7,
                brand: "cisco",
                type: "router",
                name: "Cisco ISR 4331 Router",
                images: [
                    "https://snopitechstore.online/public-images/Cisco ISR 4331 Router1.jpg",
                    "https://snopitechstore.online/public-images/Cisco ISR 4331 Router2.jpg",
                    "https://snopitechstore.online/public-images/Cisco ISR 4331 Router3.jpg",
                    "https://snopitechstore.online/public-images/Cisco ISR 4331 Router4.jpg",
                    "https://snopitechstore.online/public-images/Cisco ISR 4331 Router5.png",
                    "https://snopitechstore.online/public-images/Cisco ISR 4331 Router6.png"
                ],
                specs: {
                    ports: "4x 1G + 2x SFP",
                    throughput: "300 Mbps",
                    features: "SD-WAN, Security",
                    power: "Single PSU",
                    management: "Cisco IOS XE",
                    condition: "Refurbished"
                },
                description: "Integrated services router with advanced security and SD-WAN capabilities. Ideal for branch offices."
            },
            {
                id: 8,
                brand: "juniper",
                type: "switch",
                name: "Juniper EX4300 Switch",
                images: [
                    "https://snopitechstore.online/public-images/Juniper EX4300 Switch1.jpg",
                    "https://snopitechstore.online/public-images/Juniper EX4300 Switch2.png",
                    "https://snopitechstore.online/public-images/Juniper EX4300 Switch3.png",
                    "https://snopitechstore.online/public-images/Juniper EX4300 Switch4.png",
                    "https://snopitechstore.online/public-images/Juniper EX4300 Switch5.png",
                    "https://snopitechstore.online/public-images/Juniper EX4300 Switch6.png"
                ],
                specs: {
                    ports: "48x 1G + 4x 10G SFP+",
                    throughput: "240 Gbps",
                    switching: "Virtual Chassis",
                    power: "Dual PSU",
                    management: "Junos OS",
                    condition: "Grade A Refurbished"
                },
                description: "High-performance Ethernet switch with Virtual Chassis technology. Perfect for data center and campus deployments."
            },
            {
                id: 9,
                brand: "aruba",
                type: "switch",
                name: "Aruba 5406R Switch",
                images: [
                    "https://snopitechstore.online/public-images/Aruba 5406R Switch1.png",
                    "https://snopitechstore.online/public-images/Aruba 5406R Switch2.png",
                    "https://snopitechstore.online/public-images/Aruba 5406R Switch3.png",
                    "https://snopitechstore.online/public-images/Aruba 5406R Switch4.png",
                    "https://snopitechstore.online/public-images/Aruba 5406R Switch5.png",
                    "https://snopitechstore.online/public-images/Aruba 5406R Switch6.png"
                ],
                specs: {
                    slots: "6 Slots",
                    throughput: "1.28 Tbps",
                    switching: "Modular",
                    power: "Dual/Quad PSU",
                    management: "ArubaOS-CX",
                    condition: "Certified Refurbished"
                },
                description: "Modular chassis switch with high scalability and advanced features. Suitable for core network deployments."
            },
            {
                id: 10,
                brand: "cisco",
                type: "wireless",
                name: "Cisco Catalyst 9120 AP",
                images: [
                    "https://snopitechstore.online/public-images/Cisco Catalyst 9120 AP1.png",
                    "https://snopitechstore.online/public-images/Cisco Catalyst 9120 AP2.png",
                    "https://snopitechstore.online/public-images/Cisco Catalyst 9120 AP3.png",
                    "https://snopitechstore.online/public-images/Cisco Catalyst 9120 AP4.png",
                    "https://snopitechstore.online/public-images/Cisco Catalyst 9120 AP5.png",
                    "https://snopitechstore.online/public-images/Cisco Catalyst 9120 AP6.png"
                ],
                specs: {
                    standard: "Wi-Fi 6 (802.11ax)",
                    speed: "1.8 Gbps",
                    antennas: "Internal",
                    power: "PoE+",
                    management: "Cisco DNA Center",
                    condition: "Grade A Refurbished"
                },
                description: "Wi-Fi 6 access point with Cisco's advanced RF analytics and security. Perfect for enterprise wireless deployments."
            },
            {
                id: 11,
                brand: "dell",
                type: "patch",
                name: "Dell 48-Port Patch Panel",
                images: [
                    "https://snopitechstore.online/public-images/Dell 48-Port Patch Panel1.png",
                    "https://snopitechstore.online/public-images/Dell 48-Port Patch Panel2.png",
                    "https://snopitechstore.online/public-images/Dell 48-Port Patch Panel3.png",
                    "https://snopitechstore.online/public-images/Dell 48-Port Patch Panel4.png",
                    "https://snopitechstore.online/public-images/Dell 48-Port Patch Panel5.png",
                    "https://snopitechstore.online/public-images/Dell 48-Port Patch Panel6.png"
                ],
                specs: {
                    ports: "48 Ports",
                    type: "Cat6 Keystone",
                    mounting: "Rack Mount",
                    color: "Black",
                    cable: "UTP",
                    condition: "Refurbished"
                },
                description: "High-quality 48-port Cat6 patch panel for organized network cabling. Includes labeling areas for easy management."
            },
            {
                id: 12,
                brand: "hp",
                type: "router",
                name: "HP Aruba 7005 Router",
                images: [
                    "https://snopitechstore.online/public-images/HP Aruba 7005 Router1.png",
                    "https://snopitechstore.online/public-images/HP Aruba 7005 Router2.png",
                    "https://snopitechstore.online/public-images/HP Aruba 7005 Router3.png",
                    "https://snopitechstore.online/public-images/HP Aruba 7005 Router4.png",
                    "https://snopitechstore.online/public-images/HP Aruba 7005 Router5.png",
                    "https://snopitechstore.online/public-images/HP Aruba 7005 Router6.png"
                ],
                specs: {
                    ports: "8x 1G + 2x 10G",
                    throughput: "2 Gbps",
                    routing: "SD-WAN, BGP, OSPF",
                    power: "Dual PSU",
                    management: "ArubaOS",
                    condition: "Refurbished"
                },
                description: "SD-WAN optimized branch router with advanced security features. Perfect for distributed enterprise networks."
            },
            {
                id: 13,
                brand: "cisco",
                type: "switch",
                name: "Cisco Nexus 93180YC-FX",
                images: [
                    "https://snopitechstore.online/public-images/Cisco Nexus 93180YC-FX1.png",
                    "https://snopitechstore.online/public-images/Cisco Nexus 93180YC-FX2.png",
                    "https://snopitechstore.online/public-images/Cisco Nexus 93180YC-FX3.png",
                    "https://snopitechstore.online/public-images/Cisco Nexus 93180YC-FX4.png",
                    "https://snopitechstore.online/public-images/Cisco Nexus 93180YC-FX5.png",
                    "https://snopitechstore.online/public-images/Cisco Nexus 93180YC-FX6.png"
                ],
                specs: {
                    ports: "48x 25G + 6x 100G",
                    throughput: "3.6 Tbps",
                    switching: "Data Center",
                    power: "Dual PSU",
                    management: "NX-OS",
                    condition: "Grade A Refurbished"
                },
                description: "High-density data center switch with 25G/100G connectivity. Ideal for modern data center deployments."
            },
            {
                id: 14,
                brand: "juniper",
                type: "firewall",
                name: "Juniper SRX340 Firewall",
                images: [
                    "https://snopitechstore.online/public-images/Juniper SRX340 Firewall1.png",
                    "https://snopitechstore.online/public-images/Juniper SRX340 Firewall2.png",
                    "https://snopitechstore.online/public-images/Juniper SRX340 Firewall3.png",
                    "https://snopitechstore.online/public-images/Juniper SRX340 Firewall4.png",
                    "https://snopitechstore.online/public-images/Juniper SRX340 Firewall5.png",
                    "https://snopitechstore.online/public-images/Juniper SRX340 Firewall6.png"
                ],
                specs: {
                    throughput: "4 Gbps",
                    vpn: "1.5 Gbps",
                    interfaces: "8x 1G + 2x SFP",
                    power: "Single PSU",
                    features: "IPS, Application Security",
                    condition: "Refurbished"
                },
                description: "Next-generation firewall with advanced threat prevention and secure connectivity features."
            },
            {
                id: 15,
                brand: "aruba",
                type: "wireless",
                name: "Aruba 535 Access Point",
                images: [
                    "https://snopitechstore.online/public-images/Aruba 535 Access Point1.png",
                    "https://snopitechstore.online/public-images/Aruba 535 Access Point2.png",
                    "https://snopitechstore.online/public-images/Aruba 535 Access Point3.png",
                    "https://snopitechstore.online/public-images/Aruba 535 Access Point4.png",
                    "https://snopitechstore.online/public-images/Aruba 535 Access Point5.png",
                    "https://snopitechstore.online/public-images/Aruba 535 Access Point6.png"
                ],
                specs: {
                    standard: "Wi-Fi 6 (802.11ax)",
                    speed: "1.7 Gbps",
                    antennas: "External",
                    power: "PoE+",
                    management: "Aruba Instant",
                    condition: "Certified Refurbished"
                },
                description: "Outdoor-rated Wi-Fi 6 access point with extended temperature range. Perfect for outdoor deployments."
            },
            {
                id: 16,
                brand: "cisco",
                type: "patch",
                name: "Cisco 96-Port Patch Panel",
                images: [
                    "https://snopitechstore.online/public-images/Cisco 96-Port Patch Panel1.png",
                    "https://snopitechstore.online/public-images/Cisco 96-Port Patch Panel2.png",
                    "https://snopitechstore.online/public-images/Cisco 96-Port Patch Panel3.png",
                    "https://snopitechstore.online/public-images/Cisco 96-Port Patch Panel4.png",
                    "https://snopitechstore.online/public-images/Cisco 96-Port Patch Panel5.png",
                    "https://snopitechstore.online/public-images/Cisco 96-Port Patch Panel6.jpg"
                ],
                specs: {
                    ports: "96 Ports",
                    type: "Cat6A Keystone",
                    mounting: "2U Rack Mount",
                    color: "Gray",
                    cable: "Shielded",
                    condition: "Refurbished"
                },
                description: "High-density 96-port Cat6A patch panel with excellent cable management features. Ideal for data centers."
            },
            {
                id: 17,
                brand: "dell",
                type: "firewall",
                name: "Dell SonicWall TZ670",
                images: [
                    "https://snopitechstore.online/public-images/Dell SonicWall TZ6701.png",
                    "https://snopitechstore.online/public-images/Dell SonicWall TZ6702.jpg",
                    "https://snopitechstore.online/public-images/Dell SonicWall TZ6703.png",
                    "https://snopitechstore.online/public-images/Dell SonicWall TZ6704.png",
                    "https://snopitechstore.online/public-images/Dell SonicWall TZ6705.png",
                    "https://snopitechstore.online/public-images/Dell SonicWall TZ6706.png"
                ],
                specs: {
                    throughput: "2.5 Gbps",
                    vpn: "1 Gbps",
                    interfaces: "8x 1G + 2x SFP",
                    power: "Single PSU",
                    features: "UTM, Content Filtering",
                    condition: "Grade A Refurbished"
                },
                description: "Unified Threat Management firewall with comprehensive security features. Perfect for small to medium businesses."
            },
            {
                id: 18,
                brand: "hp",
                type: "patch",
                name: "HP 24-Port Patch Panel",
                images: [
                    "https://snopitechstore.online/public-images/HP 24-Port Patch Panel1.jpg",
                    "https://snopitechstore.online/public-images/HP 24-Port Patch Panel2.png",
                    "https://snopitechstore.online/public-images/HP 24-Port Patch Panel3.png",
                    "https://snopitechstore.online/public-images/HP 24-Port Patch Panel4.jpg",
                    "https://snopitechstore.online/public-images/HP 24-Port Patch Panel5.jpg",
                    "https://snopitechstore.online/public-images/HP 24-Port Patch Panel6.jpg"
                ],
                specs: {
                    ports: "24 Ports",
                    type: "Cat5e Keystone",
                    mounting: "1U Rack Mount",
                    color: "Black",
                    cable: "UTP",
                    condition: "Refurbished"
                },
                description: "Compact 24-port patch panel for small network installations. Easy to install and manage."
            }
        ];

        // DOM elements
        const gallery = document.getElementById('equipmentGallery');
        const filterButtons = document.querySelectorAll('.filter-btn');
        const searchInput = document.getElementById('searchInput');
        const modal = document.getElementById('equipmentModal');
        const closeModal = document.getElementById('closeModal');
        const closeModalBtn = document.getElementById('closeModalBtn');
        const mainImage = document.getElementById('mainImage');
        const thumbnailGrid = document.getElementById('thumbnailGrid');
        const imageCounter = document.getElementById('imageCounter');
        const modalTitle = document.getElementById('modalTitle');
        const modalSpecs = document.getElementById('modalSpecs');
        const modalDescription = document.getElementById('modalDescription');
        const viewAllBtn = document.getElementById('viewAllBtn');

        // Current image index for modal
        let currentImageIndex = 0;

        // Initialize gallery
        function renderGallery(equipmentToRender) {
            gallery.innerHTML = '';
            
            if (equipmentToRender.length === 0) {
                gallery.innerHTML = `
                    <div class="no-results">
                        <i class="fas fa-network-wired"></i>
                        <h3>No equipment found</h3>
                        <p>Try adjusting your search or filter criteria</p>
                    </div>
                `;
                return;
            }
            
            equipmentToRender.forEach(equipment => {
                const card = document.createElement('div');
                card.className = 'equipment-card';
                card.dataset.brand = equipment.brand;
                card.dataset.type = equipment.type;
                
                card.innerHTML = `
                    <img src="${equipment.images[0]}" alt="${equipment.name}" class="equipment-img" loading="lazy">
                    <div class="equipment-info">
                        <h3>${equipment.name} <span class="network-badge">${equipment.type}</span></h3>
                        <div class="equipment-specs">
                            <div class="spec-item">
                                <span class="spec-label">Type:</span>
                                <span>${equipment.type.charAt(0).toUpperCase() + equipment.type.slice(1)}</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Brand:</span>
                                <span>${equipment.brand.toUpperCase()}</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Key Spec:</span>
                                <span>${Object.values(equipment.specs)[0]}</span>
                            </div>
                            <div class="spec-item">
                                <span class="spec-label">Condition:</span>
                                <span>${equipment.specs.condition}</span>
                            </div>
                        </div>
                        <div class="equipment-actions">
                            <button class="btn-details view-details" data-id="${equipment.id}">View Details</button>
                        </div>
                    </div>
                `;
                
                gallery.appendChild(card);
                
                // Add image fallback
                const imgElement = card.querySelector('.equipment-img');
                const fallbackImage = "https://images.unsplash.com/photo-1558494949-ef010cbdcc31?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80";
                imgElement.onerror = function() {
                    this.src = fallbackImage;
                };
            });
            
            // Add event listeners to the new "View Details" buttons
            document.querySelectorAll('.view-details').forEach(button => {
                button.addEventListener('click', (e) => {
                    const equipmentId = parseInt(e.target.dataset.id);
                    openModal(equipmentId);
                });
            });
        }

        // Filter functionality
        function filterEquipment(filter) {
            if (filter === 'all') {
                return networkEquipment;
            }
            
            return networkEquipment.filter(equipment => 
                equipment.brand === filter || equipment.type === filter
            );
        }

        // Search functionality
        function searchEquipment(query) {
            const lowerQuery = query.toLowerCase();
            return networkEquipment.filter(equipment => 
                equipment.name.toLowerCase().includes(lowerQuery) ||
                equipment.type.toLowerCase().includes(lowerQuery) ||
                equipment.description.toLowerCase().includes(lowerQuery) ||
                Object.values(equipment.specs).some(value => 
                    value.toString().toLowerCase().includes(lowerQuery)
                )
            );
        }

        // Update thumbnail selection
        function updateThumbnailSelection(index) {
            const thumbnails = thumbnailGrid.querySelectorAll('.thumbnail');
            thumbnails.forEach((thumb, i) => {
                if (i === index) {
                    thumb.classList.add('active');
                } else {
                    thumb.classList.remove('active');
                }
            });
        }

        // Open modal with equipment details
        function openModal(equipmentId) {
            const equipment = networkEquipment.find(e => e.id === equipmentId);
            
            if (!equipment) return;
            
            // Reset image index
            currentImageIndex = 0;
            
            // Set main image
            mainImage.src = equipment.images[0];
            
            // Clear and populate thumbnails
            thumbnailGrid.innerHTML = '';
            equipment.images.forEach((image, index) => {
                const thumbnail = document.createElement('img');
                thumbnail.src = image;
                thumbnail.alt = `${equipment.name} - View ${index + 1}`;
                thumbnail.className = `thumbnail ${index === 0 ? 'active' : ''}`;
                thumbnail.dataset.index = index;
                
                thumbnail.addEventListener('click', () => {
                    mainImage.src = image;
                    currentImageIndex = index;
                    updateThumbnailSelection(index);
                    updateImageCounter();
                });
                
                // Add fallback for thumbnail
                thumbnail.onerror = function() {
                    this.src = "https://images.unsplash.com/photo-1558494949-ef010cbdcc31?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80";
                };
                
                thumbnailGrid.appendChild(thumbnail);
            });
            
            // Update image counter
            updateImageCounter();
            
            // Set equipment details
            modalTitle.innerHTML = `${equipment.name} <span class="network-badge">${equipment.type}</span>`;
            modalDescription.textContent = equipment.description;
            
            // Build specs HTML
            let specsHTML = '';
            for (const [key, value] of Object.entries(equipment.specs)) {
                const label = key.charAt(0).toUpperCase() + key.slice(1);
                specsHTML += `
                    <div class="spec-item">
                        <span class="spec-label">${label}:</span>
                        <span>${value}</span>
                    </div>
                `;
            }
            modalSpecs.innerHTML = specsHTML;
            
            // Update shop now link
            const shopBtn = document.getElementById('shopNowBtn');
            shopBtn.href = `https://snopitechstore.online/8-2/?equipment=${equipmentId}&model=${encodeURIComponent(equipment.name)}`;
            
            // Add fallback for main image
            mainImage.onerror = function() {
                this.src = "https://images.unsplash.com/photo-1558494949-ef010cbdcc31?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80";
            };
            
            modal.style.display = 'flex';
            document.body.style.overflow = 'hidden';
        }

        // Update image counter
        function updateImageCounter() {
            const equipment = networkEquipment.find(e => e.name === modalTitle.textContent.replace(/<[^>]*>/g, ''));
            if (equipment) {
                imageCounter.textContent = `Image ${currentImageIndex + 1} of ${equipment.images.length}`;
            }
        }

        // Close modal
        function closeModalFunc() {
            modal.style.display = 'none';
            document.body.style.overflow = 'auto';
        }

        // Initialize
        document.addEventListener('DOMContentLoaded', () => {
            // Render initial gallery
            renderGallery(networkEquipment);
            
            // Filter button events
            filterButtons.forEach(button => {
                button.addEventListener('click', () => {
                    filterButtons.forEach(btn => btn.classList.remove('active'));
                    button.classList.add('active');
                    
                    const filter = button.dataset.filter;
                    const filteredEquipment = filterEquipment(filter);
                    renderGallery(filteredEquipment);
                });
            });
            
            // Search input event
            searchInput.addEventListener('input', (e) => {
                const query = e.target.value.trim();
                
                if (query.length === 0) {
                    const activeFilter = document.querySelector('.filter-btn.active').dataset.filter;
                    const filteredEquipment = filterEquipment(activeFilter);
                    renderGallery(filteredEquipment);
                    return;
                }
                
                const searchedEquipment = searchEquipment(query);
                renderGallery(searchedEquipment);
            });
            
            // Modal close events
            closeModal.addEventListener('click', closeModalFunc);
            closeModalBtn.addEventListener('click', closeModalFunc);
            
            window.addEventListener('click', (e) => {
                if (e.target === modal) {
                    closeModalFunc();
                }
            });
            
            // View All button
            viewAllBtn.addEventListener('click', () => {
                filterButtons.forEach(btn => btn.classList.remove('active'));
                document.querySelector('.filter-btn[data-filter="all"]').classList.add('active');
                renderGallery(networkEquipment);
                searchInput.value = '';
            });
            
            // Close modal on escape key
            document.addEventListener('keydown', (e) => {
                if (e.key === 'Escape' && modal.style.display === 'flex') {
                    closeModalFunc();
                }
                
                // Arrow key navigation for images
                if (modal.style.display === 'flex') {
                    const equipment = networkEquipment.find(e => e.name === modalTitle.textContent.replace(/<[^>]*>/g, ''));
                    if (equipment) {
                        if (e.key === 'ArrowRight') {
                            currentImageIndex = (currentImageIndex + 1) % equipment.images.length;
                            mainImage.src = equipment.images[currentImageIndex];
                            updateThumbnailSelection(currentImageIndex);
                            updateImageCounter();
                        } else if (e.key === 'ArrowLeft') {
                            currentImageIndex = (currentImageIndex - 1 + equipment.images.length) % equipment.images.length;
                            mainImage.src = equipment.images[currentImageIndex];
                            updateThumbnailSelection(currentImageIndex);
                            updateImageCounter();
                        }
                    }
                }
            });
        });
    </script>
</body>
</html>
