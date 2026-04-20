<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ankur Datta - Dark Gold Edition</title>
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }

        :root {
            --bg-dark: #0a0a0f;
            --bg-card: #12121a;
            --gold: #d4af37;
            --gold-light: #f4d03f;
            --red: #e63946;
            --red-glow: #ff1a1a;
            --white: #ffffff;
            --gray: #a0a0a0;
        }

        body {
            font-family: 'Space Grotesk', sans-serif;
            background: var(--bg-dark);
            min-height: 100vh;
            padding: 20px;
            overflow-x: hidden;
        }

        /* Animated Background Strips */
        .bg-strips {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
        }

        .strip {
            position: absolute;
            height: 2px;
            background: linear-gradient(90deg, transparent, var(--gold), var(--red), transparent);
            animation: stripMove 8s linear infinite;
            opacity: 0.6;
        }

        .strip:nth-child(1) { top: 10%; width: 60%; left: -60%; animation-delay: 0s; }
        .strip:nth-child(2) { top: 25%; width: 80%; left: -80%; animation-delay: 1s; }
        .strip:nth-child(3) { top: 40%; width: 50%; left: -50%; animation-delay: 2s; }
        .strip:nth-child(4) { top: 55%; width: 70%; left: -70%; animation-delay: 3s; }
        .strip:nth-child(5) { top: 70%; width: 90%; left: -90%; animation-delay: 4s; }
        .strip:nth-child(6) { top: 85%; width: 40%; left: -40%; animation-delay: 5s; }

        @keyframes stripMove {
            0% { transform: translateX(0); }
            100% { transform: translateX(250%); }
        }

        /* Glowing Orbs */
        .orb {
            position: fixed;
            border-radius: 50%;
            filter: blur(80px);
            z-index: -1;
            animation: orbFloat 10s ease-in-out infinite;
        }

        .orb-gold {
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(212,175,55,0.3), transparent);
            top: 10%;
            right: 10%;
            animation-delay: 0s;
        }

        .orb-red {
            width: 250px;
            height: 250px;
            background: radial-gradient(circle, rgba(230,57,70,0.25), transparent);
            bottom: 20%;
            left: 5%;
            animation-delay: 5s;
        }

        @keyframes orbFloat {
            0%, 100% { transform: translate(0, 0) scale(1); }
            25% { transform: translate(30px, -30px) scale(1.1); }
            50% { transform: translate(-20px, 20px) scale(0.9); }
            75% { transform: translate(20px, 10px) scale(1.05); }
        }

        .cv-container {
            max-width: 1000px;
            margin: 0 auto;
            background: var(--bg-card);
            border-radius: 24px;
            overflow: hidden;
            position: relative;
            border: 1px solid rgba(212,175,55,0.2);
            box-shadow:
                0 0 100px rgba(212,175,55,0.1),
                0 0 50px rgba(230,57,70,0.05),
                inset 0 0 60px rgba(212,175,55,0.03);
            animation: containerGlow 4s ease-in-out infinite;
        }

        @keyframes containerGlow {
            0%, 100% { box-shadow: 0 0 100px rgba(212,175,55,0.1), 0 0 50px rgba(230,57,70,0.05), inset 0 0 60px rgba(212,175,55,0.03); }
            50% { box-shadow: 0 0 120px rgba(212,175,55,0.15), 0 0 70px rgba(230,57,70,0.08), inset 0 0 80px rgba(212,175,55,0.05); }
        }

        /* Animated Border */
        .border-glow {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, var(--gold), var(--red), var(--gold), var(--red), var(--gold));
            background-size: 300% 100%;
            animation: borderShine 3s linear infinite;
        }

        @keyframes borderShine {
            0% { background-position: 0% 50%; }
            100% { background-position: 300% 50%; }
        }

        /* Header */
        .header {
            padding: 50px;
            background: linear-gradient(135deg, rgba(212,175,55,0.1), rgba(230,57,70,0.05));
            position: relative;
        }

        .header-content {
            display: flex;
            align-items: center;
            gap: 40px;
        }

        .photo-frame {
            width: 150px;
            height: 190px;
            border: 3px solid transparent;
            border-radius: 16px;
            background: linear-gradient(var(--bg-card), var(--bg-card)) padding-box,
                        linear-gradient(135deg, var(--gold), var(--red)) border-box;
            overflow: hidden;
            position: relative;
            animation: photoPulse 3s ease-in-out infinite;
        }

        @keyframes photoPulse {
            0%, 100% { box-shadow: 0 0 20px rgba(212,175,55,0.3); }
            50% { box-shadow: 0 0 40px rgba(212,175,55,0.6), 0 0 20px rgba(230,57,70,0.3); }
        }

        .photo-placeholder {
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            background: linear-gradient(145deg, #1a1a25, #0f0f15);
            color: var(--gray);
        }

        .photo-placeholder i {
            font-size: 40px;
            margin-bottom: 8px;
            color: var(--gold);
        }

        .header-info h1 {
            font-size: 42px;
            font-weight: 700;
            background: linear-gradient(135deg, var(--gold), var(--gold-light));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 8px;
        }

        .title {
            font-size: 16px;
            color: var(--red);
            font-weight: 500;
            letter-spacing: 3px;
            text-transform: uppercase;
            margin-bottom: 25px;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px 25px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--gray);
            font-size: 13px;
            transition: all 0.3s ease;
        }

        .contact-item:hover {
            color: var(--gold);
            transform: translateX(5px);
        }

        .contact-item i {
            width: 28px;
            height: 28px;
            background: rgba(212,175,55,0.1);
            border: 1px solid rgba(212,175,55,0.3);
            border-radius: 6px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 11px;
            color: var(--gold);
        }

        /* Main Layout */
        .main-content {
            display: grid;
            grid-template-columns: 320px 1fr;
        }

        .sidebar {
            padding: 40px 30px;
            background: rgba(10,10,15,0.5);
            border-right: 1px solid rgba(212,175,55,0.1);
        }

        .section {
            margin-bottom: 35px;
            animation: fadeInUp 0.8s ease-out;
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .section-title {
            font-size: 14px;
            font-weight: 600;
            color: var(--gold);
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 1px solid rgba(212,175,55,0.3);
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -1px;
            left: 0;
            width: 40px;
            height: 2px;
            background: var(--red);
            animation: lineExtend 2s ease-out infinite;
        }

        @keyframes lineExtend {
            0%, 100% { width: 40px; }
            50% { width: 80px; }
        }

        .skill-item {
            margin-bottom: 18px;
        }

        .skill-name {
            display: flex;
            justify-content: space-between;
            font-size: 12px;
            color: var(--white);
            margin-bottom: 8px;
        }

        .skill-bar {
            height: 6px;
            background: rgba(255,255,255,0.1);
            border-radius: 3px;
            overflow: hidden;
            position: relative;
        }

        .skill-progress {
            height: 100%;
            background: linear-gradient(90deg, var(--red), var(--gold));
            border-radius: 3px;
            animation: skillFill 1.5s ease-out;
            position: relative;
        }

        .skill-progress::after {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            bottom: 0;
            width: 30px;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4));
            animation: shimmer 2s infinite;
        }

        @keyframes skillFill {
            from { width: 0; }
        }

        @keyframes shimmer {
            0% { transform: translateX(-30px); }
            100% { transform: translateX(30px); }
        }

        .main-area {
            padding: 40px;
        }

        .content-section {
            margin-bottom: 35px;
        }

        .content-title {
            font-size: 18px;
            font-weight: 600;
            color: var(--gold);
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .content-title i {
            width: 36px;
            height: 36px;
            background: linear-gradient(135deg, var(--gold), var(--red));
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 14px;
            color: var(--bg-dark);
        }

        .timeline {
            position: relative;
            padding-left: 25px;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(180deg, var(--gold), var(--red), var(--gold));
        }

        .timeline-item {
            position: relative;
            margin-bottom: 28px;
            padding-left: 20px;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -30px;
            top: 4px;
            width: 10px;
            height: 10px;
            background: var(--red);
            border: 2px solid var(--gold);
            border-radius: 50%;
            animation: nodePulse 2s ease-in-out infinite;
        }

        @keyframes nodePulse {
            0%, 100% { box-shadow: 0 0 0 0 rgba(230,57,70,0.7); }
            50% { box-shadow: 0 0 0 10px rgba(230,57,70,0); }
        }

        .timeline-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 6px;
        }

        .timeline-title {
            font-size: 15px;
            font-weight: 600;
            color: var(--white);
        }

        .timeline-date {
            font-size: 11px;
            color: var(--gold);
            background: rgba(212,175,55,0.1);
            padding: 4px 10px;
            border-radius: 20px;
            border: 1px solid rgba(212,175,55,0.3);
        }

        .timeline-company {
            font-size: 13px;
            color: var(--red);
            font-weight: 500;
            margin-bottom: 8px;
        }

        .timeline-desc {
            font-size: 12px;
            color: var(--gray);
            line-height: 1.8;
        }

        .timeline-desc li {
            margin-bottom: 4px;
            padding-left: 15px;
            position: relative;
            list-style: none;
        }

        .timeline-desc li::before {
            content: '›';
            position: absolute;
            left: 0;
            color: var(--gold);
            font-weight: bold;
        }

        .edu-item {
            background: rgba(255,255,255,0.03);
            border-left: 3px solid var(--gold);
            padding: 15px;
            border-radius: 0 10px 10px 0;
            margin-bottom: 15px;
            transition: all 0.3s ease;
        }

        .edu-item:hover {
            background: rgba(212,175,55,0.05);
            transform: translateX(5px);
            border-left-color: var(--red);
        }

        .summary-box {
            background: linear-gradient(135deg, rgba(212,175,55,0.05), rgba(230,57,70,0.03));
            border: 1px solid rgba(212,175,55,0.2);
            border-radius: 12px;
            padding: 25px;
            position: relative;
            overflow: hidden;
        }

        .summary-box::before {
            content: '"';
            position: absolute;
            top: -10px;
            right: 20px;
            font-size: 80px;
            color: var(--gold);
            opacity: 0.1;
            font-family: serif;
        }

        .summary-text {
            font-size: 13px;
            color: var(--gray);
            line-height: 1.9;
            font-style: italic;
        }

        .footer {
            background: linear-gradient(90deg, rgba(212,175,55,0.1), rgba(230,57,70,0.1));
            padding: 20px;
            text-align: center;
            border-top: 1px solid rgba(212,175,55,0.2);
        }

        .footer-text {
            color: var(--gray);
            font-size: 11px;
            letter-spacing: 2px;
            text-transform: uppercase;
        }
    </style>
