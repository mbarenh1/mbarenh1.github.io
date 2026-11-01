<!-- ==========================================================================
     prompts I asked gemini in order to build the website: 
    make a personal website for me with index.md. I want a dark gradient background, a headshot, as well as summaries of the projects I've worked on and what my hobbies are. Use my uploaded resume as a guide. Write an explanation for each chunk of code for how it functions.
     why isnt it including my uploaded headshot that is labeled headshot.jpg?
     why does it say "email" but then not do anything when you click on email?
     how do I add a link to this to connect to the Pilpel website at Weizmann:
     ========================================================================== -->

<h1>Meira Barenholtz | Computational & Molecular Biology</h1>


<!-- ==========================================================================
     SECTION 1: Global Theme Styles & Dark Gradient Background
     Explanation:
     Sets the visual hierarchy, color tokens, responsive layout, glassmorphic
     cards, custom badges, and interactive hover transitions.
     ========================================================================== -->
<style>
  :root {
    --bg-primary: #0a0d14;
    --bg-secondary: #131926;
    --bg-card: rgba(23, 32, 51, 0.7);
    --border-color: rgba(255, 255, 255, 0.08);
    --border-hover: rgba(56, 189, 248, 0.4);
    --accent-blue: #38bdf8;
    --accent-purple: #a855f7;
    --text-primary: #f8fafc;
    --text-secondary: #94a3b8;
    --text-muted: #64748b;
  }

  body {
    margin: 0;
    padding: 0;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    background: radial-gradient(circle at 15% 15%, #182238 0%, #0c101a 50%, #06080d 100%);
    background-attachment: fixed;
    color: var(--text-primary);
    line-height: 1.6;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 3rem 1.5rem;
  }

  /* Profile Card & Headshot */
  .profile-header {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    margin-bottom: 2rem;
    padding: 2.5rem 2rem;
    background: var(--bg-card);
    border: 1px solid var(--border-color);
    border-radius: 20px;
    backdrop-filter: blur(12px);
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.4);
  }

  .headshot-wrapper {
    position: relative;
    width: 160px;
    height: 160px;
    margin-bottom: 1.5rem;
    border-radius: 50%;
    padding: 4px;
    background: linear-gradient(135deg, var(--accent-blue), var(--accent-purple));
  }

  .headshot-img {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    object-fit: cover;
    background-color: #1e293b;
    display: block;
  }

  .affiliation-banner {
    width: 100%;
    box-sizing: border-box;
    background: rgba(56, 189, 248, 0.08);
    border: 1px solid rgba(56, 189, 248, 0.25);
    border-radius: 12px;
    padding: 0.85rem 1.25rem;
    margin: 1.25rem 0 0.5rem 0;
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-between;
    gap: 0.75rem;
    font-size: 0.92rem;
    text-align: left;
  }

  .badge-list {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    justify-content: center;
    margin-top: 1.25rem;
  }

  .badge {
    background: rgba(56, 189, 248, 0.12);
    color: var(--accent-blue);
    border: 1px solid rgba(56, 189, 248, 0.25);
    padding: 0.25rem 0.8rem;
    border-radius: 9999px;
    font-size: 0.82rem;
    font-weight: 500;
  }

  .badge-purple {
    background: rgba(168, 85, 247, 0.12);
    color: var(--accent-purple);
    border-color: rgba(168, 85, 247, 0.25);
  }

  /* Section Styling */
  .section-title {
    font-size: 1.55rem;
    font-weight: 700;
    margin: 3rem 0 1.25rem 0;
    display: flex;
    align-items: center;
    gap: 0.75rem;
    color: var(--text-primary);
  }

  .section-title::after {
    content: "";
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border-color), transparent);
  }

  /* Grid and Cards */
  .grid-layout {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }

  .card {
    background: var(--bg-card);
    border: 1px solid var(--border-color);
    border-radius: 16px;
    padding: 1.75rem;
    backdrop-filter: blur(8px);
    transition: transform 0.2s ease, border-color 0.2s ease, box-shadow 0.2s ease;
  }

  .card:hover {
    transform: translateY(-3px);
    border-color: var(--border-hover);
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.35);
  }

  .card-header {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-bottom: 0.75rem;
  }

  .card-title {
    font-size: 1.2rem;
    font-weight: 600;
    color: #ffffff;
    margin: 0;
  }

  .card-subtitle {
    font-size: 0.9rem;
    color: var(--accent-blue);
    font-weight: 500;
  }

  .card-date {
    font-size: 0.85rem;
    color: var(--text-muted);
  }

  .card-body {
    color: var(--text-secondary);
    font-size: 0.95rem;
    margin: 0;
  }

  .card-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.4rem;
    margin-top: 1rem;
  }

  .card-tag {
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.1);
    color: var(--text-secondary);
    font-size: 0.78rem;
    padding: 0.15rem 0.6rem;
    border-radius: 6px;
  }

  /* Social and Links */
  .social-links {
    display: flex;
    flex-wrap: wrap;
    gap: 0.9rem;
    align-items: center;
    justify-content: center;
    margin-top: 1.5rem;
  }

  .social-link {
    color: var(--text-secondary);
    text-decoration: none;
    font-size: 0.9rem;
    transition: color 0.2s;
  }

  .social-link:hover {
    color: var(--accent-blue);
  }

  .contact-pill {
    background: rgba(56, 189, 248, 0.15);
    color: var(--accent-blue);
    border: 1px solid rgba(56, 189, 248, 0.3);
    padding: 0.35rem 0.9rem;
    border-radius: 9999px;
    text-decoration: none;
    font-size: 0.88rem;
    font-weight: 500;
    transition: background 0.2s, border-color 0.2s;
  }

  .contact-pill:hover {
    background: rgba(56, 189, 248, 0.25);
    border-color: var(--accent-blue);
  }

  @media (min-width: 768px) {
    .grid-two-col {
      grid-template-columns: repeat(2, 1fr);
    }
  }
