<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rania Jrad - Profile</title>
    <style>
        /* ====== ANIMATIONS ====== */
        @keyframes spin { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
        @keyframes float { 0%,100% { transform: translateY(0); } 50% { transform: translateY(-12px); } }
        @keyframes pulse { 0%,100% { transform: scale(1); } 50% { transform: scale(1.06); } }
        @keyframes gradientShift { 0% { background-position: 0% 50%; } 50% { background-position: 100% 50%; } 100% { background-position: 0% 50%; } }
        @keyframes glow { 0%,100% { box-shadow: 0 0 10px rgba(168,85,247,.3); } 50% { box-shadow: 0 0 30px rgba(168,85,247,.7), 0 0 60px rgba(124,58,237,.3); } }
        @keyframes textPulse { 0%,100% { opacity: 1; transform: scale(1); } 50% { opacity: .75; transform: scale(.98); } }
        @keyframes colorShift { 0% { color: #6a0dad; } 50% { color: #a855f7; } 100% { color: #6a0dad; } }
        @keyframes borderGlow { 0%,100% { border-color: rgba(138,43,226,.3); } 50% { border-color: rgba(138,43,226,.8); } }
        @keyframes shimmer {
            0% { background-position: -500px 0; }
            100% { background-position: 500px 0; }
        }
        @keyframes tilt {
            0%,100% { transform: rotate(0deg); }
            50% { transform: rotate(1deg); }
        }
        @keyframes wave {
            0% { transform: translateX(0); }
            100% { transform: translateX(-100%); }
        }
        @keyframes bgMove {
            0% { background-position: 0% 50%; }
            100% { background-position: 200% 50%; }
        }

        /* ====== PAGE BACKGROUND ====== */
        body {
            background: linear-gradient(135deg, #f0e6ff, #e0d0ff, #f5f0ff, #e8ddff);
            background-size: 300% 300%;
            animation: bgMove 10s ease infinite;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', sans-serif;
        }

        /* ====== PROFILE CIRCLE ====== */
        .profile-circle {
            position: relative;
            width: 340px;
            height: 340px;
            margin: 30px auto;
            animation: float 4s ease-in-out infinite;
            cursor: pointer;
        }
        .rotating-border {
            position: absolute;
            top: -15px;
            left: -15px;
            width: 370px;
            height: 370px;
            border: 3px dashed rgba(138,43,226,.35);
            border-radius: 50%;
            animation: spin 14s linear infinite;
            z-index: 0;
        }
        .top-semi {
            position: absolute;
            top: 0;
            left: 0;
            width: 320px;
            height: 155px;
            border: 9px solid #1a1a1a;
            border-bottom: none;
            border-radius: 320px 320px 0 0;
            background: linear-gradient(135deg, #a855f7, #7c3aed, #6b21a8, #a855f7);
            background-size: 300% 300%;
            animation: gradientShift 5s ease infinite;
            box-shadow: 0 -10px 30px rgba(168,85,247,.4);
            z-index: 1;
        }
        .bottom-semi {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 320px;
            height: 155px;
            border: 9px solid #1a1a1a;
            border-top: none;
            border-radius: 0 0 320px 320px;
            background: linear-gradient(135deg, #6b21a8, #4c1d95, #3b0764, #6b21a8);
            background-size: 300% 300%;
            animation: gradientShift 5s ease infinite .5s;
            box-shadow: 0 10px 30px rgba(107,33,168,.4);
            z-index: 1;
        }
        .center-ring {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%,-50%);
            width: 110px;
            height: 110px;
            border-radius: 50%;
            border: 8px solid #fff;
            background: rgba(255,255,255,.85);
            box-shadow: 0 0 20px rgba(0,0,0,.1), 0 0 40px rgba(168,85,247,.15);
            z-index: 5;
            animation: pulse 2s ease-in-out infinite;
        }
        .center-inner {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%,-50%);
            width: 62px;
            height: 62px;
            border-radius: 50%;
            background: radial-gradient(circle, #c084fc, #a855f7, #6b21a8);
            animation: glow 2s ease-in-out infinite;
            z-index: 6;
        }
        .profile-text {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%,-50%);
            z-index: 10;
            background: rgba(255,255,255,.97);
            padding: 7px 18px;
            border-radius: 25px;
            font-family: 'Segoe UI', Tahoma, sans-serif;
            font-size: 13px;
            font-weight: 700;
            color: #2d2d2d;
            white-space: nowrap;
            box-shadow: 0 4px 20px rgba(0,0,0,.12);
            display: flex;
            align-items: center;
            gap: 6px;
            animation: textPulse 2s ease-in-out infinite;
            border: 2px solid #f0e6ff;
        }
        .profile-text .arrow {
            color: #7c3aed;
            font-size: 12px;
            display: inline-block;
            animation: spin 3s linear infinite;
            transform-origin: center;
        }

        /* ====== TITLE SHIMMER ====== */
        .shimmer-title {
            background: linear-gradient(90deg, #6a0dad, #a855f7, #7c3aed, #6a0dad);
            background-size: 200% auto;
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: shimmer 3s linear infinite;
        }

        /* ====== TYPEWRITER ====== */
        #typewriter {
            display: inline-block;
            border-right: 2px solid #6a0dad;
            padding-right: 5px;
            animation: blinkCaret .8s step-end infinite;
        }
        @keyframes blinkCaret { 50% { border-color: transparent; } }

        /* ====== TABLE HOVER ====== */
        .tech-table td {
            transition: all .3s ease;
            border-radius: 10px;
            padding: 12px;
        }
        .tech-table td:hover {
            background: rgba(138,43,226,.08);
            transform: scale(1.02);
            box-shadow: 0 4px 15px rgba(138,43,226,.1);
        }

        /* ====== BADGES ====== */
        .badge-item {
            display: inline-block;
            transition: all .3s ease;
            animation: float 3s ease-in-out infinite;
        }
        .badge-item:hover {
            transform: scale(1.1) rotate(3deg);
        }

        /* ====== PROJECT CARDS (3D TILT) ====== */
        .project-card {
            transition: all .3s ease;
            border-radius: 15px;
            padding: 15px;
            margin: 10px;
            border: 2px solid transparent;
            background: linear-gradient(white, white) padding-box,
                linear-gradient(135deg, #a855f7, #6b21a8) border-box;
            animation: borderGlow 3s ease-in-out infinite;
            transform-style: preserve-3d;
        }
        .project-card:hover {
            transform: perspective(600px) rotateX(5deg) rotateY(-5deg) translateY(-6px);
            box-shadow: 0 15px 40px rgba(138,43,226,.25);
        }

        /* ====== WAVE FOOTER (extra animation) ====== */
        .wave-container {
            position: relative;
            height: 100px;
            width: 100%;
            overflow: hidden;
            margin-top: 30px;
        }
        .wave {
            position: absolute;
            bottom: -20px;
            left: 0;
            width: 200%;
            height: 100px;
            background: url('data:image/svg+xml;utf8,<svg viewBox="0 0 1200 120" xmlns="http://www.w3.org/2000/svg"><path d="M0,60 C150,110 350,10 600,60 C850,110 1050,10 1200,60 L1200,120 L0,120 Z" fill="%23a855f7" opacity="0.3"/></svg>') repeat-x;
            animation: wave 8s linear infinite;
        }

        /* ====== RESPONSIVE ====== */
        @media(max-width: 700px) {
            .profile-circle, .top-semi, .bottom-semi { transform: scale(0.8); }
        }
    </style>
</head>
<body>

    <!-- ====== TITLE ====== -->
    <h1 align="center" class="shimmer-title" style="font-family:'Segoe UI',sans-serif; font-size:40px; margin-top:20px;">
        Hey, I'm Rania Jrad 👋
    </h1>

    <p align="center" style="font-family:'Segoe UI',sans-serif; font-size:18px; color:#555;">
        <em id="typewriter"></em>
    </p>

    <!-- ====== ANIMATED PROFILE CIRCLE ====== -->
    <div align="center">
        <a href="https://github.com/raniajrad" style="text-decoration:none;">
            <div class="profile-circle">
                <div class="rotating-border"></div>
                <div class="top-semi"></div>
                <div class="bottom-semi"></div>
                <div class="center-ring"></div>
                <div class="center-inner"></div>
                <div class="profile-text">
                    <span class="arrow">▶</span> Open my profile
                </div>
            </div>
        </a>
    </div>

    <!-- ====== PROFILE VIEWS ====== -->
    <p align="center">
        <img src="https://komarev.com/ghpvc/?username=raniajrad&color=8a2be2" alt="Profile views" />
    </p>

    <!-- ====== GITHUB TROPHIES ====== -->
    <h2 align="center" style="color:#8a2be2; font-family:'Segoe UI',sans-serif;">🏆 GitHub Trophies</h2>
    <p align="center">
        <img src="https://github-profile-trophy.vercel.app/?username=raniajrad" alt="GitHub Trophies" />
    </p>

    <!-- ====== TECHNOLOGIES & TOOLS ====== -->
    <h2 align="center" style="color:#8a2be2; font-family:'Segoe UI',sans-serif;">🛠️ Technologies & Tools</h2>

    <table align="center" class="tech-table" border="0" cellpadding="8" cellspacing="8">
        <tr align="center">
            <th style="color:#6a0dad; font-size:14px;">Programming Languages</th>
            <th style="color:#6a0dad; font-size:14px;">Back-end</th>
            <th style="color:#6a0dad; font-size:14px;">Front-end</th>
            <th style="color:#6a0dad; font-size:14px;">Database</th>
        </tr>
        <tr align="center">
            <td>
                <img src="https://skillicons.dev/icons?i=java" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(5deg)'" onmouseout="this.style.transform='scale(1)'" />
                <img src="https://skillicons.dev/icons?i=js" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(5deg)'" onmouseout="this.style.transform='scale(1)'" />
            </td>
            <td>
                <img src="https://skillicons.dev/icons?i=php" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(-5deg)'" onmouseout="this.style.transform='scale(1)'" />
                <img src="https://skillicons.dev/icons?i=laravel" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(5deg)'" onmouseout="this.style.transform='scale(1)'" />
            </td>
            <td>
                <img src="https://skillicons.dev/icons?i=html" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(5deg)'" onmouseout="this.style.transform='scale(1)'" />
                <img src="https://skillicons.dev/icons?i=css" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(-5deg)'" onmouseout="this.style.transform='scale(1)'" />
                <img src="https://skillicons.dev/icons?i=bootstrap" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(5deg)'" onmouseout="this.style.transform='scale(1)'" />
                <img src="https://skillicons.dev/icons?i=tailwind" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(-5deg)'" onmouseout="this.style.transform='scale(1)'" />
                <img src="https://skillicons.dev/icons?i=flutter" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(5deg)'" onmouseout="this.style.transform='scale(1)'" />
            </td>
            <td>
                <img src="https://skillicons.dev/icons?i=mysql" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(5deg)'" onmouseout="this.style.transform='scale(1)'" />
                <img src="https://skillicons.dev/icons?i=mongodb" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(-5deg)'" onmouseout="this.style.transform='scale(1)'" />
                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/oracle/oracle-original.svg" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(5deg)'" onmouseout="this.style.transform='scale(1)'" />
            </td>
        </tr>
        <tr align="center">
            <th style="color:#6a0dad; font-size:14px;">Systems & Deployment</th>
            <th style="color:#6a0dad; font-size:14px;">Tools</th>
            <th style="color:#6a0dad; font-size:14px;">Operating Systems</th>
            <th style="color:#6a0dad; font-size:14px;">UI/UX</th>
        </tr>
        <tr align="center">
            <td>
                <img src="https://skillicons.dev/icons?i=docker" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(5deg)'" onmouseout="this.style.transform='scale(1)'" />
            </td>
            <td>
                <img src="https://skillicons.dev/icons?i=git" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(5deg)'" onmouseout="this.style.transform='scale(1)'" />
                <img src="https://skillicons.dev/icons?i=vscode" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(-5deg)'" onmouseout="this.style.transform='scale(1)'" />
                <img src="https://skillicons.dev/icons?i=androidstudio" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(5deg)'" onmouseout="this.style.transform='scale(1)'" />
                <img src="https://skillicons.dev/icons?i=eclipse" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(-5deg)'" onmouseout="this.style.transform='scale(1)'" />
            </td>
            <td>
                <img src="https://skillicons.dev/icons?i=windows" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(5deg)'" onmouseout="this.style.transform='scale(1)'" />
            </td>
            <td>
                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/figma/figma-original.svg" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(5deg)'" onmouseout="this.style.transform='scale(1)'" />
                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/canva/canva-original.svg" width="45" style="transition:transform .3s;" onmouseover="this.style.transform='scale(1.2) rotate(-5deg)'" onmouseout="this.style.transform='scale(1)'" />
            </td>
        </tr>
    </table>

    <!-- ====== BADGES ====== -->
    <h2 align="center" style="color:#8a2be2; font-family:'Segoe UI',sans-serif;">🎓 Badges</h2>
    <p align="center">
        <a href="https://www.credly.com/badges/b9693b72-25a6-453e-894f-285eb2fb601c" class="badge-item">
            <img src="https://images.credly.com/size/340x340/images/1d37e2c9-e63d-4e64-b758-071509f9469d/image.png" width="120" style="border-radius:10px; box-shadow:0 5px 15px rgba(0,0,0,.2);" />
        </a>
        <a href="https://learn.microsoft.com/fr-fr/users/raniajrad-0198/" class="badge-item" style="animation-delay:.5s;">
            <img src="https://img.shields.io/badge/Microsoft_Learn-2F2F2F?style=for-the-badge&logo=microsoft&logoColor=white" alt="Microsoft Learn" />
        </a>
    </p>

    <!-- ====== GITHUB STATS ====== -->
    <h2 align="center" style="color:#8a2be2; font-family:'Segoe UI',sans-serif;">📈 GitHub Stats 📊</h2>
    <p align="center">
        <img src="https://github-readme-stats.vercel.app/api?username=raniajrad&show_icons=true&theme=dark" alt="Rania's GitHub Stats" style="border-radius:15px; box-shadow:0 5px 20px rgba(0,0,0,.2);" />
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=raniajrad&theme=dark" alt="GitHub Streak" style="border-radius:15px; box-shadow:0 5px 20px rgba(0,0,0,.2);" />
    </p>

    <!-- ====== ABOUT ME ====== -->
    <h2 align="center" style="color:#8a2be2; font-family:'Segoe UI',sans-serif;">🧠 About Me</h2>
    <p align="center" style="max-width:800px; margin:0 auto; font-family:'Segoe UI',sans-serif; color:#333; font-size:15px; line-height:1.8;">
        👩‍💻<strong>Junior Full Stack Developer diplômée en Technologie de l’Informatique, spécialité Développement des Systèmes d’Information.
        Passionnée par le développement web et mobile, avec des compétences en Flutter, Java et Laravel.
        À la recherche d’opportunités pour développer mes compétences et contribuer à des projets réels.</strong>
        <br><br>
        🎯 My goal is to <strong>design elegant and efficient digital solutions</strong> that <strong>make everyday life easier</strong>.
    </p>

    <!-- ====== CONNECT ====== -->
    <h2 align="center" style="color:#8a2be2; font-family:'Segoe UI',sans-serif;">🔗 Let's Work Together! 🤝</h2>
    <p align="center">
        <a href="https://www.linkedin.com/in/votre-profil-linkedin/" class="badge-item">
            <img src="https://img.shields.io/badge/LINKEDIN-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
        </a>
        <a href="mailto:rania.jrad.07@gmail.com" class="badge-item" style="animation-delay:.5s;">
            <img src="https://img.shields.io/badge/GMAIL-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail" />
        </a>
    </p>

    <!-- ====== PROJECTS ====== -->
    <h2 align="center" style="color:#8a2be2; font-family:'Segoe UI',sans-serif;">📂 My Projects</h2>
    <div align="center" style="display:flex; flex-wrap:wrap; justify-content:center; gap:20px; max-width:900px; margin:0 auto;">
        <div class="project-card" style="flex:1; min-width:250px; text-align:center;">
            <h3>👗 Clothing Store</h3>
            <p>An <strong>e-commerce application</strong> for clothing sales, developed with <strong>Laravel</strong>.</p>
            <a href="https://github.com/raniajrad/vente-photo" style="color:#7c3aed; text-decoration:none; font-weight:600;">👉 View Project</a>
        </div>
        <div class="project-card" style="flex:1; min-width:250px; text-align:center;">
            <h3>🏡 Local Platform</h3>
            <p>A <strong>local service platform</strong> connecting clients, providers, and admins for various digital services.</p>
            <a href="https://github.com/raniajrad/platforme-locale" style="color:#7c3aed; text-decoration:none; font-weight:600;">👉 View Project</a>
        </div>
        <div class="project-card" style="flex:1; min-width:250px; text-align:center;">
            <h3>📱 JS2024</h3>
            <p>A <strong>front-end training project</strong> built with <strong>HTML/CSS/JS</strong>.</p>
            <a href="https://github.com/raniajrad/js2024" style="color:#7c3aed; text-decoration:none; font-weight:600;">👉 View Project</a>
        </div>
    </div>

    <!-- ====== WAVE FOOTER ====== -->
    <div class="wave-container">
        <div class="wave"></div>
    </div>

    <!-- ====== FOOTER ====== -->
    <p align="center" style="font-family:'Segoe UI',sans-serif; color:#888; font-size:13px; margin-top:10px;">
        Made with ❤️ by Rania Jrad
    </p>

    <!-- ====== TYPEWRITER JS ====== -->
    <script>
        const phrases = [
            "Junior Full Stack Developer | Flutter | Java | Laravel",
            "Passionate about crafting digital experiences",
            "Open to new opportunities"
        ];
        let phraseIndex = 0, charIndex = 0, deleting = false;
        const typewriter = document.getElementById("typewriter");

        function type() {
            const current = phrases[phraseIndex];
            if (!deleting) {
                typewriter.textContent = current.substring(0, charIndex+1);
                charIndex++;
                if (charIndex === current.length) {
                    deleting = true;
                    setTimeout(type, 2000);
                    return;
                }
                setTimeout(type, 70);
            } else {
                typewriter.textContent = current.substring(0, charIndex-1);
                charIndex--;
                if (charIndex === 0) {
                    deleting = false;
                    phraseIndex = (phraseIndex + 1) % phrases.length;
                }
                setTimeout(type, 40);
            }
        }
        type();
    </script>
</body>
</html>
