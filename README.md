<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aryan Dhiman | Developer Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Orbitron:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #00f7ff;
            --secondary: #ff2a6d;
            --dark: #0f0c29;
            --darker: #05031a;
            --light: #ffffff;
            --gray: #a5b3c9;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, var(--dark), #302b63, #24243e);
            color: var(--light);
            min-height: 100vh;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }
        
        /* Header Section */
        .header {
            text-align: center;
            padding: 3rem 0;
            position: relative;
        }
        
        .profile-image {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            margin: 0 auto 1.5rem;
            border: 4px solid var(--primary);
            box-shadow: 0 0 25px var(--primary);
            overflow: hidden;
            position: relative;
            animation: float 6s ease-in-out infinite;
        }
        
        .profile-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .name {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 15px rgba(0, 247, 255, 0.5);
            font-family: 'Orbitron', sans-serif;
            letter-spacing: 2px;
        }
        
        .tagline {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            color: var(--gray);
            position: relative;
            display: inline-block;
        }
        
        .tagline::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            border-radius: 3px;
        }
        
        /* Social Links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 2rem;
        }
        
        .social-link {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            color: var(--light);
            font-size: 1.2rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .social-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: all 0.5s ease;
        }
        
        .social-link:hover::before {
            left: 100%;
        }
        
        .social-link:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 247, 255, 0.3);
            color: var(--primary);
            border-color: var(--primary);
        }
        
        /* Sections */
        .section {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 2.5rem;
            margin-bottom: 2.5rem;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease;
        }
        
        .section:hover {
            transform: translateY(-5px);
        }
        
        .section-title {
            font-size: 2rem;
            margin-bottom: 1.5rem;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 10px;
            font-family: 'Orbitron', sans-serif;
        }
        
        .section-title i {
            color: var(--secondary);
        }
        
        /* Certifications */
        .cert-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
        }
        
        .cert-card {
            background: rgba(255, 255, 255, 0.08);
            border-radius: 15px;
            padding: 1.5rem;
            border-left: 4px solid var(--primary);
            transition: all 0.3s ease;
        }
        
        .cert-card:hover {
            background: rgba(255, 255, 255, 0.12);
            transform: translateX(5px);
        }
        
        .cert-name {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--light);
        }
        
        .cert-issuer {
            color: var(--gray);
            margin-bottom: 0.5rem;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .cert-date {
            color: var(--primary);
            font-size: 0.9rem;
        }
        
        /* Projects */
        .project-card {
            background: rgba(255, 255, 255, 0.08);
            border-radius: 15px;
            padding: 2rem;
            margin-bottom: 2rem;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 5px;
            height: 100%;
            background: linear-gradient(to bottom, var(--primary), var(--secondary));
        }
        
        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }
        
        .project-title {
            font-size: 1.8rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }
        
        .project-desc {
            color: var(--gray);
            margin-bottom: 1.5rem;
            line-height: 1.6;
        }
        
        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
            margin-bottom: 1.5rem;
        }
        
        .tech-item {
            background: rgba(0, 247, 255, 0.1);
            color: var(--primary);
            padding: 0.4rem 1rem;
            border-radius: 20px;
            font-size: 0.9rem;
            border: 1px solid rgba(0, 247, 255, 0.3);
        }
        
        .project-links {
            display: flex;
            gap: 1rem;
        }
        
        .project-link {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            color: var(--light);
            text-decoration: none;
            padding: 0.6rem 1.2rem;
            border-radius: 30px;
            background: rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .project-link:hover {
            background: var(--primary);
            color: var(--dark);
            transform: translateY(-3px);
        }
        
        /* Tech Stack */
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 1.5rem;
        }
        
        .tech-category {
            margin-bottom: 2rem;
        }
        
        .category-title {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: var(--secondary);
            border-bottom: 2px solid rgba(255, 42, 109, 0.3);
            padding-bottom: 0.5rem;
        }
        
        .tech-badge {
            background: rgba(255, 255, 255, 0.08);
            border-radius: 10px;
            padding: 1rem;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .tech-badge:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 0.12);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }
        
        .tech-icon {
            font-size: 2rem;
            margin-bottom: 0.5rem;
            color: var(--primary);
        }
        
        .tech-name {
            font-size: 0.9rem;
            color: var(--light);
        }
        
        /* Stats */
        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
        }
        
        .stat-card {
            background: rgba(255, 255, 255, 0.08);
            border-radius: 15px;
            padding: 1.5rem;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }
        
        .stat-title {
            font-size: 1rem;
            color: var(--gray);
            margin-bottom: 0.5rem;
        }
        
        .stat-value {
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary);
            font-family: 'Orbitron', sans-serif;
        }
        
        /* Spotify */
        .spotify-card {
            background: rgba(255, 255, 255, 0.08);
            border-radius: 15px;
            padding: 2rem;
            display: flex;
            align-items: center;
            gap: 2rem;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .spotify-cover {
            width: 150px;
            height: 150px;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
        }
        
        .spotify-cover img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .spotify-info h3 {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
            color: var(--primary);
        }
        
        .spotify-info p {
            color: var(--gray);
            margin-bottom: 1rem;
        }
        
        .spotify-play {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: #1DB954;
            color: white;
            padding: 0.7rem 1.5rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        
        .spotify-play:hover {
            background: #1ed760;
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(29, 185, 84, 0.3);
        }
        
        /* Animations */
        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-15px);
            }
        }
        
        @keyframes glow {
            0%, 100% {
                box-shadow: 0 0 5px var(--primary), 0 0 10px var(--primary);
            }
            50% {
                box-shadow: 0 0 20px var(--primary), 0 0 30px var(--primary);
            }
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .name {
                font-size: 2.5rem;
            }
            
            .section {
                padding: 1.5rem;
            }
            
            .cert-grid, .tech-grid, .stats-container {
                grid-template-columns: 1fr;
            }
            
            .spotify-card {
                flex-direction: column;
                text-align: center;
            }
        }
        
        /* Particles Background */
        #particles-js {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: -1;
        }
    </style>