</style>

<div class="container">

<!-- ==========================================================================
     SECTION 2: Profile Header, Affiliation Banner & Contact
     ========================================================================== -->
<header class="profile-header">
  <div class="headshot-wrapper">
    <img src="{{ '/headshot.jpg' | relative_url }}" alt="Meira Barenholtz" class="headshot-img" />
  </div>

  <h1 style="margin: 0; font-size: 2.1rem; font-weight: 800; letter-spacing: -0.02em;">Meira Barenholtz</h1>
  <p style="color: var(--accent-blue); font-size: 1.05rem; margin: 0.4rem 0 0.8rem 0; font-weight: 500;">
    Computational & Molecular Biology Researcher
  </p>

  <p style="max-width: 680px; color: var(--text-secondary); margin: 0; font-size: 0.96rem;">
    M.Sc. student in Computational Biology at the Feinberg Graduate School, Weizmann Institute of Science. Graduated Summa Cum Laude with Highest Honors in Genetics from Rutgers University. Focused on combining molecular bench science with data-driven modeling to explore cellular adaptation, translation dynamics, and regulatory networks.
  </p>

  <!-- Current Lab Affiliation Banner -->
  <div class="affiliation-banner">
    <div>
      <span style="color: var(--accent-blue); font-weight: 600;">Current Affiliation:</span>
      <span style="color: var(--text-primary); margin-left: 0.3rem;">Pilpel Lab &bull; Department of Molecular Genetics</span>
    </div>
    <a href="https://longitude.weizmann.ac.il/" target="_blank" rel="noopener noreferrer" style="color: var(--accent-blue); text-decoration: none; font-weight: 500;">
      Lab Website &nearr;
    </a>
  </div>

  <div class="badge-list">
    <span class="badge">Weizmann Institute of Science</span>
    <span class="badge">Rutgers University '26 (4.0 GPA)</span>
    <span class="badge badge-purple">Summa Cum Laude</span>
    <span class="badge badge-purple">Phi Beta Kappa</span>
    <span class="badge">Paul Robeson Scholar</span>
    <span class="badge">Henry Rutgers Scholar</span>
  </div>

  <div class="social-links">
    <a 
      href="https://mail.google.com/mail/?view=cm&fs=1&to=mbarenh1@gmail.com" 
      target="_blank" 
      rel="noopener noreferrer" 
      class="contact-pill"
    >
      Email Me
    </a>
    <a 
      href="https://www.linkedin.com/in/meira-barenholtz-698b89346/" 
      target="_blank" 
      rel="noopener noreferrer" 
      class="social-link"
    >
      LinkedIn
    </a>
    <span style="color: var(--text-muted);">&bull;</span>
    <a 
      href="https://longitude.weizmann.ac.il/" 
      target="_blank" 
      rel="noopener noreferrer" 
      class="social-link"
    >
      Pilpel Lab
    </a>
    <span style="color: var(--text-muted);">&bull;</span>
    <a href="tel:053-951-7420" class="social-link">053-951-7420</a>
    <span style="color: var(--text-muted);">&bull;</span>
    <span class="social-link">Rehovot, Israel</span>
  </div>
