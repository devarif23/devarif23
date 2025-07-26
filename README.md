<?php
/*
Template Name: Arif Jahan - Developer Portfolio
*/
get_header();
?>

<!-- Hero Section -->
<section class="aj-hero" style="background: linear-gradient(135deg, #6C63FF, #4D44DB);">
    <div class="container">
        <div class="aj-hero-content">
            <img src="<?php echo get_stylesheet_directory_uri(); ?>/images/arif-avatar.jpg" alt="Arif Jahan" class="aj-avatar">
            <h1>Arif Jahan</h1>
            <h2>Professional WordPress & Frontend Developer</h2>
            <p class="aj-tagline">Elementor Expert | React Specialist | Web Solutions Architect</p>
            <div class="aj-hero-btns">
                <a href="#services" class="aj-btn aj-btn-primary">My Services</a>
                <a href="#contact" class="aj-btn aj-btn-secondary">Hire Me</a>
            </div>
        </div>
    </div>
</section>

<!-- About Section -->
<section class="aj-section" id="about">
    <div class="container">
        <div class="aj-section-header">
            <h2>About Me</h2>
            <p class="aj-section-subtitle">Transforming ideas into digital reality</p>
        </div>
        
        <div class="aj-about-grid">
            <div class="aj-about-content">
                <h3>Who I Am</h3>
                <p>I'm Arif Jahan, a passionate WordPress and Frontend Developer with over 5 years of experience creating high-performance websites and web applications. I specialize in WordPress development using Elementor and custom theme development, along with modern frontend technologies like React.</p>
                
                <h3>What I Do</h3>
                <div class="aj-skills">
                    <div class="aj-skill">
                        <i class="fas fa-wordpress"></i>
                        <span>WordPress Development</span>
                    </div>
                    <div class="aj-skill">
                        <i class="fas fa-paint-brush"></i>
                        <span>Elementor Design</span>
                    </div>
                    <div class="aj-skill">
                        <i class="fab fa-react"></i>
                        <span>React Applications</span>
                    </div>
                    <div class="aj-skill">
                        <i class="fas fa-shopping-cart"></i>
                        <span>WooCommerce</span>
                    </div>
                </div>
            </div>
            
            <div class="aj-about-stats">
                <div class="aj-stat">
                    <span class="aj-stat-number">500+</span>
                    <span class="aj-stat-label">Projects Completed</span>
                </div>
                <div class="aj-stat">
                    <span class="aj-stat-number">100%</span>
                    <span class="aj-stat-label">Client Satisfaction</span>
                </div>
                <div class="aj-stat">
                    <span class="aj-stat-number">5+</span>
                    <span class="aj-stat-label">Years Experience</span>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- Services Section -->
<section class="aj-section aj-bg-light" id="services">
    <div class="container">
        <div class="aj-section-header">
            <h2>My Services</h2>
            <p class="aj-section-subtitle">Professional solutions for your digital needs</p>
        </div>
        
        <div class="aj-services-grid">
            <!-- Service 1 -->
            <div class="aj-service-card">
                <div class="aj-service-icon">
                    <i class="fas fa-laptop-code"></i>
                </div>
                <h3>WordPress Development</h3>
                <ul>
                    <li>Custom WordPress Themes</li>
                    <li>Elementor Website Design</li>
                    <li>Plugin Customization</li>
                    <li>Website Migration</li>
                </ul>
            </div>
            
            <!-- Service 2 -->
            <div class="aj-service-card">
                <div class="aj-service-icon">
                    <i class="fab fa-react"></i>
                </div>
                <h3>Frontend Development</h3>
                <ul>
                    <li>React Applications</li>
                    <li>Responsive Web Design</li>
                    <li>Performance Optimization</li>
                    <li>UI/UX Implementation</li>
                </ul>
            </div>
            
            <!-- Service 3 -->
            <div class="aj-service-card">
                <div class="aj-service-icon">
                    <i class="fas fa-store"></i>
                </div>
                <h3>E-Commerce Solutions</h3>
                <ul>
                    <li>WooCommerce Setup</li>
                    <li>Payment Integration</li>
                    <li>Product Management</li>
                    <li>Store Optimization</li>
                </ul>
            </div>
        </div>
    </div>