</head>
<body>
    <div id="particles-js"></div>
    
    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <div class="profile-image">
                <img src="https://imgs.search.brave.com/6vnlt73NoBsVzbZAsUL6zriLJ4WXC0C7EeQ9ell1hes/rs:fit:860:0:0:0/g:ce/aHR0cHM6Ly9naWZk/Yi5jb20vaW1hZ2Vz/L2hpZ2gvcHJvZ3Jh/bW1pbmctYW5ncnkt/cHVuY2hpbmcta2V5/Ym9hcmQtZnc0NXlo/MmUzOWcyNHlsYi5n/aWY.gif" alt="Aryan Dhiman">
            </div>
            <h1 class="name">Aryan Dhiman</h1>
            <p class="tagline">I can learn, build, deploy</p>
            
            <div class="social-links">
                <a href="https://discord.gg/aryan_9" class="social-link">
                    <i class="fab fa-discord"></i>
                </a>
                <a href="https://instagram.com/https://www.instagram.com/aryan_dhiman09/" class="social-link">
                    <i class="fab fa-instagram"></i>
                </a>
                <a href="https://linkedin.com/in/https://www.linkedin.com/in/aryan-dhiman-a8974628b/" class="social-link">
                    <i class="fab fa-linkedin-in"></i>
                </a>
                <a href="https://github.com/Aryanplux" class="social-link">
                    <i class="fab fa-github"></i>
                </a>
            </div>
        </header>
        
        <!-- Certifications Section -->
        <section class="section">
            <h2 class="section-title"><i class="fas fa-certificate"></i> Certifications & Education</h2>
            <div class="cert-grid">
                <div class="cert-card">
                    <h3 class="cert-name">AWS Cloud Practitioner</h3>
                    <p class="cert-issuer"><i class="fas fa-building"></i> Amazon Web Services</p>
                    <p class="cert-date"><i class="far fa-calendar"></i> July 2025</p>
                </div>
                <div class="cert-card">
                    <h3 class="cert-name">Microsoft Azure Fundamentals</h3>
                    <p class="cert-issuer"><i class="fas fa-building"></i> Microsoft Corporation</p>
                    <p class="cert-date"><i class="far fa-calendar"></i> July 2025</p>
                </div>
                <div class="cert-card">
                    <h3 class="cert-name">Google Cloud Digital Leader</h3>
                    <p class="cert-issuer"><i class="fas fa-building"></i> Google LLC</p>
                    <p class="cert-date"><i class="far fa-calendar"></i> July 2025</p>
                </div>
            </div>
        </section>
        
        <!-- Projects Section -->
        <section class="section">
            <h2 class="section-title"><i class="fas fa-code"></i> Major Projects</h2>
            
            <div class="project-card">
                <h3 class="project-title">UniKart</h3>
                <p class="project-desc">Runner-Up, Inter College Hackathon. Team: Hackuna Matata (Aryan Dhiman, Samriddhi Chauhan, Lavanya Garg, Nitika Thakur, Vikas Kaushal). UniKart is a secure, university-exclusive digital marketplace empowering students to monetize skills and exchange products with AI-based matching and secure payments. Features university email verification onboarding, gamification badges, and auto-portfolio generation.</p>
                
                <div class="tech-stack">
                    <span class="tech-item">React</span>
                    <span class="tech-item">Django REST</span>
                    <span class="tech-item">MySQL</span>
                    <span class="tech-item">Python AI</span>
                    <span class="tech-item">UPI Payments</span>
                </div>
                
                <div class="project-links">
                    <a href="https://youtu.be/UOp9HBIOCY4" class="project-link">
                        <i class="fab fa-youtube"></i> YouTube Tutorial
                    </a>
                    <a href="https://github.com/Aryanplux/UniKart" class="project-link">
                        <i class="fab fa-github"></i> GitHub
                    </a>
                    <a href="https://github.com/Aryanplux/UniKart/blob/main/UNIKART%20Documentation.pdf" class="project-link">
                        <i class="fas fa-file-pdf"></i> Documentation
                    </a>
                </div>
            </div>
        </section>
        
        <!-- Tech Stack Section -->
        <section class="section">
            <h2 class="section-title"><i class="fas fa-laptop-code"></i> Tech Stack</h2>
            
            <div class="tech-category">
                <h3 class="category-title">Frontend</h3>
                <div class="tech-grid">
                    <div class="tech-badge">
                        <i class="fab fa-react tech-icon"></i>
                        <p class="tech-name">React</p>
                    </div>
                </div>
            </div>
            
            <div class="tech-category">
                <h3 class="category-title">Backend</h3>
                <div class="tech-grid">
                    <div class="tech-badge">
                        <i class="fab fa-python tech-icon"></i>
                        <p class="tech-name">Django</p>
                    </div>
                </div>
            </div>
            
            <div class="tech-category">
                <h3 class="category-title">Languages & Frameworks</h3>
                <div class="tech-grid">
                    <div class="tech-badge">
                        <i class="fab fa-python tech-icon"></i>
                        <p class="tech-name">Python</p>
                    </div>
                    <div class="tech-badge">
                        <i class="fab fa-java tech-icon"></i>
                        <p class="tech-name">Java</p>
                    </div>
                    <div class="tech-badge">
                        <i class="fas fa-leaf tech-icon"></i>
                        <p class="tech-name">Spring Boot</p>
                    </div>
                </div>
            </div>
            
            <div class="tech-category">
                <h3 class="category-title">Databases & Others</h3>
                <div class="tech-grid">
                    <div class="tech-badge">
                        <i class="fas fa-database tech-icon"></i>
                        <p class="tech-name">MySQL</p>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Stats Section -->
        <section class="section">
            <h2 class="section-title"><i class="fas fa-chart-bar"></i> GitHub & Coding Stats</h2>
            
            <div class="stats-container">
                <div class="stat-card">
                    <p class="stat-title">GitHub Followers</p>
                    <p class="stat-value">127</p>
                </div>
                <div class="stat-card">
                    <p class="stat-title">Repositories</p>
                    <p class="stat-value">24</p>
                </div>
                <div class="stat-card">
                    <p class="stat-title">LeetCode Solved</p>
                    <p class="stat-value">85</p>
                </div>
                <div class="stat-card">
                    <p class="stat-title">Projects Completed</p>
                    <p class="stat-value">12</p>
                </div>
            </div>
        </section>
        
        <!-- Spotify Section -->
        <section class="section">
            <h2 class="section-title"><i class="fab fa-spotify"></i> Spotify Playlist</h2>
            
            <div class="spotify-card">
                <div class="spotify-cover">
                    <img src="https://images.unsplash.com/photo-1571330735066-03aaa9429d89?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80" alt="Lilo & Stitch Playlist">
                </div>
                <div class="spotify-info">
                    <h3>Lilo x Stitch Playlist</h3>
                    <p>A curated selection of coding focus tracks and relaxing beats</p>
                    <a href="https://open.spotify.com/playlist/5Ymts0OPxrphCHcKZekPqW?si=8d73c1bab9bd428b" class="spotify-play">
                        <i class="fab fa-spotify"></i> Play on Spotify
                    </a>
                </div>
            </div>
        </section>
    </div>
    
    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script>
        // Initialize particles.js
        particlesJS("particles-js", {
            particles: {
                number: { value: 80, density: { enable: true, value_area: 800 } },
                color: { value: "#00f7ff" },
                shape: { type: "circle" },
                opacity: { value: 0.5, random: true },
                size: { value: 3, random: true },
                line_linked: {
                    enable: true,
                    distance: 150,
                    color: "#00f7ff",
                    opacity: 0.4,
                    width: 1
                },
                move: {
                    enable: true,
                    speed: 2,
                    direction: "none",
                    random: true,
                    straight: false,
                    out_mode: "out",
                    bounce: false
                }
            },
            interactivity: {
                detect_on: "canvas",
                events: {
                    onhover: { enable: true, mode: "repulse" },
                    onclick: { enable: true, mode: "push" },
                    resize: true
                }
            }
        });
        
        // Add scroll animations
        document.addEventListener('DOMContentLoaded', function() {
            const sections = document.querySelectorAll('.section');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = 1;
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, { threshold: 0.1 });
            
            sections.forEach(section => {
                section.style.opacity = 0;
                section.style.transform = 'translateY(20px)';
                section.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
                observer.observe(section);
            });
        });
    </script>
</body>
</html>