</header>

<!-- ==========================================================================
     SECTION 3: Research Experience
     ========================================================================== -->
<h2 class="section-title">Research Experience</h2>

<div class="grid-layout">

  <!-- Weizmann / Pilpel Lab -->
  <article class="card">
    <div class="card-header">
      <div>
        <h3 class="card-title">Cellular Adaptation & Regulatory Dynamics</h3>
        <div class="card-subtitle">
          <a href="https://longitude.weizmann.ac.il/" target="_blank" rel="noopener noreferrer" style="color: var(--accent-blue); text-decoration: none;">
            Pilpel Lab &bull; Weizmann Institute of Science &nearr;
          </a>
        </div>
      </div>
      <span class="card-date">Fall 2026 – Present</span>
    </div>
    <p class="card-body">
      Investigating translation dynamics, evolutionary genomics, and cell-autonomous adaptation systems. Working within computational genomics frameworks to understand gene expression regulation, tRNA pool adjustments during cellular stress, and transcriptomic adaptation.
    </p>
    <div class="card-tags">
      <span class="card-tag">Computational Biology</span>
      <span class="card-tag">Genomics</span>
      <span class="card-tag">Translation Dynamics</span>
      <span class="card-tag">Cellular Adaptation</span>
      <span class="card-tag">R / Python</span>
    </div>
  </article>

  <!-- Rutgers Thesis / Blaser Lab -->
  <article class="card">
    <div class="card-header">
      <div>
        <h3 class="card-title">Microbial Lipids & Intestinal Epithelial Metabolism</h3>
        <div class="card-subtitle">Blaser Lab &bull; Center for Advanced Biotechnology and Medicine (CABM)</div>
      </div>
      <span class="card-date">Jan 2025 – Aug 2026</span>
    </div>
    <p class="card-body">
      Conducted senior honors thesis research investigating how gut microbial lipid metabolites modulate mitochondrial function and inflammatory signaling in gut epithelial cell models. Screened 30+ metabolic and immune response genes via RT-qPCR, synthesized cDNA, and maintained intestinal cell lines. Processed and analyzed 2,400+ experimental data points using GraphPad Prism and R to identify statistically significant metabolic shifts. Defended honors thesis in March 2026 and presented findings at the Rutgers Departmental Honors Day Symposium.
    </p>
    <div class="card-tags">
      <span class="card-tag">Senior Honors Thesis</span>
      <span class="card-tag">RT-qPCR</span>
      <span class="card-tag">cDNA Synthesis</span>
      <span class="card-tag">Cell Culture (HT29)</span>
      <span class="card-tag">Statistical Analysis</span>
      <span class="card-tag">GraphPad Prism</span>
      <span class="card-tag">R</span>
    </div>
  </article>

  <!-- Hadassah Hospital -->
  <article class="card">
    <div class="card-header">
      <div>
        <h3 class="card-title">Xenopus Developmental Modeling & Axis Formation</h3>
        <div class="card-subtitle">Hadassah Hospital &bull; Hebrew University of Jerusalem</div>
      </div>
      <span class="card-date">Jun 2025 – Aug 2025</span>
    </div>
    <p class="card-body">
      Investigated left-right body axis determination and cardiac developmental signaling in <em>Xenopus</em> embryonic models. Executed high-precision immunofluorescent antibody staining protocols, conducted binocular and confocal microscopy on 30+ tissue samples, and quantified morphological cell area changes in gastrocoel roof plate knockout specimens.
    </p>
    <div class="card-tags">
      <span class="card-tag">Xenopus Embryology</span>
      <span class="card-tag">Immunofluorescence</span>
      <span class="card-tag">Confocal Microscopy</span>
      <span class="card-tag">Morphometric Quantification</span>
    </div>
  </article>

