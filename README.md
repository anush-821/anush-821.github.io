<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Anush Shiwakoti - Cyber Security Portfolio</title>
    <style>
        /* Global Styles */
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #0d0d0d;
            color: #e0e0e0;
            line-height: 1.6;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        /* Header */
        .header {
            text-align: center;
            padding: 50px 20px;
            background-color: #1a1a1a;
            border-bottom: 2px solid #00ff41; /* Green accent for cyber theme */
        }
        .avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 4px solid #00ff41;
            margin-bottom: 20px;
        }
        .header h1 {
            margin: 10px 0;
            color: #00ff41;
        }
        /* Bio */
        .bio {
            margin: 40px 0;
            text-align: center;
            font-size: 1.2em;
        }
        /* Projects Grid */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 40px 0;
        }
        .project-card {
            background-color: #2a2a2a;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 8px rgba(0,0,0,0.5);
            transition: transform 0.3s;
            border: 1px solid #00ff41;
        }
        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 12px rgba(0,255,65,0.3);
        }
        .project-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }
        .project-content {
            padding: 15px;
        }
        .project-title {
            font-size: 1.5em;
            margin-bottom: 10px;
            color: #00ff41;
        }
        .project-description {
            margin-bottom: 15px;
        }
        .view-button {
            display: inline-block;
            background-color: #00ff41;
            color: #0d0d0d;
            padding: 10px 15px;
            text-decoration: none;
            border-radius: 5px;
            transition: background-color 0.3s;
            font-weight: bold;
        }
        .view-button:hover {
            background-color: #00cc33;
        }
        /* Footer */
        .footer {
            text-align: center;
            padding: 20px;
            background-color: #1a1a1a;
            border-top: 2px solid #00ff41;
        }
        .social-links a {
            margin: 0 10px;
            color: #00ff41;
            text-decoration: none;
            font-size: 1.5em;
        }
        .social-links a:hover {
            color: #00cc33;
        }
        /* Responsive */
        @media (max-width: 768px) {
            .header {
                padding: 30px 20px;
            }
            .avatar {
                width: 120px;
                height: 120px;
            }
            .projects-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header class="header">
        <img id="avatar" class="avatar" src="" alt="Avatar">
        <h1 id="name"></h1>
        <p id="bio"></p>
    </header>

    <div class="container">
        <section class="projects">
            <h2 style="text-align: center; color: #00ff41; margin-bottom: 20px;">My Projects</h2>
            <div id="projects-grid" class="projects-grid"></div>
        </section>
    </div>

    <footer class="footer">
        <div class="social-links">
            <a id="linkedin-link" href="" target="_blank">LinkedIn</a>
            <a id="github-link" href="" target="_blank">GitHub</a>
            <a id="twitter-link" href="" target="_blank">Twitter</a>
        </div>
        <p>&copy; 2023 Anush Shiwakoti. All rights reserved.</p>
    </footer>

    <script>
        // Simulated portfolio data (replace with your real data)
        const portfolio = {
            name: "Anush Shiwakoti",
            avatar: "https://via.placeholder.com/150",
            bio: "Cyber security enthusiast and aspiring ethical hacker. Passionate about protecting digital assets, exploring vulnerabilities, and learning through CTFs. Currently a computer science student diving into penetration testing, cryptography, and network security.",
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
            document.getElementById('bio').textContent = data.bio;

            // Projects
            const projectsGrid = document.getElementById('projects-grid');
            data.projects.forEach(project => {
                const card = document.createElement('div');
                card.className = 'project-card';
                card.innerHTML = `
                    <img class="project-image" src="${project.image}" alt="${project.title}">
                    <div class="project-content">
                        <h3 class="project-title">${project.title}</h3>
                        <p class="project-description">${project.description}</p>
                        <a class="view-button" href="${project.link}" target="_blank">View Project</a>
                    </div>
                `;
                projectsGrid.appendChild(card);
            });

            // Social Links
            document.getElementById('linkedin-link').href = data.social.linkedin;
            document.getElementById('github-link').href = data.social.github;
            document.getElementById('twitter-link').href = data.social.twitter;
        }

        // Load on page load
        loadPortfolio(portfolio);
    </script>
</body>
</html>
