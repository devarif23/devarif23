<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arif Jahan | WordPress & Frontend Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #6C63FF;
            --secondary: #4D44DB;
            --accent: #FF6584;
            --dark: #2D3748;
            --light: #F7FAFC;
            --gray: #718096;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Cover Section */
        .cover {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            text-align: center;
            padding: 100px 0 60px;
            position: relative;
            overflow: hidden;
        }
        
        .cover::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('https://images.unsplash.com/photo-1499750310107-5fef28a66643?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80') center/cover;
            opacity: 0.15;
            z-index: 0;
        }
        
        .cover-content {
            position: relative;
            z-index: 1;
        }
        
        .avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            object-fit: cover;
            border: 5px solid white;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            margin-bottom: 20px;
        }
        
        h1 {
            font-size: 2.8rem;
            margin-bottom: 10px;
        }
        
        .tagline {
            font-size: 1.5rem;
            margin-bottom: 20px;
            font-weight: 300;
        }
        
        .intro {
            max-width: 700px;
            margin: 0 auto 30px;
            font-size: 1.1rem;
        }
        
        /* Main Content */
        .main-content {
            padding: 60px 0;
        }
        
        .section {
            background: white;
            border-radius: 15px;
            padding: 40px;
            margin-bottom: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        h2 {
            color: var(--primary);
            font-size: 2rem;
            margin-bottom: 25px;
            position: relative;
            display: inline-block;
        }
        
        h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 50px;
            height: 4px;
            background: var(--accent);
            border-radius: 2px;
        }
        
        h3 {
            font-size: 1.4rem;
            margin: 25px 0 15px;
            color: var(--secondary);
        }
        
        p {
            margin-bottom: 15px;
            color: var(--gray);
        }
        
        ul {
            margin-bottom: 20px;
            padding-left: 20px;
        }
        
        li {
            margin-bottom: 10px;
            position: relative;
        }
        
        li::before {
            content: '▹';
            position: absolute;
            left: -20px;
            color: var(--accent);
        }
        
        /* Badges */
        .badges {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin: 20px 0;
        }
        
        .badge {
            display: inline-block;
            padding: 8px 15px;
            background: var(--light);
            border-radius: 50px;
            font-size: 0.9rem;
            font-weight: 600;
            color: var(--dark);
            border: 1px solid #E2E8F0;
        }
        
        /* Services */
        .services {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }
        
        .service-card {
            background: var(--light);
            border-radius: 10px;
            padding: 25px;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border-left: 4px solid var(--primary);
        }
        
        .service-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }
        
        .service-card h4 {
            font-size: 1.2rem;
            margin-bottom: 15px;
            color: var(--secondary);
        }
        
        /* Stats */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }
        
        .stat-card {
            text-align: center;
            padding: 20px;
            background: var(--light);
            border-radius: 10px;
        }
        
        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 5px;
        }
        
        .stat-label {
            color: var(--gray);
            font-size: 0.9rem;
        }
        
        /* Social Links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }
        
        .social-link {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.3rem;
            transition: transform 0.3s ease;
        }
        
        .social-link:hover {
            transform: translateY(-5px);
        }
        
        .facebook { background: #1877F2; }
        .instagram { background: linear-gradient(45deg, #f09433, #e6683c, #dc2743, #cc2366, #bc1888); }
        .twitter { background: #1DA1F2; }
        .pinterest { background: #BD081C; }
        .youtube { background: #FF0000; }
        .email { background: var(--accent); }
        
        /* Footer */
        footer {
            text-align: center;
            padding: 30px 0;
            background: var(--dark);
            color: white;
        }
        
        .quote {
            font-style: italic;
            font-size: 1.2rem;
            margin-bottom: 20px;
            color: var(--accent);
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.2rem;
            }
            
            .tagline {
                font-size: 1.2rem;
            }
            
            .section {
                padding: 30px;
            }
        }
    </style>