</div>

<!-- ==========================================================================
     SECTION 4: Honors, Awards & Academic Milestones
     ========================================================================== -->
<h2 class="section-title">Honors & Academic Awards</h2>

<div class="card">
  <div style="display: grid; grid-template-columns: 1fr; gap: 1rem;">
    <div>
      <div style="display: flex; justify-content: space-between; flex-wrap: wrap;">
        <strong style="color: #ffffff;">Departmental Highest Honors in Genetics</strong>
        <span style="color: var(--text-muted); font-size: 0.85rem;">2026</span>
      </div>
      <p style="color: var(--text-secondary); margin: 0.2rem 0 0.8rem 0; font-size: 0.92rem;">
        Awarded by Rutgers University for senior thesis research defense and academic performance in Genetics.
      </p>
    </div>

    <div>
      <div style="display: flex; justify-content: space-between; flex-wrap: wrap;">
        <strong style="color: #ffffff;">The Howard C. Passmore Award for Distinguished Academic Achievement</strong>
        <span style="color: var(--text-muted); font-size: 0.85rem;">2026</span>
      </div>
      <p style="color: var(--text-secondary); margin: 0.2rem 0 0.8rem 0; font-size: 0.92rem;">
        Conferred to graduating seniors with outstanding scholarship, laboratory dedication, and research contributions in genetics.
      </p>
    </div>

    <div>
      <div style="display: flex; justify-content: space-between; flex-wrap: wrap;">
        <strong style="color: #ffffff;">Henry Rutgers Scholar & Paul Robeson Scholar Awards</strong>
        <span style="color: var(--text-muted); font-size: 0.85rem;">2026</span>
      </div>
      <p style="color: var(--text-secondary); margin: 0.2rem 0 0.8rem 0; font-size: 0.92rem;">
        University honors recognizing exceptional senior honors thesis work and sustained academic excellence within the SAS Honors Program.
      </p>
    </div>

    <div>
      <div style="display: flex; justify-content: space-between; flex-wrap: wrap;">
        <strong style="color: #ffffff;">Phi Beta Kappa Honor Society & Dean's Award for Academic Excellence</strong>
        <span style="color: var(--text-muted); font-size: 0.85rem;">2026</span>
      </div>
      <p style="color: var(--text-secondary); margin: 0.2rem 0 0 0; font-size: 0.92rem;">
        Elected to the Alpha Chapter of New Jersey for liberal arts and sciences scholarship; sustained 4.0 GPA across all undergraduate coursework.
      </p>
    </div>
  </div>
</div>

<!-- ==========================================================================
     SECTION 5: Leadership & STEM Instruction
     ========================================================================== -->
<h2 class="section-title">Leadership & Instruction</h2>

