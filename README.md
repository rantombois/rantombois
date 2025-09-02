<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Yusuf Saputra - Finance Professional Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-blue: #1a5276;
            --secondary-blue: #3498db;
            --accent-orange: #e67e22;
            --light-blue: #5dade2;
            --dark-gray: #34495e;
            --medium-gray: #7f8c8d;
            --light-gray: #ecf0f1;
            --white: #ffffff;
            --shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
            --transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--dark-gray);
            background-color: var(--white);
            overflow-x: hidden;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            z-index: 1000;
            transition: var(--transition);
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary-blue);
            display: flex;
            align-items: center;
        }

        .logo i {
            margin-right: 0.5rem;
            color: var(--accent-orange);
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--dark-gray);
            font-weight: 500;
            position: relative;
            transition: var(--transition);
            padding: 0.5rem 0;
        }

        .nav-links a:hover {
            color: var(--secondary-blue);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 3px;
            background: linear-gradient(90deg, var(--secondary-blue), var(--accent-orange));
            transition: var(--transition);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Timeline Navigation */
        .timeline-nav {
            position: fixed;
            right: 30px;
            top: 50%;
            transform: translateY(-50%);
            z-index: 999;
        }

        .timeline-dot {
            width: 16px;
            height: 16px;
            border-radius: 50%;
            background-color: var(--light-gray);
            margin: 20px 0;
            cursor: pointer;
            position: relative;
            transition: var(--transition);
        }

        .timeline-dot.active {
            background-color: var(--accent-orange);
            transform: scale(1.3);
            box-shadow: 0 0 0 4px rgba(230, 126, 34, 0.2);
        }

        .timeline-dot::before {
            content: attr(data-section);
            position: absolute;
            right: 30px;
            top: 50%;
            transform: translateY(-50%);
            background: linear-gradient(135deg, var(--secondary-blue), var(--accent-orange));
            color: var(--white);
            padding: 8px 15px;
            border-radius: 30px;
            font-size: 0.9rem;
            white-space: nowrap;
            opacity: 0;
            pointer-events: none;
            transition: var(--transition);
            box-shadow: var(--shadow);
        }

        .timeline-dot:hover::before {
            opacity: 1;
            right: 40px;
        }

        /* Sections */
        section {
            padding: 6rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            position: relative;
        }

        .section-title {
            font-size: 3rem;
            color: var(--primary-blue);
            margin-bottom: 2.5rem;
            position: relative;
            padding-bottom: 1rem;
            display: inline-block;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100px;
            height: 5px;
            background: linear-gradient(90deg, var(--secondary-blue), var(--accent-orange));
            border-radius: 5px;
        }

        /* Home Section */
        #home {
            background: linear-gradient(135deg, rgba(44, 62, 80, 0.05) 0%, rgba(52, 152, 219, 0.1) 100%);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        #home::before {
            content: '';
            position: absolute;
            top: -150px;
            right: -150px;
            width: 400px;
            height: 400px;
            border-radius: 50%;
            background: linear-gradient(135deg, rgba(52, 152, 219, 0.2), rgba(230, 126, 34, 0.2));
            z-index: -1;
        }

        #home::after {
            content: '';
            position: absolute;
            bottom: -100px;
            left: -100px;
            width: 300px;
            height: 300px;
            border-radius: 50%;
            background: linear-gradient(135deg, rgba(230, 126, 34, 0.2), rgba(52, 152, 219, 0.2));
            z-index: -1;
        }

        .hero-headline {
            font-size: 3.5rem;
            color: var(--primary-blue);
            margin-bottom: 1.5rem;
            font-weight: 700;
            line-height: 1.2;
            max-width: 900px;
        }

        .hero-subheadline {
            font-size: 1.3rem;
            color: var(--medium-gray);
            max-width: 800px;
            margin-bottom: 3rem;
        }

        .hero-buttons {
            display: flex;
            gap: 1.5rem;
        }

        .btn {
            padding: 1rem 2.5rem;
            border-radius: 50px;
            font-weight: 600;
            text-decoration: none;
            transition: var(--transition);
            cursor: pointer;
            border: none;
            font-size: 1.1rem;
            display: inline-flex;
            align-items: center;
            justify-content: center;
        }

        .btn i {
            margin-left: 0.5rem;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--secondary-blue), var(--light-blue));
            color: var(--white);
            box-shadow: 0 5px 15px rgba(52, 152, 219, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(52, 152, 219, 0.4);
        }

        .btn-secondary {
            background: linear-gradient(135deg, var(--accent-orange), #f39c12);
            color: var(--white);
            box-shadow: 0 5px 15px rgba(230, 126, 34, 0.3);
        }

        .btn-secondary:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(230, 126, 34, 0.4);
        }

        /* About Section */
        #about {
            display: flex;
            gap: 4rem;
            align-items: center;
        }

        .about-content {
            flex: 1;
        }

        .about-text {
            font-size: 1.2rem;
            line-height: 1.8;
            color: var(--dark-gray);
            margin-bottom: 1.5rem;
        }

        .about-image {
            flex: 0 0 350px;
            height: 350px;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: var(--shadow);
            position: relative;
            transform: rotate(3deg);
            transition: var(--transition);
        }

        .about-image:hover {
            transform: rotate(0deg) scale(1.03);
        }

        .about-image::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(52, 152, 219, 0.3), rgba(230, 126, 34, 0.3));
            z-index: 1;
        }

        .about-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        /* Work Experience Section */
        #experience {
            background-color: #f8f9fa;
            border-radius: 30px;
            padding: 6rem 3rem;
        }

        .timeline {
            position: relative;
            margin-left: 2rem;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            height: 100%;
            width: 5px;
            background: linear-gradient(180deg, var(--secondary-blue), var(--accent-orange));
            border-radius: 5px;
        }

        .timeline-item {
            position: relative;
            margin-bottom: 3rem;
            padding-left: 3rem;
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.7s ease;
        }

        .timeline-item.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .timeline-item:last-child {
            margin-bottom: 0;
        }

        .timeline-dot {
            position: absolute;
            left: -12px;
            top: 5px;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            background-color: var(--white);
            border: 5px solid var(--secondary-blue);
            box-shadow: var(--shadow);
            z-index: 2;
        }

        .timeline-date {
            font-weight: 700;
            color: var(--accent-orange);
            margin-bottom: 0.5rem;
            font-size: 1.1rem;
        }

        .timeline-title {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-blue);
            margin-bottom: 0.5rem;
        }

        .timeline-company {
            font-style: italic;
            color: var(--medium-gray);
            margin-bottom: 1rem;
            font-size: 1.1rem;
        }

        .timeline-description {
            color: var(--dark-gray);
            font-size: 1.1rem;
            line-height: 1.6;
        }

        /* Education Section */
        #education {
            display: flex;
            flex-direction: column;
        }

        .education-container {
            display: flex;
            gap: 3rem;
            margin-top: 2rem;
        }

        .education-box, .certification-box {
            flex: 1;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.9), rgba(255, 255, 255, 0.7));
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 2.5rem;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .education-box:hover, .certification-box:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .box-title {
            font-size: 1.8rem;
            color: var(--primary-blue);
            margin-bottom: 1.5rem;
            display: flex;
            align-items: center;
        }

        .box-title i {
            margin-right: 0.8rem;
            color: var(--accent-orange);
            font-size: 2rem;
        }

        .education-item, .certification-item {
            margin-bottom: 1.8rem;
            padding-bottom: 1.8rem;
            border-bottom: 1px solid var(--light-gray);
        }

        .education-item:last-child, .certification-item:last-child {
            margin-bottom: 0;
            padding-bottom: 0;
            border-bottom: none;
        }

        .item-title {
            font-weight: 700;
            color: var(--dark-gray);
            margin-bottom: 0.3rem;
            font-size: 1.2rem;
        }

        .item-subtitle {
            color: var(--medium-gray);
            margin-bottom: 0.3rem;
            font-size: 1.1rem;
        }

        .item-date {
            font-size: 1rem;
            color: var(--secondary-blue);
            font-weight: 600;
        }

        /* Skills Section */
        #skills {
            background: linear-gradient(135deg, rgba(44, 62, 80, 0.05) 0%, rgba(52, 152, 219, 0.1) 100%);
            border-radius: 30px;
            padding: 6rem 3rem;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2.5rem;
            margin-top: 2rem;
        }

        .skill-card {
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.9), rgba(255, 255, 255, 0.7));
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 2rem;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.2);
            display: flex;
            flex-direction: column;
        }

        .skill-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .skill-header {
            display: flex;
            align-items: center;
            margin-bottom: 1.5rem;
        }

        .skill-icon {
            width: 60px;
            height: 60px;
            border-radius: 15px;
            background: linear-gradient(135deg, var(--secondary-blue), var(--light-blue));
            display: flex;
            justify-content: center;
            align-items: center;
            margin-right: 1rem;
            color: var(--white);
            font-size: 1.8rem;
            box-shadow: 0 5px 15px rgba(52, 152, 219, 0.3);
        }

        .skill-name {
            font-weight: 700;
            color: var(--dark-gray);
            font-size: 1.3rem;
        }

        .skill-level {
            margin-top: auto;
        }

        .progress-bar {
            height: 10px;
            background-color: var(--light-gray);
            border-radius: 10px;
            overflow: hidden;
            margin-top: 1rem;
        }

        .progress {
            height: 100%;
            background: linear-gradient(90deg, var(--secondary-blue), var(--accent-orange));
            border-radius: 10px;
            width: 0;
            transition: width 1.5s ease;
        }

        /* Contact Section */
        #contact {
            display: flex;
            flex-direction: column;
        }

        .contact-container {
            display: flex;
            gap: 4rem;
            margin-top: 2rem;
        }

        .contact-info {
            flex: 1;
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 2rem;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.9), rgba(255, 255, 255, 0.7));
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 1.5rem;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .contact-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }

        .contact-icon {
            width: 60px;
            height: 60px;
            border-radius: 15px;
            background: linear-gradient(135deg, var(--secondary-blue), var(--light-blue));
            display: flex;
            justify-content: center;
            align-items: center;
            margin-right: 1.5rem;
            color: var(--white);
            font-size: 1.5rem;
            box-shadow: 0 5px 15px rgba(52, 152, 219, 0.3);
        }

        .contact-text {
            font-size: 1.2rem;
            color: var(--dark-gray);
        }

        .contact-form {
            flex: 1;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.9), rgba(255, 255, 255, 0.7));
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 2.5rem;
            box-shadow: var(--shadow);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .form-group {
            margin-bottom: 1.8rem;
        }

        .form-control {
            width: 100%;
            padding: 1rem 1.5rem;
            border: 2px solid var(--light-gray);
            border-radius: 10px;
            font-size: 1.1rem;
            transition: var(--transition);
            background-color: rgba(255, 255, 255, 0.7);
        }

        .form-control:focus {
            outline: none;
            border-color: var(--secondary-blue);
            box-shadow: 0 0 0 3px rgba(52, 152, 219, 0.2);
            background-color: var(--white);
        }

        textarea.form-control {
            resize: vertical;
            min-height: 150px;
        }

        /* Footer */
        footer {
            background: linear-gradient(135deg, var(--primary-blue), var(--secondary-blue));
            color: var(--white);
            text-align: center;
            padding: 3rem 2rem;
        }

        .social-links {
            margin-bottom: 2rem;
        }

        .social-links a {
            color: var(--white);
            margin: 0 1rem;
            font-size: 1.8rem;
            transition: var(--transition);
            display: inline-block;
        }

        .social-links a:hover {
            color: var(--accent-orange);
            transform: translateY(-5px);
        }

        /* Responsive */
        .menu-toggle {
            display: none;
            flex-direction: column;
            justify-content: space-between;
            width: 30px;
            height: 21px;
            cursor: pointer;
        }

        .menu-toggle span {
            height: 3px;
            width: 100%;
            background-color: var(--dark-gray);
            border-radius: 3px;
        }

        @media (max-width: 992px) {
            .hero-headline {
                font-size: 2.8rem;
            }

            .about {
                flex-direction: column;
            }

            .about-image {
                flex: 0 0 300px;
                height: 300px;
                align-self: center;
            }

            .education-container, .contact-container {
                flex-direction: column;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                position: fixed;
                right: -100%;
                top: 70px;
                flex-direction: column;
                background-color: var(--white);
                width: 100%;
                text-align: center;
                transition: 0.3s;
                box-shadow: var(--shadow);
                padding: 2rem 0;
            }

            .nav-links.active {
                right: 0;
            }

            .nav-links li {
                margin: 1rem 0;
            }

            .menu-toggle {
                display: flex;
            }

            .timeline-nav {
                display: none;
            }

            .hero-headline {
                font-size: 2.2rem;
            }

            .hero-buttons {
                flex-direction: column;
                width: 100%;
                max-width: 300px;
            }

            .skills-grid {
                grid-template-columns: 1fr;
            }

            section {
                padding: 4rem 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <div class="logo"><i class="fas fa-chart-line"></i> YS</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#experience">Experience</a></li>
                <li><a href="#education">Education</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="menu-toggle">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- Timeline Navigation -->
    <div class="timeline-nav">
        <div class="timeline-dot active" data-section="Home" data-target="home"></div>
        <div class="timeline-dot" data-section="About" data-target="about"></div>
        <div class="timeline-dot" data-section="Experience" data-target="experience"></div>
        <div class="timeline-dot" data-section="Education" data-target="education"></div>
        <div class="timeline-dot" data-section="Skills" data-target="skills"></div>
        <div class="timeline-dot" data-section="Contact" data-target="contact"></div>
    </div>

    <!-- Home Section -->
    <section id="home">
        <h1 class="hero-headline">Yusuf Saputra – Finance, Accounting, Taxation & Internal Audit Supervisor</h1>
        <p class="hero-subheadline">With over 8 years of experience in finance, accounting, taxation, and internal audit, I help companies deliver financial solutions that are accurate, efficient, and value-driven.</p>
        <div class="hero-buttons">
            <a href="#contact" class="btn btn-primary">Hire Me <i class="fas fa-arrow-right"></i></a>
            <a href="#" class="btn btn-secondary" id="download-cv">Download CV <i class="fas fa-download"></i></a>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <div class="about-content">
            <h2 class="section-title">About Me</h2>
            <p class="about-text">I am a professional accountant with more than 8 years of experience across industries such as manufacturing, retail, and services. Specialized in financial reporting, taxation, internal audit, and financial system development, I consistently ensure accuracy, efficiency, and compliance in every project.</p>
            <p class="about-text">With a strong academic background in accounting and taxation certifications, I believe integrity, analytical thinking, and innovation are the key drivers to creating meaningful value for organizations.</p>
        </div>
        <div class="about-image">
            <img src="https://z-cdn-media.chatglm.cn/files/992e7594-cbbb-451b-afdf-4b911d3eef3c_DSC01089%401969801586%20%282%29.jpg?auth_key=1788320539-877b169f7a304d88927f607cfe7caf8f-0-7992b13d2494b198d8df6d7d3a24c02d" alt="Yusuf Saputra">
        </div>
    </section>

    <!-- Work Experience Section -->
    <section id="experience">
        <h2 class="section-title">Work Experience</h2>
        <div class="timeline">
            <div class="timeline-item">
                <div class="timeline-dot"></div>
                <div class="timeline-date">2024 – Present</div>
                <div class="timeline-title">Finance, Accounting, Taxation & Internal Audit Supervisor</div>
                <div class="timeline-company">PT. Vetways Indonesia Group</div>
                <div class="timeline-description">Managed financial statements, AP/AR, costing, and taxation to ensure effectiveness and compliance.</div>
            </div>
            <div class="timeline-item">
                <div class="timeline-dot"></div>
                <div class="timeline-date">2020 – 2024</div>
                <div class="timeline-title">Finance & Accounting Supervisor</div>
                <div class="timeline-company">PT. Bentonit Makmur Sentosa</div>
                <div class="timeline-description">Controlled financial reports, AP/AR, costing, taxation, and developed financial strategies.</div>
            </div>
            <div class="timeline-item">
                <div class="timeline-dot"></div>
                <div class="timeline-date">2019 – 2020</div>
                <div class="timeline-title">Finance & Accounting Specialist</div>
                <div class="timeline-company">PT. Mitra Media Bangsa (JITU Group)</div>
                <div class="timeline-description">Handled reporting and taxation for 5 subsidiaries and analyzed their performance.</div>
            </div>
            <div class="timeline-item">
                <div class="timeline-dot"></div>
                <div class="timeline-date">2018 – 2019</div>
                <div class="timeline-title">Finance & Accounting Staff</div>
                <div class="timeline-company">PT. Enggal Group</div>
                <div class="timeline-description">Prepared financial reports and performance analysis.</div>
            </div>
        </div>
    </section>

    <!-- Education & Certifications Section -->
    <section id="education">
        <h2 class="section-title">Education & Certifications</h2>
        <div class="education-container">
            <div class="education-box">
                <h3 class="box-title"><i class="fas fa-graduation-cap"></i> Education</h3>
                <div class="education-item">
                    <div class="item-title">Bachelor of Accounting</div>
                    <div class="item-subtitle">Yogyakarta University of Technology</div>
                    <div class="item-date">2014 – 2018</div>
                </div>
            </div>
            <div class="certification-box">
                <h3 class="box-title"><i class="fas fa-certificate"></i> Certifications</h3>
                <div class="certification-item">
                    <div class="item-title">Associate Member</div>
                    <div class="item-subtitle">Indonesian Institute of Accountants</div>
                    <div class="item-date">2019 – Present</div>
                </div>
                <div class="certification-item">
                    <div class="item-title">Tax Brevet A & B</div>
                    <div class="item-subtitle">Tax Certification</div>
                    <div class="item-date">2021 – Present</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills">
        <h2 class="section-title">Skills</h2>
        <div class="skills-grid">
            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon"><i class="fas fa-chart-line"></i></div>
                    <div class="skill-name">Financial Reporting</div>
                </div>
                <div class="skill-level">
                    <div class="progress-bar">
                        <div class="progress" data-width="95%"></div>
                    </div>
                </div>
            </div>
            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon"><i class="fas fa-cogs"></i></div>
                    <div class="skill-name">Finance Engineering & Development</div>
                </div>
                <div class="skill-level">
                    <div class="progress-bar">
                        <div class="progress" data-width="90%"></div>
                    </div>
                </div>
            </div>
            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon"><i class="fas fa-analytics"></i></div>
                    <div class="skill-name">Financial Analysis</div>
                </div>
                <div class="skill-level">
                    <div class="progress-bar">
                        <div class="progress" data-width="92%"></div>
                    </div>
                </div>
            </div>
            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon"><i class="fas fa-file-invoice-dollar"></i></div>
                    <div class="skill-name">AR/AP Management</div>
                </div>
                <div class="skill-level">
                    <div class="progress-bar">
                        <div class="progress" data-width="93%"></div>
                    </div>
                </div>
            </div>
            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon"><i class="fas fa-search"></i></div>
                    <div class="skill-name">Internal Audit</div>
                </div>
                <div class="skill-level">
                    <div class="progress-bar">
                        <div class="progress" data-width="88%"></div>
                    </div>
                </div>
            </div>
            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon"><i class="fas fa-calculator"></i></div>
                    <div class="skill-name">Taxation</div>
                </div>
                <div class="skill-level">
                    <div class="progress-bar">
                        <div class="progress" data-width="91%"></div>
                    </div>
                </div>
            </div>
            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon"><i class="fas fa-laptop-code"></i></div>
                    <div class="skill-name">ERP & Accounting Systems</div>
                </div>
                <div class="skill-level">
                    <div class="progress-bar">
                        <div class="progress" data-width="87%"></div>
                    </div>
                </div>
            </div>
            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon"><i class="fas fa-award"></i></div>
                    <div class="skill-name">ISO 9001:2015, API Q1</div>
                </div>
                <div class="skill-level">
                    <div class="progress-bar">
                        <div class="progress" data-width="85%"></div>
                    </div>
                </div>
            </div>
            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon"><i class="fas fa-desktop"></i></div>
                    <div class="skill-name">Microsoft Office & IT Skills</div>
                </div>
                <div class="skill-level">
                    <div class="progress-bar">
                        <div class="progress" data-width="94%"></div>
                    </div>
                </div>
            </div>
            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon"><i class="fas fa-pen"></i></div>
                    <div class="skill-name">Content Creator</div>
                </div>
                <div class="skill-level">
                    <div class="progress-bar">
                        <div class="progress" data-width="80%"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <h2 class="section-title">Contact</h2>
        <div class="contact-container">
            <div class="contact-info">
                <div class="contact-item">
                    <div class="contact-icon"><i class="fas fa-phone"></i></div>
                    <div class="contact-text">+62 878 8770 4030</div>
                </div>
                <div class="contact-item">
                    <div class="contact-icon"><i class="fas fa-envelope"></i></div>
                    <div class="contact-text">yusuf.saputra@akuntanindonesia.or.id</div>
                </div>
                <div class="contact-item">
                    <div class="contact-icon"><i class="fab fa-linkedin"></i></div>
                    <div class="contact-text">linkedin.com/in/yusuf-saputra41</div>
                </div>
                <div class="contact-item">
                    <div class="contact-icon"><i class="fas fa-map-marker-alt"></i></div>
                    <div class="contact-text">Surabaya, Indonesia</div>
                </div>
            </div>
            <div class="contact-form">
                <form id="contact-form">
                    <div class="form-group">
                        <input type="text" class="form-control" placeholder="Your Name" required>
                    </div>
                    <div class="form-group">
                        <input type="email" class="form-control" placeholder="Your Email" required>
                    </div>
                    <div class="form-group">
                        <textarea class="form-control" placeholder="Your Message" required></textarea>
                    </div>
                    <button type="submit" class="btn btn-primary">Send Message <i class="fas fa-paper-plane"></i></button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="social-links">
            <a href="#"><i class="fab fa-linkedin"></i></a>
            <a href="#"><i class="fab fa-twitter"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
            <a href="#"><i class="fab fa-github"></i></a>
        </div>
        <p>&copy; 2024 Yusuf Saputra. All Rights Reserved.</p>
    </footer>

    <script>
        // Mobile Menu Toggle
        const menuToggle = document.querySelector('.menu-toggle');
        const navLinks = document.querySelector('.nav-links');

        menuToggle.addEventListener('click', () => {
            navLinks.classList.toggle('active');
        });

        // Close mobile menu when clicking on a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
            });
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    window.scrollTo({
                        top: target.offsetTop - 70,
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Timeline Navigation
        const timelineDots = document.querySelectorAll('.timeline-dot');
        const sections = document.querySelectorAll('section');

        // Function to update active timeline dot
        function updateActiveDot() {
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if (pageYOffset >= (sectionTop - 200)) {
                    current = section.getAttribute('id');
                }
            });

            timelineDots.forEach(dot => {
                dot.classList.remove('active');
                if (dot.getAttribute('data-target') === current) {
                    dot.classList.add('active');
                }
            });
        }

        // Click on timeline dots to navigate
        timelineDots.forEach(dot => {
            dot.addEventListener('click', () => {
                const targetId = dot.getAttribute('data-target');
                const targetSection = document.getElementById(targetId);
                if (targetSection) {
                    window.scrollTo({
                        top: targetSection.offsetTop - 70,
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Update active dot on scroll
        window.addEventListener('scroll', updateActiveDot);

        // Timeline animation on scroll
        const timelineItems = document.querySelectorAll('.timeline-item');

        function checkTimelineItems() {
            timelineItems.forEach(item => {
                const itemTop = item.getBoundingClientRect().top;
                const windowHeight = window.innerHeight;
                
                if (itemTop < windowHeight * 0.8) {
                    item.classList.add('visible');
                }
            });
        }

        // Skills progress animation
        const progressBars = document.querySelectorAll('.progress');

        function animateProgressBars() {
            progressBars.forEach(bar => {
                const barTop = bar.getBoundingClientRect().top;
                const windowHeight = window.innerHeight;
                
                if (barTop < windowHeight * 0.8 && !bar.style.width) {
                    const width = bar.getAttribute('data-width');
                    bar.style.width = width;
                }
            });
        }

        // Contact form submission
        const contactForm = document.getElementById('contact-form');
        
        contactForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get form values
            const name = this.querySelector('input[type="text"]').value;
            const email = this.querySelector('input[type="email"]').value;
            const message = this.querySelector('textarea').value;
            
            // Here you would normally send the form data to a server
            // For this example, we'll just show a success message
            const formElements = this.querySelectorAll('.form-control');
            formElements.forEach(element => {
                element.value = '';
            });
            
            // Create and show success message
            const successMessage = document.createElement('div');
            successMessage.className = 'alert alert-success';
            successMessage.textContent = 'Thank you for your message! I will get back to you soon.';
            successMessage.style.padding = '1rem';
            successMessage.style.marginTop = '1rem';
            successMessage.style.backgroundColor = '#d4edda';
            successMessage.style.color = '#155724';
            successMessage.style.borderRadius = '10px';
            successMessage.style.textAlign = 'center';
            
            this.appendChild(successMessage);
            
            // Remove success message after 5 seconds
            setTimeout(() => {
                successMessage.remove();
            }, 5000);
        });

        // Download CV button
        document.getElementById('download-cv').addEventListener('click', function(e) {
            e.preventDefault();
            // In a real implementation, this would link to an actual CV file
            alert('CV download would start here in a real implementation.');
        });

        // Event listeners for scroll animations
        window.addEventListener('scroll', () => {
            checkTimelineItems();
            animateProgressBars();
        });

        // Initial checks
        document.addEventListener('DOMContentLoaded', () => {
            updateActiveDot();
            checkTimelineItems();
            animateProgressBars();
        });
    </script>
</body>
</html>