</section>

<!-- Technologies Section -->
<section class="aj-section" id="technologies">
    <div class="container">
        <div class="aj-section-header">
            <h2>Technologies I Use</h2>
            <p class="aj-section-subtitle">Modern tools for exceptional results</p>
        </div>
        
        <div class="aj-tech-tabs">
            <button class="aj-tech-tab active" data-tab="frontend">Frontend</button>
            <button class="aj-tech-tab" data-tab="wordpress">WordPress</button>
            <button class="aj-tech-tab" data-tab="tools">Tools</button>
        </div>
        
        <div class="aj-tech-content active" id="frontend">
            <div class="aj-tech-badges">
                <div class="aj-tech-badge">
                    <img src="<?php echo get_stylesheet_directory_uri(); ?>/images/html5.svg" alt="HTML5">
                    <span>HTML5</span>
                </div>
                <!-- More badges for CSS, JS, React, etc. -->
            </div>
        </div>
        
        <div class="aj-tech-content" id="wordpress">
            <div class="aj-tech-badges">
                <div class="aj-tech-badge">
                    <img src="<?php echo get_stylesheet_directory_uri(); ?>/images/wordpress.svg" alt="WordPress">
                    <span>WordPress</span>
                </div>
                <!-- More badges for Elementor, WooCommerce, etc. -->
            </div>
        </div>
    </div>
</section>

<!-- Portfolio Section -->
<section class="aj-section aj-bg-light" id="portfolio">
    <div class="container">
        <div class="aj-section-header">
            <h2>My Portfolio</h2>
            <p class="aj-section-subtitle">Some of my recent work</p>
        </div>
        
        <div class="aj-portfolio-grid">
            <!-- Portfolio items would be dynamically loaded from WordPress -->
            <?php
            $portfolio_args = array(
                'post_type' => 'portfolio',
                'posts_per_page' => 6
            );
            $portfolio_query = new WP_Query($portfolio_args);
            
            if ($portfolio_query->have_posts()) :
                while ($portfolio_query->have_posts()) : $portfolio_query->the_post();
            ?>
                <div class="aj-portfolio-item">
                    <a href="<?php the_permalink(); ?>">
                        <?php the_post_thumbnail('portfolio-thumb'); ?>
                        <div class="aj-portfolio-overlay">
                            <h3><?php the_title(); ?></h3>
                            <p><?php echo get_the_excerpt(); ?></p>
                        </div>
                    </a>
                </div>
            <?php
                endwhile;
                wp_reset_postdata();
            endif;
            ?>
        </div>
    </div>
</section>

<!-- Contact Section -->
<section class="aj-section" id="contact">
    <div class="container">
        <div class="aj-section-header">
            <h2>Get In Touch</h2>
            <p class="aj-section-subtitle">Let's work together on your next project</p>
        </div>
        
        <div class="aj-contact-grid">
            <div class="aj-contact-info">
                <h3>Contact Information</h3>
                <div class="aj-contact-method">
                    <i class="fas fa-envelope"></i>
                    <span>mdarifjahan138@gmail.com</span>
                </div>
                <div class="aj-contact-method">
                    <i class="fas fa-phone"></i>
                    <span>(840) 765-43-21</span>
                </div>
                
                <h3>Follow Me</h3>
                <div class="aj-social-links">
                    <a href="https://facebook.com/arifjahan01" target="_blank"><i class="fab fa-facebook-f"></i></a>
                    <a href="https://twitter.com/arifjahan864" target="_blank"><i class="fab fa-twitter"></i></a>
                    <a href="https://instagram.com/arifjahan864" target="_blank"><i class="fab fa-instagram"></i></a>
                    <a href="https://github.com/devarif23" target="_blank"><i class="fab fa-github"></i></a>
                </div>
            </div>
            
            <div class="aj-contact-form">
                <?php echo do_shortcode('[contact-form-7 id="123" title="Contact form 1"]'); ?>
            </div>
        </div>
    </div>
</section>

<?php get_footer(); ?>