<div class="grid-layout grid-two-col">

  <article class="card">
    <div class="card-header">
      <div>
        <h3 class="card-title">STEM Recitation & Workshop Instruction</h3>
        <div class="card-subtitle">Rutgers Physics & Chemistry Depts.</div>
      </div>
      <span class="card-date">2024 – 2026</span>
    </div>
    <p class="card-body">
      Led active problem-solving recitations for General Physics I and provided supplemental instructional workshops for General Chemistry. Partnered with course professors to isolate student conceptual bottlenecks in kinematics, dynamics, and equilibrium, adapting pedagogical materials to strengthen intuitive mastery.
    </p>
    <div class="card-tags">
      <span class="card-tag">Physics Recitations</span>
      <span class="card-tag">Chemistry Pedagogy</span>
      <span class="card-tag">Problem-Solving Workshops</span>
    </div>
  </article>

  <article class="card">
    <div class="card-header">
      <div>
        <h3 class="card-title">Student Governance & Editorial Leadership</h3>
        <div class="card-subtitle">Campus Executive Board</div>
      </div>
      <span class="card-date">2024 – 2026</span>
    </div>
    <p class="card-body">
      Served as Executive Vice President following a term as Education Chair. Authored formal governance and election bylaws overseeing 400+ participants, founded a campus student publication reaching 300+ readers, and established mentorship networks pairing newer undergraduates with upperclass research mentors.
    </p>
    <div class="card-tags">
      <span class="card-tag">Governance & Bylaws</span>
      <span class="card-tag">Editorial Direction</span>
      <span class="card-tag">Undergraduate Mentorship</span>
    </div>
  </article>

</div>

<!-- ==========================================================================
     SECTION 6: Technical Competencies & Analytical Tooling
     ========================================================================== -->
<h2 class="section-title">Technical Competencies</h2>

<div class="card">
  <p style="margin: 0 0 0.5rem 0; font-weight: 600; color: #ffffff;">Wet-Lab Molecular Biology:</p>
  <div class="card-tags" style="margin-bottom: 1.25rem;">
    <span class="card-tag">RT-qPCR / qPCR</span>
    <span class="card-tag">RNA & DNA Extraction</span>
    <span class="card-tag">cDNA Synthesis</span>
    <span class="card-tag">Immunofluorescent Staining</span>
    <span class="card-tag">Confocal & Light Microscopy</span>
    <span class="card-tag">Mammalian Cell Culture</span>
    <span class="card-tag">Tissue Homogenization</span>
  </div>

  <p style="margin: 0 0 0.5rem 0; font-weight: 600; color: #ffffff;">Computational & Quantitative Analysis:</p>
  <div class="card-tags" style="margin-bottom: 1.25rem;">
    <span class="card-tag">Python</span>
    <span class="card-tag">R (tidyverse: dplyr, ggplot2, tidyr)</span>
    <span class="card-tag">scRNA-seq Methodologies</span>
    <span class="card-tag">GraphPad Prism</span>
    <span class="card-tag">Git / GitHub</span>
    <span class="card-tag">Statistical Hypothesis Testing</span>
    <span class="card-tag">Microsoft Excel (Advanced Data Integrity)</span>
  </div>

  <p style="margin: 0 0 0.5rem 0; font-weight: 600; color: #ffffff;">Core Coursework Foundations:</p>
  <div class="card-tags">
    <span class="card-tag">Advanced Genetics</span>
    <span class="card-tag">Cancer Biology</span>
    <span class="card-tag">General Physics I & II</span>
    <span class="card-tag">General Chemistry</span>
    <span class="card-tag">Calculus</span>
    <span class="card-tag">Introductory Computer Science</span>
  </div>
</div>

<!-- ==========================================================================
     SECTION: Goals for Coding Python with AI Course
     ========================================================================== -->
<h2 class="section-title">Course Goals: Coding Python with AI</h2>