</head>
<body>
    <!-- Cover Section -->
    <section class="cover">
        <div class="container">
            <div class="cover-content">
                <img src="https://avatars.githubusercontent.com/u/12345678?v=4" alt="Arif Jahan" class="avatar">
                <h1>Arif Jahan</h1>
                <h2 class="tagline">Professional WordPress & Frontend Developer</h2>
                <p class="intro">Building high-performance WordPress sites & modern web apps<br>Expert in Elementor, React, and responsive design</p>
            </div>
        </div>
    </section>

    <!-- Main Content -->
    <div class="container">
        <div class="main-content">
            <!-- Current Activities -->
            <section class="section">
                <h2>What I'm Currently Doing</h2>
                <ul>
                    <li><strong>Working on</strong> React Projects & Custom WordPress Themes</li>
                    <li><strong>Learning</strong> Advanced WordPress Development</li>
                    <li><strong>Ask me about</strong> Frontend Development | WordPress | Elementor</li>
                    <li><strong>Open for</strong> Frontend or WordPress Projects</li>
                </ul>
            </section>

            <!-- Technologies -->
            <section class="section">
                <h2>Technologies I Use</h2>
                
                <h3>Frontend</h3>
                <div class="badges">
                    <span class="badge">HTML5</span>
                    <span class="badge">CSS3</span>
                    <span class="badge">JavaScript</span>
                    <span class="badge">React</span>
                    <span class="badge">TailwindCSS</span>
                    <span class="badge">Bootstrap</span>
                </div>
                
                <h3>WordPress & CMS</h3>
                <div class="badges">
                    <span class="badge">WordPress</span>
                    <span class="badge">Elementor</span>
                    <span class="badge">WooCommerce</span>
                </div>
                
                <h3>Programming Languages</h3>
                <div class="badges">
                    <span class="badge">Python</span>
                    <span class="badge">C</span>
                    <span class="badge">C++</span>
                </div>
                
                <h3>Other Skills</h3>
                <div class="badges">
                    <span class="badge">Git</span>
                    <span class="badge">GitHub</span>
                    <span class="badge">Figma</span>
                </div>
            </section>

            <!-- Services -->
            <section class="section">
                <h2>My Development Services</h2>
                
                <h3>Frontend Development</h3>
                <div class="services">
                    <div class="service-card">
                        <h4>Responsive Web Design</h4>
                        <p>Mobile-friendly websites that look great on all devices</p>
                    </div>
                    <div class="service-card">
                        <h4>React Applications</h4>
                        <p>Modern, interactive web applications with React</p>
                    </div>
                    <div class="service-card">
                        <h4>Performance Optimization</h4>
                        <p>Lightning fast websites with optimized code</p>
                    </div>
                </div>
                
                <h3>WordPress Development</h3>
                <div class="services">
                    <div class="service-card">
                        <h4>Custom WordPress Themes</h4>
                        <p>Tailored themes built to your specifications</p>
                    </div>
                    <div class="service-card">
                        <h4>Elementor Websites</h4>
                        <p>Beautiful websites built with Elementor</p>
                    </div>
                    <div class="service-card">
                        <h4>WooCommerce Solutions</h4>
                        <p>Complete e-commerce solutions for your business</p>
                    </div>
                </div>
            </section>

            <!-- Stats -->
            <section class="section">
                <h2>My Stats</h2>
                <div class="stats">
                    <div class="stat-card">
                        <div class="stat-number">50+</div>
                        <div class="stat-label">Projects Completed</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">100%</div>
                        <div class="stat-label">Client Satisfaction</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">5+</div>
                        <div class="stat-label">Years Experience</div>
                    </div>
                </div>
            </section>

            <!-- Connect -->
            <section class="section">
                <h2>Connect With Me</h2>
                <div class="social-links">
                    <a href="https://www.facebook.com/arifjahan01" class="social-link facebook"><i class="fab fa-facebook-f"></i></a>
                    <a href="https://www.instagram.com/arifjahan864/" class="social-link instagram"><i class="fab fa-instagram"></i></a>
                    <a href="https://www.twitter.com/arifjahan864/" class="social-link twitter"><i class="fab fa-twitter"></i></a>
                    <a href="https://www.pinterest.com/mdarifjahan90/" class="social-link pinterest"><i class="fab fa-pinterest-p"></i></a>
                    <a href="https://www.youtube.com/@devarif420" class="social-link youtube"><i class="fab fa-youtube"></i></a>
                    <a href="mailto:mdarifjahan138@gmail.com" class="social-link email"><i class="fas fa-envelope"></i></a>
                </div>
            </section>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p class="quote">I transform ideas into powerful WordPress websites with stunning designs, blazing speed, and perfect functionality. Let's build something amazing together!</p>
            <p>© 2023 Arif Jahan. All rights reserved.</p>
        </div>
    </footer>
</body>
</html>