</head>
<body>
    <!-- Animated Background -->
    <div class="bg-strips">
        <div class="strip"></div>
        <div class="strip"></div>
        <div class="strip"></div>
        <div class="strip"></div>
        <div class="strip"></div>
        <div class="strip"></div>
    </div>
    <div class="orb orb-gold"></div>
    <div class="orb orb-red"></div>

    <div class="cv-container">
        <div class="border-glow"></div>

        <header class="header">
            <div class="header-content">
                <div class="photo-frame">
                    <div class="photo-placeholder">
                        <i class="fas fa-user"></i>
                        <span style="font-size: 10px;"><img src="#"/></span>
                    </div>
                </div>
                <div class="header-info">
                    <h1>Ankur Datta (Rana)</h1>
                    <p class="title">Self-Taught Developer & Technical Professional</p>
                    <div class="contact-grid">
                        <div class="contact-item"><i class="fas fa-envelope"></i> datta.ankur327@gmail.com</div>
                        <div class="contact-item"><i class="fas fa-phone"></i> +880-1517-824806</div>
                        <div class="contact-item"><i class="fas fa-map-marker-alt"></i> Feni/Fulgazi, Bangladesh</div>
                        <div class="contact-item"><i class="fas fa-calendar"></i> January 5, 1993</div>
                        <div class="contact-item"><i class="fab fa-linkedin"></i> linkedin.com/in/ankur-datta-cat006</div>
                        <div class="contact-item"><i class="fab fa-github"></i> github.com/Cat00006</div>
                    </div>
                </div>
            </div>
        </header>

        <div class="main-content">
            <aside class="sidebar">
                <div class="section">
                    <h3 class="section-title">Personal Info</h3>
                    <div style="font-size: 12px; color: #a0a0a0; line-height: 2;">
                        <div><strong style="color: #d4af37;">Full Name:</strong> Ankur Datta (Rana)</div>
                        <div><strong style="color: #d4af37;">Birth:</strong> January 5, 1993</div>
                        <div><strong style="color: #d4af37;">Nationality:</strong> Bangladeshi</div>
                        <div><strong style="color: #d4af37;">Languages:</strong> Bengali (Native), English</div>
                    </div>
                </div>

                <div class="section">
                    <h3 class="section-title">Digital Skills</h3>
                    <div class="skill-item">
                        <div class="skill-name"><span>Web Development</span><span>75%</span></div>
                        <div class="skill-bar"><div class="skill-progress" style="width: 75%"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name"><span>Survey Systems</span><span>85%</span></div>
                        <div class="skill-bar"><div class="skill-progress" style="width: 85%"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name"><span>Content Creation</span><span>80%</span></div>
                        <div class="skill-bar"><div class="skill-progress" style="width: 80%"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name"><span>Video Production</span><span>70%</span></div>
                        <div class="skill-bar"><div class="skill-progress" style="width: 70%"></div></div>
                    </div>
                </div>

                <div class="section">
                    <h3 class="section-title">Technical Skills</h3>
                    <div class="skill-item">
                        <div class="skill-name"><span>Electrical Maintenance</span><span>95%</span></div>
                        <div class="skill-bar"><div class="skill-progress" style="width: 95%"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name"><span>Power Plant Operations</span><span>90%</span></div>
                        <div class="skill-bar"><div class="skill-progress" style="width: 90%"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name"><span>Industrial Safety</span><span>85%</span></div>
                        <div class="skill-bar"><div class="skill-progress" style="width: 85%"></div></div>
                    </div>
                </div>

                <div class="section">
                    <h3 class="section-title">Tools</h3>
                    <div style="font-size: 11px; color: #a0a0a0; line-height: 1.9;">
                        • HTML & CSS • JavaScript<br>
                        • MS Office Suite<br>
                        • CMS Platforms<br>
                        • Survey Software<br>
                        • Video Editing
                    </div>
                </div>
            </aside>

            <main class="main-area">
                <div class="content-section">
                    <h2 class="content-title"><i class="fas fa-user-tie"></i> Professional Summary</h2>
                    <div class="summary-box">
                        <p class="summary-text">Technical professional with 10+ years of industrial experience in electrical maintenance and power plant operations (2012-2023). Successfully transitioned to digital entrepreneurship in 2020, building skills in web development, content creation, and software engineering through self-learning and mentorship under Cyber Prince (Sourav).</p>
                    </div>
                </div>

                <div class="content-section">
                    <h2 class="content-title"><i class="fas fa-briefcase"></i> Experience</h2>
                    <div class="timeline">
                        <div class="timeline-item">
                            <div class="timeline-header">
                                <h3 class="timeline-title">Freelance Developer & Content Creator</h3>
                                <span class="timeline-date">2020 - Present</span>
                            </div>
                            <div class="timeline-company">Cyber Prince Network (Online)</div>
                            <div class="timeline-desc">
                                <ul>
                                    <li>Self-taught software development through mentorship</li>
                                    <li>Built web applications and websites for clients</li>
                                    <li>Created content for blogs and video platforms</li>
                                    <li>Developed survey systems and data collection tools</li>
                                </ul>
                            </div>
                        </div>

                        <div class="timeline-item">
                            <div class="timeline-header">
                                <h3 class="timeline-title">Senior Technician - Power Plant</h3>
                                <span class="timeline-date">2019 - Jan 2023</span>
                            </div>
                            <div class="timeline-company">200MW Power Plant, Bangla CAT</div>
                            <div class="timeline-desc">
                                <ul>
                                    <li>Supervised electrical systems maintenance and operations</li>
                                    <li>Led preventive maintenance programs</li>
                                    <li>Mentored junior technicians and apprentices</li>
                                </ul>
                            </div>
                        </div>

                        <div class="timeline-item">
                            <div class="timeline-header">
                                <h3 class="timeline-title">Technician - Electrical</h3>
                                <span class="timeline-date">2015 - 2018</span>
                            </div>
                            <div class="timeline-company">Bangla CAT</div>
                            <div class="timeline-desc">
                                <ul>
                                    <li>Performed routine maintenance on electrical systems</li>
                                    <li>Troubleshot electrical faults and implemented solutions</li>
                                </ul>
                            </div>
                        </div>

                        <div class="timeline-item">
                            <div class="timeline-header">
                                <h3 class="timeline-title">Apprentice - Electrical</h3>
                                <span class="timeline-date">2012 - 2015</span>
                            </div>
                            <div class="timeline-company">Bangla CAT</div>
                            <div class="timeline-desc">
                                <ul>
                                    <li>Completed 3-year apprenticeship program</li>
                                    <li>Learned industrial electrical standards and safety</li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="content-section">
                    <h2 class="content-title"><i class="fas fa-graduation-cap"></i> Education</h2>
                    <div class="edu-item">
                        <div style="display: flex; justify-content: space-between; margin-bottom: 4px;">
                            <span style="color: #fff; font-weight: 500;">Higher Secondary (HSC) - Science</span>
                            <span style="color: #d4af37; font-size: 11px;">2013</span>
                        </div>
                        <div style="color: #a0a0a0; font-size: 12px;">Fulgazi Government College</div>
                    </div>
                    <div class="edu-item">
                        <div style="display: flex; justify-content: space-between; margin-bottom: 4px;">
                            <span style="color: #fff; font-weight: 500;">Secondary School (SSC)</span>
                            <span style="color: #d4af37; font-size: 11px;">2008</span>
                        </div>
                        <div style="color: #a0a0a0; font-size: 12px;">Fulgazi Pilot High School</div>
                    </div>
                </div>
            </main>
        </div>

        <footer class="footer">
            <p class="footer-text">REFERENCES AVAILABLE UPON REQUEST</p>
        </footer>
    </div>
</body>
</html>