<div class="card">
  <div class="card-header">
    <div>
      <h3 class="card-title">Building Core Programming Fluency with AI Assistance</h3>
      <div class="card-subtitle">Foundations & Learning Objectives</div>
    </div>
    <span class="card-date">Introductory Course</span>
  </div>
  <p class="card-body" style="margin-bottom: 1.25rem;">
    Coming from a wet-lab background, my goal in this course is to become genuinely comfortable writing and reading Python without getting stuck on early syntax hurdles. I want to learn how to use AI responsibly as a collaborative tutor—helping me debug, explain unfamiliar errors, and build clean coding habits from the ground up:
  </p>

  <div style="display: grid; grid-template-columns: 1fr; gap: 0.85rem;">
    <div style="background: rgba(255, 255, 255, 0.02); border: 1px solid var(--border-color); border-radius: 10px; padding: 0.9rem 1.1rem;">
      <strong style="color: var(--accent-blue); display: block; margin-bottom: 0.2rem;">
        1. Solidify Core Python Foundations
      </strong>
      <span style="color: var(--text-secondary); font-size: 0.91rem;">
        Get comfortable with basic syntax, control flow (loops, conditionals), custom functions, and standard data structures (lists, dictionaries) so I can write scripts independently.
      </span>
    </div>

    <div style="background: rgba(255, 255, 255, 0.02); border: 1px solid var(--border-color); border-radius: 10px; padding: 0.9rem 1.1rem;">
      <strong style="color: var(--accent-blue); display: block; margin-bottom: 0.2rem;">
        2. Effective Debugging with AI
      </strong>
      <span style="color: var(--text-secondary); font-size: 0.91rem;">
        Learn how to ask AI the right questions when code breaks, using it to explain stack traces and logic bugs rather than just copy-pasting answers without understanding the underlying error.
      </span>
    </div>

    <div style="background: rgba(255, 255, 255, 0.02); border: 1px solid var(--border-color); border-radius: 10px; padding: 0.9rem 1.1rem;">
      <strong style="color: var(--accent-blue); display: block; margin-bottom: 0.2rem;">
        3. Practical Data & File Handling
      </strong>
      <span style="color: var(--text-secondary); font-size: 0.91rem;">
        Practice opening, parsing, and cleaning simple CSV and text files to automate repetitive tasks that usually take hours in spreadsheets.
      </span>
    </div>

    <div style="background: rgba(255, 255, 255, 0.02); border: 1px solid var(--border-color); border-radius: 10px; padding: 0.9rem 1.1rem;">
      <strong style="color: var(--accent-blue); display: block; margin-bottom: 0.2rem;">
        4. Gaining Coding Confidence
      </strong>
      <span style="color: var(--text-secondary); font-size: 0.91rem;">
        Move past the intimidation of an empty terminal or script, building enough muscle memory to tackle small, real-world research problems step-by-step.
      </span>
    </div>
  </div>

  <div class="card-tags" style="margin-top: 1.25rem;">
    <span class="card-tag">Python Basics</span>
    <span class="card-tag">AI-Assisted Debugging</span>
    <span class="card-tag">File Processing</span>
    <span class="card-tag">Functions & Control Flow</span>
    <span class="card-tag">Problem Solving</span>
  </div>
</div>

<!-- ==========================================================================
     SECTION 7: Hobbies & Personal Pursuits
     ========================================================================== -->
<h2 class="section-title">Hobbies & Personal Pursuits</h2>

<div class="grid-layout grid-two-col">

  <article class="card">
    <div class="card-header">
      <h3 class="card-title">Textile Design & Screen Printing</h3>
    </div>
    <p class="card-body">
      Extensive background in hands-on textile arts, including manual screen printing, color separation, pattern construction, and craft studio direction. Directed community apparel runs designing and printing custom garments for over 1,200 individuals.
    </p>
  </article>

  <article class="card">
    <div class="card-header">
      <h3 class="card-title">Science Writing & Medical Narratives</h3>
    </div>
    <p class="card-body">
      Passionate about editorial writing that makes dense genetic concepts accessible. Beyond managing campus publications, I follow literature in gene editing, evolutionary biology, and historical perspectives in molecular medicine.
    </p>
  </article>

  <article class="card">
    <div class="card-header">
      <h3 class="card-title">Clinical Documentation & Scribing</h3>
    </div>
    <p class="card-body">
      Experience in medical scribing and physician shadowing. Interested in doctor-patient communication dynamics, precise clinical record-keeping, and the translation of bench discoveries into bedside practice.
    </p>
  </article>

  <article class="card">
    <div class="card-header">
      <h3 class="card-title">Visual Arts & Craft Studio Management</h3>
    </div>
    <p class="card-body">
      Practicing painting, mixed media, and manual printmaking. Experienced in managing studio workflows, material inventory, and facilitating collaborative community arts workshops.
    </p>
  </article>

</div>

<footer style="text-align: center; margin-top: 4rem; color: var(--text-muted); font-size: 0.85rem;">
  <p>&copy; Meira Barenholtz. Built with Markdown & CSS.</p>
</footer>

</div>
