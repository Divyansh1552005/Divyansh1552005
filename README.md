<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Divyansh Sharma - Developer Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Noto Sans', Helvetica, Arial, sans-serif;
            background: #0d1117;
            color: #c9d1d9;
            line-height: 1.5;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 300px 1fr;
            gap: 24px;
        }

        .sidebar {
            display: flex;
            flex-direction: column;
            gap: 24px;
        }

        .profile-card {
            background: #161b22;
            border: 1px solid #30363d;
            border-radius: 6px;
            overflow: hidden;
        }

        .header-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
            display: block;
        }

        .profile-content {
            padding: 24px;
            text-align: center;
        }

        .profile-name {
            font-size: 24px;
            font-weight: 600;
            margin-bottom: 4px;
            color: #f0f6fc;
        }

        .profile-title {
            color: #8b949e;
            margin-bottom: 16px;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 8px;
            margin-bottom: 16px;
        }

        .social-btn {
            padding: 6px 12px;
            border-radius: 6px;
            font-size: 12px;
            text-decoration: none;
            color: white;
            font-weight: 500;
        }

        .social-btn.linkedin { background: #0077b5; }
        .social-btn.github { background: #171515; }
        .social-btn.twitter { background: #1da1f2; }

        .section {
            background: #161b22;
            border: 1px solid #30363d;
            border-radius: 6px;
            padding: 24px;
        }

        .section-title {
            font-size: 16px;
            font-weight: 600;
            margin-bottom: 16px;
            color: #f0f6fc;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .section-title::before {
            content: "📊";
        }

        .about-list {
            list-style: none;
        }

        .about-list li {
            margin-bottom: 8px;
            color: #8b949e;
            position: relative;
            padding-left: 16px;
        }

        .about-list li::before {
            content: "👉";
            position: absolute;
            left: 0;
        }

        .about-placeholder {
            background: #21262d;
            border: 1px dashed #30363d;
            border-radius: 4px;
            padding: 20px;
            color: #8b949e;
            font-style: italic;
            text-align: justify;
            margin: 16px 0;
        }

        .tech-section {
            display: flex;
            flex-direction: column;
            gap: 16px;
        }

        .tech-category h4 {
            color: #58a6ff;
            margin-bottom: 12px;
            font-size: 14px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .tech-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .tech-tag {
            background: #21262d;
            border: 1px solid #30363d;
            padding: 6px 12px;
            border-radius: 16px;
            font-size: 12px;
            color: #c9d1d9;
            display: flex;
            align-items: center;
            gap: 6px;
            transition: all 0.2s ease;
        }

        .tech-tag:hover {
            background: #30363d;
            border-color: #58a6ff;
        }

        .tech-icon {
            width: 16px;
            height: 16px;
            object-fit: contain;
        }

        .main-content {
            display: flex;
            flex-direction: column;
            gap: 24px;
        }

        .github-stats-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-bottom: 20px;
        }

        .github-stat-card {
            background: #161b22;
            border: 1px solid #30363d;
            border-radius: 8px;
            overflow: hidden;
        }

        .github-stat-card img {
            width: 100%;
            height: auto;
            display: block;
        }

        .streak-stats {
            grid-column: 1 / -1;
        }

        .repos-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 16px;
        }

        .repo-card {
            background: #161b22;
            border: 1px solid #30363d;
            border-radius: 6px;
            padding: 16px;
            transition: border-color 0.2s;
        }

        .repo-card:hover {
            border-color: #58a6ff;
        }

        .repo-name {
            color: #58a6ff;
            font-weight: 600;
            margin-bottom: 8px;
            text-decoration: none;
        }

        .repo-name:hover {
            text-decoration: underline;
        }

        .repo-description {
            color: #8b949e;
            font-size: 14px;
            margin-bottom: 12px;
        }

        .repo-meta {
            display: flex;
            gap: 16px;
            font-size: 12px;
            color: #8b949e;
        }

        .repo-meta span {
            display: flex;
            align-items: center;
            gap: 4px;
        }

        .language-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }

        .python { background: #3572a5; }
        .javascript { background: #f1e05a; }
        .react { background: #61dafb; }
        .html { background: #e34c26; }
        .css { background: #1572B6; }
        .cpp { background: #00599C; }

        .wakatime-stats {
            background: #161b22;
            border: 1px solid #30363d;
            border-radius: 6px;
            padding: 24px;
            margin-top: 20px;
        }

        .wakatime-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 12px;
        }

        .wakatime-bar {
            height: 8px;
            background: #21262d;
            border-radius: 4px;
            overflow: hidden;
            margin-top: 6px;
        }

        .wakatime-progress {
            height: 100%;
            background: linear-gradient(90deg, #58a6ff, #7c3aed);
            border-radius: 4px;
            transition: width 0.3s ease;
        }

        @media (max-width: 768px) {
            .container {
                grid-template-columns: 1fr;
            }
            
            .github-stats-container {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="sidebar">
            <div class="profile-card">
                <img src="https://raw.githubusercontent.com/Divyansh1552005/Divyansh1552005/main/header_img.jpg" alt="Divyansh Sharma Header" class="header-image" loading="lazy">
                <div class="profile-content">
                    <h1 class="profile-name">Divyansh Sharma</h1>
                    <p class="profile-title">@Divyansh1552005</p>
                    
                    <div class="social-links">
                        <a href="https://www.linkedin.com/in/divyansh-sharma-b05897286/" class="social-btn linkedin">LinkedIn</a>
                        <a href="https://github.com/Divyansh1552005" class="social-btn github">GitHub</a>
                        <a href="https://x.com/Divyansh1552005" class="social-btn twitter">Twitter</a>
                    </div>
                </div>
            </div>

            <div class="section">
                <h2 class="section-title">About Me:</h2>
                <div class="about-placeholder">
                    • Currently working on a Hospital Management System using the MERN stack with a built-in Generative AI medical chatbot.
                    <br />
• Exploring DevOps and cloud computing to scale my applications effectively.
<br />
• Aiming to become a full-stack developer and use AI to solve real-world problems.
<br />
• Fun facts: I love ice cream 🍦, play badminton regularly 🏸, and enjoy simplifying complex topics for others.
                </div>
            </div>

            <div class="section">
                <h2 class="section-title">🛠️ Tech Stack:</h2>
                <div class="tech-section">
                    <div class="tech-category">
                        <h4>💻 Languages:</h4>
                        <div class="tech-tags">
                            <span class="tech-tag">
                                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python" class="tech-icon">
                                Python
                            </span>
                            <span class="tech-tag">
                                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="JavaScript" class="tech-icon">
                                JavaScript
                            </span>
                            <span class="tech-tag">
                                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg" alt="C++" class="tech-icon">
                                C++
                            </span>
                            <span class="tech-tag">
                                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg" alt="C" class="tech-icon">
                                C
                            </span>
                        </div>
                    </div>
                    
                    <div class="tech-category">
                        <h4>🚀 Development:</h4>
                        <div class="tech-tags">
                            <span class="tech-tag">
                                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="HTML" class="tech-icon">
                                HTML
                            </span>
                            <span class="tech-tag">
                                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt="CSS" class="tech-icon">
                                CSS
                            </span>
                            <span class="tech-tag">
                                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" alt="React" class="tech-icon">
                                React
                            </span>
                            <span class="tech-tag">
                                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" alt="Node.js" class="tech-icon">
                                Node.js
                            </span>
                            <span class="tech-tag">
                                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/express/express-original.svg" alt="Express" class="tech-icon">
                                Express
                            </span>
                            <span class="tech-tag">
                                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg" alt="MongoDB" class="tech-icon">
                                MongoDB
                            </span>
                            <span class="tech-tag">
                                <svg class="tech-icon" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path d="M12 2L2 7L12 12L22 7L12 2Z" fill="#00D4AA"/>
                                    <path d="M2 17L12 22L22 17" stroke="#00D4AA" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                                    <path d="M2 12L12 17L22 12" stroke="#00D4AA" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                                </svg>
                                Pinecone DB
                            </span>
                            <span class="tech-tag">
                                <svg class="tech-icon" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path d="M4 8L12 4L20 8L12 12L4 8Z" fill="#1C3C3C"/>
                                    <path d="M4 12L12 16L20 12" stroke="#1C3C3C" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                                    <circle cx="12" cy="12" r="2" fill="#FFD700"/>
                                    <path d="M8 10L16 10" stroke="#FFD700" stroke-width="1.5"/>
                                    <path d="M8 14L16 14" stroke="#FFD700" stroke-width="1.5"/>
                                </svg>
                                LangChain
                            </span>
                        </div>
                    </div>

                    <div class="tech-category">
                        <h4>🔧 Tools:</h4>
                        <div class="tech-tags">
                            <span class="tech-tag">
                                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" alt="Git" class="tech-icon">
                                Git
                            </span>
                            <span class="tech-tag">
                                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg" alt="Linux" class="tech-icon">
                                Linux (Fedora)
                            </span>
                            <span class="tech-tag">
                                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jupyter/jupyter-original.svg" alt="Jupyter" class="tech-icon">
                                Jupyter Notebook
                            </span>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="main-content">
            <div class="section">
                <h2 class="section-title">📊 GitHub Statistics</h2>
                <div class="github-stats-container">
                    <div class="github-stat-card">
                        <img src="https://github-readme-stats.vercel.app/api?username=Divyansh1552005&theme=dark&hide_border=true&include_all_commits=true&count_private=true" alt="GitHub Stats" loading="lazy">
                    </div>
                    <div class="github-stat-card">
                        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Divyansh1552005&theme=dark&hide_border=true&include_all_commits=true&count_private=true&layout=compact" alt="Top Languages" loading="lazy">
                    </div>
                    <div class="github-stat-card streak-stats">
                        <img src="https://streak-stats.demolab.com?user=Divyansh1552005&theme=dark&hide_border=true" alt="GitHub Streak" loading="lazy">
                    </div>
                </div>

                <div class="wakatime-stats">
                    <h3 style="margin-bottom: 16px; color: #f0f6fc; display: flex; align-items: center; gap: 8px;">
                        ⏱️ Weekly Development Breakdown
                    </h3>
                    <div class="wakatime-item">
                        <span style="display: flex; align-items: center; gap: 8px;">
                            <div class="language-dot python"></div>
                            Python
                        </span>
                        <span>8 hrs 45 mins</span>
                    </div>
                    <div class="wakatime-bar">
                        <div class="wakatime-progress" style="width: 40%"></div>
                    </div>

                    <div class="wakatime-item">
                        <span style="display: flex; align-items: center; gap: 8px;">
                            <div class="language-dot javascript"></div>
                            JavaScript
                        </span>
                        <span>6 hrs 30 mins</span>
                    </div>
                    <div class="wakatime-bar">
                        <div class="wakatime-progress" style="width: 35%"></div>
                    </div>

                    <div class="wakatime-item">
                        <span style="display: flex; align-items: center; gap: 8px;">
                            <div class="language-dot react"></div>
                            React
                        </span>
                        <span>4 hrs 15 mins</span>
                    </div>
                    <div class="wakatime-bar">
                        <div class="wakatime-progress" style="width: 25%"></div>
                    </div>

                    <div class="wakatime-item">
                        <span style="display: flex; align-items: center; gap: 8px;">
                            <div class="language-dot cpp"></div>
                            C++
                        </span>
                        <span>3 hrs 20 mins</span>
                    </div>
                    <div class="wakatime-bar">
                        <div class="wakatime-progress" style="width: 20%"></div>
                    </div>

                    <div class="wakatime-item">
                        <span style="display: flex; align-items: center; gap: 8px;">
                            <div class="language-dot html"></div>
                            HTML/CSS
                        </span>
                        <span>2 hrs 45 mins</span>
                    </div>
                    <div class="wakatime-bar">
                        <div class="wakatime-progress" style="width: 15%"></div>
                    </div>
                </div>
            </div>

            <div class="section">
                <h2 class="section-title">📁 Featured Repositories</h2>
                <div class="repos-grid">
    <div class="repo-card">
        <a href="https://github.com/Divyansh1552005/Medical_Chatbot_OpenAI" class="repo-name">🤖 Medical Chatbot (OpenAI)</a>
        <p class="repo-description">A chatbot powered by OpenAI, designed to assist in basic medical queries and guidance.</p>
        <div class="repo-meta">
            <span><div class="language-dot python"></div>Python</span>
            <span>⭐ #</span>
            <span>🍴 #</span>
        </div>
    </div>

    <div class="repo-card">
        <a href="#" class="repo-name">🏥 Hospital Management System</a>
        <p class="repo-description">A full-stack web application for managing hospital records, patients, doctors, and integrating AI chat assistance.</p>
        <div class="repo-meta">
            <span><div class="language-dot react"></div>MERN Stack</span>
            <span>⭐ #</span>
            <span>🍴 #</span>
        </div>
    </div>

    <div class="repo-card">
        <a href="#" class="repo-name">🌐 Portfolio Website</a>
        <p class="repo-description">Personal portfolio website built with modern web technologies showcasing my projects and skills.</p>
        <div class="repo-meta">
            <span><div class="language-dot javascript"></div>JavaScript</span>
            <span>⭐ #</span>
            <span>🍴 #</span>
        </div>
    </div>
</div>

                </div>
            </div>
        </div>
    </div>

    <script>
        // Add smooth animations for progress bars
        document.addEventListener('DOMContentLoaded', function() {
            const progressBars = document.querySelectorAll('.wakatime-progress');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.animation = 'progressLoad 1.5s ease-out';
                    }
                });
            });

            progressBars.forEach(bar => observer.observe(bar));
        });

        // Add CSS animation for progress bars
        const style = document.createElement('style');
        style.textContent = `
            @keyframes progressLoad {
                from { width: 0; }
                to { width: var(--target-width); }
            }
        `;
        document.head.appendChild(style);

        // Set target widths for each progress bar
        document.querySelectorAll('.wakatime-progress').forEach((bar, index) => {
            const widths = ['40%', '35%', '25%', '20%', '15%'];
            bar.style.setProperty('--target-width', widths[index] || '10%');
        });
    </script>
</body>
</html>
