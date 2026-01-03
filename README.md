<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&family=JetBrains+Mono:wght@500&display=swap');
        
        body {
            margin: 0;
            padding: 0;
            overflow: hidden;
            background-color: #0d1117;
            font-family: 'Inter', sans-serif;
        }

        .grid-pattern {
            background-image: radial-gradient(#30363d 1px, transparent 1px);
            background-size: 40px 40px;
            animation: grid-pulse 8s ease-in-out infinite;
        }

        @keyframes grid-pulse {
            0%, 100% { opacity: 0.3; transform: scale(1); }
            50% { opacity: 0.5; transform: scale(1.02); }
        }

        .scanline {
            width: 100%;
            height: 100px;
            z-index: 5;
            background: linear-gradient(to bottom, transparent, rgba(88, 166, 255, 0.05), transparent);
            position: absolute;
            animation: scan 4s linear infinite;
        }

        @keyframes scan {
            from { transform: translateY(-100%); }
            to { transform: translateY(320px); }
        }

        .gradient-text {
            background: linear-gradient(90deg, #58a6ff, #bc8cff, #58a6ff);
            background-size: 200% auto;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: shimmer 5s linear infinite;
        }

        @keyframes shimmer {
            to { background-position: 200% center; }
        }

        .floating-path {
            stroke-dasharray: 1000;
            stroke-dashoffset: 1000;
            animation: draw 10s linear infinite forwards;
        }

        @keyframes draw {
            0% { stroke-dashoffset: 1000; opacity: 0; }
            20% { opacity: 0.4; }
            80% { opacity: 0.4; }
            100% { stroke-dashoffset: 0; opacity: 0; }
        }

        .badge {
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.75rem;
            padding: 4px 10px;
            border-radius: 4px;
            background: #21262d;
            border: 1px solid #30363d;
            color: #8b949e;
            transition: all 0.3s ease;
        }

        .badge:hover {
            border-color: #58a6ff;
            color: #f0f6fc;
            transform: translateY(-2px);
        }

        .pillar-line {
            height: 1px;
            background: linear-gradient(90deg, transparent, #30363d, transparent);
            width: 100%;
        }
    </style>
</head>
<body>
    <div id="banner-container" class="relative w-full h-[320px] flex items-center justify-center overflow-hidden bg-[#0d1117]">
        <!-- Animated Background Layer -->
        <div class="absolute inset-0 grid-pattern"></div>
        <div class="scanline"></div>
        
        <!-- Abstract Architectural Lines with Dash Animation -->
        <svg class="absolute inset-0 w-full h-full" preserveAspectRatio="none">
            <path class="floating-path" d="M0 80 Q 250 20 500 120 T 1000 80 T 1500 120" stroke="#58a6ff" fill="transparent" stroke-width="0.5" />
            <path class="floating-path" style="animation-delay: -5s" d="M0 240 Q 350 300 700 180 T 1400 240" stroke="#bc8cff" fill="transparent" stroke-width="0.5" />
        </svg>

        <!-- Main Content -->
        <div class="relative z-10 w-full max-w-4xl px-8 flex flex-col items-center text-center">
            <h1 class="text-4xl md:text-5xl font-extrabold text-white mb-2 tracking-tight">
                Sushanto <span class="gradient-text">Kumar</span>
            </h1>
            
            <p class="text-lg md:text-xl text-gray-400 font-medium mb-6 uppercase tracking-[0.2em] opacity-90">
                Full-Stack Engineer & Architectural Consultant
            </p>

            <!-- Tech Stack Pills -->
            <div class="flex flex-wrap justify-center gap-3 mb-8">
                <span class="badge">TypeScript</span>
                <span class="badge">React</span>
                <span class="badge">Node.js</span>
                <span class="badge">Next.js</span>
                <span class="badge">Prisma</span>
                <span class="badge">MongoDB</span>
                <span class="badge">Express</span>
            </div>

            <!-- Focus Pillars -->
            <div class="w-full">
                <div class="pillar-line mb-6"></div>
                <div class="grid grid-cols-3 gap-8 w-full">
                    <div class="flex flex-col items-center group">
                        <span class="text-[#58a6ff] font-bold text-sm tracking-widest transition-opacity group-hover:opacity-80">STRATEGY</span>
                        <span class="text-[10px] text-gray-500 mt-1 uppercase">Scalable Architecture</span>
                    </div>
                    <div class="flex flex-col items-center border-x border-[#30363d] group">
                        <span class="text-[#bc8cff] font-bold text-sm tracking-widest transition-opacity group-hover:opacity-80">VELOCITY</span>
                        <span class="text-[10px] text-gray-500 mt-1 uppercase">Dev Productivity</span>
                    </div>
                    <div class="flex flex-col items-center group">
                        <span class="text-[#58a6ff] font-bold text-sm tracking-widest transition-opacity group-hover:opacity-80">INTEGRITY</span>
                        <span class="text-[10px] text-gray-500 mt-1 uppercase">Clean Code Design</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- System Status Decorative UI -->
        <div class="absolute top-4 left-4 flex gap-1.5">
            <div class="w-2.5 h-2.5 rounded-full bg-[#ff5f56]"></div>
            <div class="w-2.5 h-2.5 rounded-full bg-[#ffbd2e]"></div>
            <div class="w-2.5 h-2.5 rounded-full bg-[#27c93f]"></div>
        </div>
        
        <div class="absolute bottom-4 left-6 flex items-center gap-2">
            <div class="w-1.5 h-1.5 rounded-full bg-[#27c93f] animate-pulse"></div>
            <span class="font-mono text-[9px] text-gray-500 uppercase tracking-widest">System Operational</span>
        </div>

        <div class="absolute bottom-4 right-6 font-mono text-[9px] text-gray-600 uppercase tracking-widest">
            v2.1.0 // env: production
        </div>
    </div>

    <!-- Interface Control -->
    <div class="fixed bottom-4 left-1/2 -translate-x-1/2">
        <button onclick="window.print()" class="px-6 py-2 bg-[#21262d] border border-[#30363d] hover:border-[#58a6ff] text-gray-300 hover:text-white rounded-md text-xs font-bold transition-all uppercase tracking-widest">
            Export Frame
        </button>
    </div>
</body>
</html>


<div>
   <img src="https://komarev.com/ghpvc/?username=Sushanto171&label=Profile%20Views&color=0e75b6&style=flat-square" alt="Profile Views Counter"/>
   <br/>
   
  <img height="200" src="https://raw.githubusercontent.com/Sushanto171/Sushanto171/main/github_initial.png" />
<h1 align="center"> 
👋 Hi, I'm <strong>Sushanto Kumar</strong>
</h1>
  <p align="center" >🚀 Web Developer | 🌿 Botany Student | 🌟 Tech Enthusiast </p>
  <br/>
  <br/>
  <img src="https://github-profile-trophy.vercel.app/?username=Sushanto171&theme=onedark&no-frame=false&margin-w=10" alt="GitHub Trophies" />
</div>

---

### 📚 **About Me**  
I'm **Sushanto Kumar**, a passionate **web developer** and **Botany student** pursuing a **BSc in Botany**. Skilled in **React.js, Next.js, TypeScript, Node.js, TailwindCSS, Express.js, MongoDB, Postgres and Prisma**, I love building **user-friendly, efficient, and scalable web applications**.
<br/>

• 📌 **Currently, I'm exploring:** **Next.js** to enhance my full-stack development skills.  
• 📧 **Email:** [sushantokumar171@gmail.com](mailto:sushantokumar171@gmail.com)  
• 🔗 **Portfolio:** [Explore My Work](https://sushantokumar.vercel.app)  
• 📞 **Phone:** <a href="tel:+8801791407583">+8801791407583 (WhatsApp)</a>

---

### 🌐 **Connect With Me**
<p align="center">
  <a href="https://www.linkedin.com/in/sushantokumar" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-blue?style=for-the-badge&logo=linkedin" alt="LinkedIn"/>
  </a>
  <a href="https://x.com/sushanto171" target="_blank">
    <img src="https://img.shields.io/badge/Twitter-black?style=for-the-badge&logo=twitter" alt="Twitter"/>
  </a>
</p>

---

### 💻 I Code With  
<p align="center">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5" />
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript" />
  <img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="React" />
  <img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white" alt="Next.js" />
  <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white" alt="Node.js" />
  <img src="https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white" alt="Express.js" />
  <img src="https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB" />
  <img src="https://img.shields.io/badge/Mongoose-880000?style=for-the-badge&logo=mongoose&logoColor=white" alt="Mongoose" />
   <img src="https://img.shields.io/badge/Redux-764ABC?style=for-the-badge&logo=redux&logoColor=white" alt="Redux" />
   <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt ="TypeScript"/>
   <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
<img src="https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white" alt="Prisma"/>

</p>

---

### 🛠️ **I Use Tools**
<p align="center">
  <img src="https://img.shields.io/badge/VS%20Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white" alt="VS Code" />
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git" />
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
  <img src="https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white" alt="Postman" />
  <img src="https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white" alt="Figma" />
  <img src="https://img.shields.io/badge/Netlify-00C7B7?style=for-the-badge&logo=netlify&logoColor=white" alt="Netlify" />
  <img src="https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Vercel" />
   <img src="https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=white" alt="Firebase" />

</p>

---

### 📊 **GitHub Stats**
<div align="center">
  <table>
    <tr>
      <td>
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=Sushanto171&theme=radical" alt="GitHub Streak"/>
      </td>
      <td>
        <img src="https://github-readme-stats.vercel.app/api?username=Sushanto171&show_icons=true&theme=radical" alt="GitHub Stats"/>
      </td>
      <td>
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Sushanto171&layout=compact&theme=radical" alt="Top Languages"/>
      </td>
    </tr>
  </table>
</div>

---
### 📈 **Contribution Graph**
<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=Sushanto171&theme=react-dark" alt="Contribution Graph" />
</p>
---

✨ **"Every line of code brings an idea to life!"** 🚀