<style>
/* Base Styles */
:root {
    --aj-primary: #6C63FF;
    --aj-primary-dark: #4D44DB;
    --aj-secondary: #FF6584;
    --aj-dark: #2D3748;
    --aj-light: #F7FAFC;
    --aj-gray: #718096;
    --aj-light-gray: #E2E8F0;
}

body {
    font-family: 'Poppins', sans-serif;
    color: var(--aj-dark);
    line-height: 1.6;
}

.container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

/* Hero Section */
.aj-hero {
    color: white;
    text-align: center;
    padding: 120px 0 80px;
    position: relative;
}

.aj-hero-content {
    max-width: 800px;
    margin: 0 auto;
}

.aj-avatar {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    object-fit: cover;
    border: 5px solid rgba(255,255,255,0.2);
    margin-bottom: 30px;
}

.aj-hero h1 {
    font-size: 3rem;
    margin-bottom: 10px;
}

.aj-hero h2 {
    font-size: 1.8rem;
    font-weight: 400;
    margin-bottom: 15px;
}

.aj-tagline {
    font-size: 1.2rem;
    margin-bottom: 30px;
    opacity: 0.9;
}

.aj-hero-btns {
    display: flex;
    gap: 15px;
    justify-content: center;
}

.aj-btn {
    display: inline-block;
    padding: 12px 30px;
    border-radius: 50px;
    font-weight: 600;
    text-decoration: none;
    transition: all 0.3s ease;
}

.aj-btn-primary {
    background: white;
    color: var(--aj-primary);
}

.aj-btn-primary:hover {
    background: var(--aj-light);
    transform: translateY(-3px);
    box-shadow: 0 10px 20px rgba(0,0,0,0.1);
}

.aj-btn-secondary {
    background: transparent;
    color: white;
    border: 2px solid white;
}

.aj-btn-secondary:hover {
    background: rgba(255,255,255,0.1);
    transform: translateY(-3px);
}

/* Section Styles */
.aj-section {
    padding: 80px 0;
}

.aj-bg-light {
    background: var(--aj-light);
}

.aj-section-header {
    text-align: center;
    margin-bottom: 50px;
}

.aj-section-header h2 {
    font-size: 2.5rem;
    color: var(--aj-primary);
    margin-bottom: 15px;
    position: relative;
}

.aj-section-header h2::after {
    content: '';
    display: block;
    width: 80px;
    height: 4px;
    background: var(--aj-secondary);
    margin: 15px auto 0;
}

.aj-section-subtitle {
    font-size: 1.2rem;
    color: var(--aj-gray);
}

/* About Section */
.aj-about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 50px;
    align-items: center;
}

.aj-about-content h3 {
    font-size: 1.5rem;
    color: var(--aj-primary-dark);
    margin-bottom: 20px;
}

.aj-about-content p {
    margin-bottom: 30px;
}

.aj-skills {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 15px;
}

.aj-skill {
    display: flex;
    align-items: center;
    gap: 10px;
    background: white;
    padding: 15px;
    border-radius: 8px;
    box-shadow: 0 5px 15px rgba(0,0,0,0.05);
}

.aj-skill i {
    color: var(--aj-primary);
    font-size: 1.2rem;
}

.aj-about-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}

.aj-stat {
    background: white;
    padding: 30px;
    border-radius: 10px;
    text-align: center;
    box-shadow: 0 5px 15px rgba(0,0,0,0.05);
}

.aj-stat-number {
    font-size: 2.5rem;
    font-weight: 700;
    color: var(--aj-primary);
    display: block;
    margin-bottom: 5px;
}

.aj-stat-label {
    color: var(--aj-gray);
    font-size: 1rem;
}

/* Services Section */
.aj-services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
}

.aj-service-card {
    background: white;
    padding: 40px 30px;
    border-radius: 10px;
    box-shadow: 0 5px 15px rgba(0,0,0,0.05);
    transition: all 0.3s ease;
    border-top: 4px solid var(--aj-primary);
}

.aj-service-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 15px 30px rgba(0,0,0,0.1);
}

.aj-service-icon {
    width: 70px;
    height: 70px;
    background: var(--aj-light);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 25px;
}

.aj-service-icon i {
    font-size: 1.8rem;
    color: var(--aj-primary);
}

