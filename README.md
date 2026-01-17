<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Anush Shiwakoti - Cyber Security Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Roboto:wght@300;400;700&display=swap" rel="stylesheet">
    <style>
        /* Global Styles */
        body {
            font-family: 'Roboto', sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #0d0d0d 0%, #1a1a1a 100%);
            color: #e0e0e0;
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
        }
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: radial-gradient(circle, rgba(0, 255, 65, 0.1) 1px, transparent 1px);
            background-size: 20px 20px;
            z-index: -1;
            opacity: 0.3;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(26, 26, 26, 0.9);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 10px 20px;
            box-shadow: 0 2px 10px rgba(0, 255, 65, 0.3);
        }
        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            margin: 0;
            padding: 0;
        }
        nav li {
            margin: 0 20px;
        }
        nav a {
            color: #00ff41;
            text-decoration: none;
            font-weight: 700;
            transition: color 0.3s;
        }
        nav a:hover {
            color: #00cc33;
        }
        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background: linear-gradient(135deg, #0d0d0d 0%, #1a1a1a 50%, #0d0d0d 100%);
            position: relative;
        }
        .hero::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, transparent, #00ff41, transparent);
        }
        .avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 4px solid #00ff41;
            box-shadow: 0 0 20px rgba(0, 255, 65, 0.5);
            margin-bottom: 20px;
            animation: glow 2s ease-in-out infinite alternate;
        }
        .hero h1 {
            font-family: 'Orbitron', sans-serif;
            font-size: 3em;
            margin: 10px 0;
            color: #00ff41;
            text-shadow: 0 0 10px #00ff41;
        }
        .bio {
            font-size: 1.2em;
            max-width: 600px;
            margin: 20px auto;
            animation: type 3s steps(40, end);
            overflow: hidden;
            white-space: nowrap;
            border-right: 2px solid #00ff41;
        }
        /* Sections */
        .section {
            margin: 80px 0;
            padding: 40px 20px;
            opacity: 0;
            transform: translateY(50px);
            transition: opacity 0.6s, transform 0.6s;
        }
        .section.visible {
            opacity: 1;
            transform: translateY(0);
        }
        .section h2 {
            font-family: 'Orbitron', sans-serif;
            text-align: center;
            color: #00ff41;
            margin-bottom: 40px;
            text-shadow: 0 0 10px #00ff41;
        }
        /* Skills */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }
        .skill-item {
            background: rgba(42, 42, 42, 0.8);
            padding: 20px;
            border-radius: 10px;
            border: 1px solid #00ff41;
            box-shadow: 0 4px 15px rgba(0, 255, 65, 0.2);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .skill-item:hover {
            transform: scale(1.05);
            box-shadow: 0 6px 20px rgba(0, 255, 65, 0.4);
        }
        .skill-bar {
            background: #333;
            border-radius: 10px;
            height: 10px;
            overflow: hidden;
            margin-top: 10px;
        }
        .skill-fill {
            height: 100%;
            background: linear-gradient(90deg, #00ff41, #00cc33);
            width: 0%;
            transition: width 1.5s ease-in-out;
        }
        /* Projects Grid */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        .project-card {
            background: rgba(42, 42, 42, 0.9);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.5);
            transition: transform 0.3s, box-shadow 0.3s;
            border: 2px solid transparent;
        }
        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 12px 35px rgba(0, 255, 65, 0.3);
            border-color: #00ff41;
        }
        .project-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
            transition: transform 0.3s;
        }
        .project-card:hover .project-image {
            transform: scale(1.1);
        }
        .project-content {
            padding: 20px;
        }
        .project-title {
            font-family: 'Orbitron', sans-serif;
            font-size: 1.5em;
            margin-bottom: 10px;
            color: #00ff41;
        }
        .project-description {
            margin-bottom: 15px;
        }
        .view-button {
            display: inline-block;
            background: linear-gradient(90deg, #00ff41, #00cc33);
            color: #0d0d0d;
            padding: 12px 20px;
            text-decoration: none;
            border-radius: 25px;
            font-weight: bold;
            transition: background 0.3s, transform 0.3s;
        }
        .view-button:hover {
            background: linear-gradient(90deg, #00cc33, #009926);
            transform: scale(1.05);
        }
        /* Contact */
        .contact-form {
            max-width: 500px;
            margin: 0 auto;
            background: rgba(42, 42, 42, 0.8);
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(0, 255, 65, 0.2);
        }
        .contact-form input, .contact-form textarea {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #00ff41;
            border-radius: 5px;
            background: #1a1a1a;
            color: #e0e0e0;
        }
        .contact-form button {
            background: #00ff41;
            color: #0d0d0d;
            padding: 12px 20px;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-weight: bold;
            transition: background 0.3s;
        }
        .contact-form button:hover {
            background: #00cc33;
        }
        /* Footer */
        .footer {
            text-align: center;
            padding: 20px;
            background: rgba(26, 26, 26, 0.9);
            border-top: 2px solid #00ff41;
        }
        .social-links a {
            margin: 0 15px;
            color: #00ff41;
            text-decoration: none;
            font-size: 1.5em;
            transition: color 0.3s;
        }
        .social-links a:hover {
            color: #00cc33;
        }
        /* Animations */
        @keyframes glow {
            from { box-shadow: 0 0 20px rgba(0, 255, 65, 0.5); }
            to { box-shadow: 0 0 30px rgba(0, 255, 65, 0.8); }
        }
        @keyframes type {
            from { width: 0; }
            to { width: 100%; }
        }
        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 { font-size: 2em; }
            .projects-grid, .skills-grid { grid-template-columns: 1fr; }
            nav ul { flex-direction: column; }
        }
    </style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#hero">Home</a></li>
            <li><a href="#skills">Skills</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <section id="hero" class="hero">
        <div>
            <img id="avatar" class="avatar" src="" alt="Avatar">
            <h1 id="name"></h1>
            <p id="bio"></p>
        </div>
    </section>

    <div class="container">
        <section id="skills" class="section">
            <h2>Skills</h2>
            <div id="skills-grid" class="skills-grid"></div>
        </section>

        <section id="projects" class="section">
            <h2>Projects</h2>
            <div id="projects-grid" class="projects-grid"></div>
        </section>

        <section id="contact" class="section">
            <h2>Contact</h2>
            <form class="contact-form" action="https://formspree.io/f/your-form-id" method="POST">
                <input type="text" name="name" placeholder="Your Name" required>
                <input type="email" name="email" placeholder="Your Email" required>
                <textarea name="message" placeholder="Your Message" rows="5" required></textarea>
                <button type="submit">Send Message</button>
            </form>
        </section>
    </div>

    <footer class="footer">
        <div class="social-links">
            <a id="linkedin-link" href="" target="_blank">LinkedIn</a>
            <a id="github-link" href="" target="_blank">GitHub</a>
            <a id="twitter-link" href="" target="_blank">Twitter</a>
        </div>
        <p>&copy; <span id="year"></span> Anush Shiwakoti. All rights reserved.</p>
    </footer>

    <script>
        // Simulated portfolio data (replace with your real data)
        const portfolio = {
            name: "Anush Shiwakoti",
            avatar: "https://via.placeholder.com/150",
            bio: "Cyber security enthusiast and aspiring ethical hacker. Passionate about protecting digital assets, exploring vulnerabilities, and learning through CTFs. Currently a computer science student diving into penetration testing, cryptography, and network security.",
            skills: [
                { name: "Penetration Testing", level: 75 },
                { name: "Cryptography", level: 70 },
                { name: "Network Security", level: 80 },
                { name: "Python Scripting", level: 85 },
                { name: "Ethical Hacking", level: 65 }
            ],
            projects: [
                {
                    title: "Vulnerability Scanner Tool",
                    image: "https://via.placeholder.com/300x200",
                    description: "A Python-based tool for scanning common vulnerabilities in web apps. Features automated checks for SQL injection and XSS.",
                    link: "https://github.com/anushshiwakoti/vuln-scanner"
                },
                {
                    title: "CTF Writeups Collection",
                    image: "https://via.placeholder.com/300x200",
                    description: "Detailed writeups from Capture The Flag challenges on platforms like HackTheBox and TryHackMe. Includes solutions for forensics and crypto puzzles.",
                    link: "https://github.com/anushshiwakoti/ctf-writeups"
                },
                {
                    title: "Network Security Blog",
                    image: "https://via.placeholder.com/300x200",
                    description: "A blog series on network security basics, including firewall configurations and intrusion detection. Updated with latest trends.",
                    link: "https://anushshiwakoti.github.io/security-blog"
                }
            ],
            social: {
                linkedin: "https://www.linkedin.com/in/anush-shiwakoti-96506a391/",
                github: "https://github.com/anushshiwakoti",
                twitter: "https://twitter.com/anushshiwakoti"
            }
        };

        // Function to load portfolio data
        function loadPortfolio(data) {
            document.getElementById('avatar').src = data.avatar;
            document.getElementById('name').textContent = data.name;
            document.getElementBy