.aj-service-card h3 {
    text-align: center;
    font-size: 1.5rem;
    margin-bottom: 20px;
    color: var(--aj-primary-dark);
}

.aj-service-card ul {
    list-style: none;
    padding-left: 0;
}

.aj-service-card li {
    padding: 10px 0;
    border-bottom: 1px dashed var(--aj-light-gray);
    position: relative;
    padding-left: 25px;
}

.aj-service-card li:before {
    content: '✓';
    position: absolute;
    left: 0;
    color: var(--aj-primary);
    font-weight: bold;
}

/* Portfolio Section */
.aj-portfolio-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
    gap: 30px;
}

.aj-portfolio-item {
    position: relative;
    border-radius: 10px;
    overflow: hidden;
    height: 250px;
}

.aj-portfolio-item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.5s ease;
}

.aj-portfolio-overlay {
    position: absolute;
    bottom: -100%;
    left: 0;
    right: 0;
    background: rgba(108, 99, 255, 0.9);
    color: white;
    padding: 20px;
    transition: all 0.3s ease;
}

.aj-portfolio-item:hover .aj-portfolio-overlay {
    bottom: 0;
}

.aj-portfolio-item:hover img {
    transform: scale(1.1);
}

/* Contact Section */
.aj-contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 50px;
}

.aj-contact-info h3, .aj-contact-form h3 {
    font-size: 1.5rem;
    color: var(--aj-primary-dark);
    margin-bottom: 30px;
    position: relative;
}

.aj-contact-info h3::after, .aj-contact-form h3::after {
    content: '';
    display: block;
    width: 50px;
    height: 3px;
    background: var(--aj-secondary);
    margin-top: 10px;
}

.aj-contact-method {
    display: flex;
    align-items: center;
    gap: 15px;
    margin-bottom: 20px;
}

.aj-contact-method i {
    width: 40px;
    height: 40px;
    background: var(--aj-light);
    color: var(--aj-primary);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.aj-social-links {
    display: flex;
    gap: 15px;
    margin-top: 30px;
}

.aj-social-links a {
    width: 40px;
    height: 40px;
    background: var(--aj-primary);
    color: white;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.3s ease;
}

.aj-social-links a:hover {
    background: var(--aj-secondary);
    transform: translateY(-5px);
}

/* Responsive Styles */
@media (max-width: 992px) {
    .aj-about-grid, .aj-contact-grid {
        grid-template-columns: 1fr;
    }
    
    .aj-about-content {
        order: 2;
    }
    
    .aj-about-stats {
        order: 1;
    }
}

@media (max-width: 768px) {
    .aj-hero {
        padding: 100px 0 60px;
    }
    
    .aj-hero h1 {
        font-size: 2.2rem;
    }
    
    .aj-hero h2 {
        font-size: 1.4rem;
    }
    
    .aj-section {
        padding: 60px 0;
    }
    
    .aj-skills {
        grid-template-columns: 1fr;
    }
    
    .aj-about-stats {
        grid-template-columns: 1fr;
    }
}

@media (max-width: 576px) {
    .aj-hero-btns {
        flex-direction: column;
    }
    
    .aj-portfolio-grid {
        grid-template-columns: 1fr;
    }
    
    .aj-services-grid {
        grid-template-columns: 1fr;
    }
}
</style>

<script>
jQuery(document).ready(function($) {
    // Technology tabs functionality
    $('.aj-tech-tab').click(function() {
        $('.aj-tech-tab').removeClass('active');
        $(this).addClass('active');
        
        var tabId = $(this).data('tab');
        $('.aj-tech-content').removeClass('active');
        $('#' + tabId).addClass('active');
    });
    
    // Smooth scrolling for anchor links
    $('a[href*="#"]').on('click', function(e) {
        e.preventDefault();
        
        $('html, body').animate(
            {
                scrollTop: $($(this).attr('href')).offset().top - 80,
            },
            500,
            'linear'
        );
    });
    
    // Portfolio item hover effect for touch devices
    if ('ontouchstart' in window) {
        $('.aj-portfolio-item').click(function() {
            $(this).toggleClass('hover');
        });
    }
});
</script>
