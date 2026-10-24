<!-- make a personal website for me with index.md. I want a dark gradient background, a headshot, as well as summaries of the projects I've worked on and what my hobbies are. Use my uploaded resume as a guide. Write an explanation for each chunk of code for how it functions. -->

---
layout: default
title: Meira Barenholtz | Genetics Researcher & Educator
---

<!-- ==========================================================================
     SECTION 1: Global Theme Styles & Dark Gradient Background
     Explanation:
     This embedded <style> block sets up the visual identity of the website.
     It applies a smooth, deep dark radial and linear gradient background
     to the page body, defines high-contrast typography colors, sets a responsive
     container width, and provides clean card components with subtle borders
     and hover effects.
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
    margin-bottom: 3.5rem;
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

  .badge-list {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    justify-content: center;
    margin-top: 1rem;
  }

  .badge {
    background: rgba(56, 189, 248, 0.12);
    color: var(--accent-blue);
    border: 1px solid rgba(56, 189, 248, 0.25);
    padding: 0.25rem 0.8rem;
    border-radius: 9999px;
    font-size: 0.85rem;
    font-weight: 500;
  }

  /* Section Styling */
  .section-title {
    font-size: 1.6rem;
    font-weight: 700;
    margin: 2.5rem 0 1.25rem 0;
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

  /* Contact and Links */
  .social-links {
    display: flex;
    gap: 1.25rem;
    margin-top: 1.25rem;
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

  @media (min-width: 768px) {
    .grid-two-col {
      grid-template-columns: repeat(2, 1fr);
    }
  }
</style>

<div class="container">

<!-- ==========================================================================
     SECTION 2: Profile Header & Headshot
     Explanation:
     This section displays your identity, academic credentials (Rutgers 4.0 GPA,
     Summa Cum Laude), bio, and links. The <img> tag references "headshot.jpg"
     wrapped in a gradient border ring. Replace "assets/headshot.jpg" with your
     actual image file path or URL.
     ========================================================================== -->
<header class="profile-header">
  <div class="headshot-wrapper">
  <img 
    src="./headshot.jpg" 
    alt="Meira Barenholtz" 
    class="headshot-img"
  />
</div>
  <h1 style="margin: 0; font-size: 2rem; font-weight: 800; letter-spacing: -0.02em;">Meira Barenholtz</h1>
  <p style="color: var(--accent-blue); font-size: 1.05rem; margin: 0.4rem 0 1rem 0; font-weight: 500;">
    Genetics Researcher & Molecular Biology Specialist
  </p>
  <p style="max-width: 650px; color: var(--text-secondary); margin: 0; font-size: 0.98rem;">
    Graduating Senior in Genetics at Rutgers University (Summa Cum Laude, 4.0 GPA). Passionate about translational genetics, computational analysis, and biomedical research bridging bench science with clinical insights.
  </p>

  <div class="badge-list">
    <span class="badge">Rutgers University '26</span>
    <span class="badge">Summa Cum Laude (4.0 GPA)</span>
    <span class="badge">Paul Robeson Scholar</span>
    <span class="badge">Henry Rutgers Scholar</span>
  </div>

  <div class="social-links">
    <a href="mailto:mbarenh1@gmail.com" class="contact-pill">Email</a>
    <span style="color: var(--text-muted);">&bull;</span>
    <a href="tel:551-275-9663" class="social-link">053-951-7420</a>
    <span style="color: var(--text-muted);">&bull;</span>
    <span class="social-link">Rehovot, Israel</span>
  </div>
</header>

<!-- ==========================================================================
     SECTION 3: Research & Scientific Projects
     Explanation:
     This section showcases your primary wet-lab and translational projects
     from the Blaser Lab and Hadassah Hospital. Each card highlights the core
     scientific objective, quantitative milestones (e.g., 2,400+ data points,
     50+ genes screened), and relevant analytical methods used.
     ========================================================================== -->
<h2 class="section-title">Research Projects</h2>

<div class="grid-layout">
  
  <article class="card">
    <div class="card-header">
      <div>
        <h3 class="card-title">Type 1 Diabetes Pathogenesis & Gene Expression Profiling</h3>
        <div class="card-subtitle">Blaser Lab &bull; Center for Advanced Biotechnology and Medicine</div>
      </div>
      <span class="card-date">Jan 2025 – May 2026</span>
    </div>
    <p class="card-body">
      Conducted targeted literature reviews and experimental designs to evaluate the expression patterns of 50+ genes involved in the pathogenesis of Type 1 Diabetes. Processed and statistically evaluated over 2,400 data points to identify significant expression changes while maintaining a 99% data integrity threshold for laboratory records. Compiled comprehensive technical reports on protocols and findings for faculty review.
    </p>
    <div class="card-tags">
      <span class="card-tag">RT-qPCR</span>
      <span class="card-tag">Big Data Genetics</span>
      <span class="card-tag">GraphPad Prism</span>
      <span class="card-tag">Statistical Analysis</span>
      <span class="card-tag">RStudio</span>
    </div>
  </article>

  <article class="card">
    <div class="card-header">
      <div>
        <h3 class="card-title">Translational Xenopus Disease Modeling & Protein Expression</h3>
        <div class="card-subtitle">Hadassah Hospital &bull; Hebrew University of Jerusalem</div>
      </div>
      <span class="card-date">Jun 2025 – Aug 2025</span>
    </div>
    <p class="card-body">
      Investigated molecular disease mechanisms and localized protein expression using <em>Xenopus</em> developmental models. Executed high-precision immunofluorescent antibody staining protocols, performed binocular and confocal microscopy on 30+ experimental tissue samples, and conducted morphometric cell area quantifications to evaluate clinical correlates.
    </p>
    <div class="card-tags">
      <span class="card-tag">Immunofluorescence</span>
      <span class="card-tag">Microscopy</span>
      <span class="card-tag">Translational Research</span>
      <span class="card-tag">Cell Area Quantification</span>
    </div>
  </article>

</div>

<!-- ==========================================================================
     SECTION 4: Leadership, Mentorship & Scientific Communication
     Explanation:
     Presents your leadership and academic service, detailing the executive 
     governance at Rutgers Hillel, student mentorship initiatives, and STEM 
     instruction in physics and chemistry.
     ========================================================================== -->
<h2 class="section-title">Leadership & Teaching Initiatives</h2>

<div class="grid-layout grid-two-col">

  <article class="card">
    <div class="card-header">
      <div>
        <h3 class="card-title">STEM Peer Instruction & Pedagogy</h3>
        <div class="card-subtitle">Rutgers University Physics & Chemistry Depts.</div>
      </div>
      <span class="card-date">2024 – 2026</span>
    </div>
    <p class="card-body">
      Led recitations and problem-solving workshops for 20+ undergraduates in kinematics, chemical equilibrium, and thermodynamic dynamics. Collaborated closely with course professors to isolate learning bottlenecks and revise conceptual instruction.
    </p>
    <div class="card-tags">
      <span class="card-tag">Pedagogy</span>
      <span class="card-tag">Kinematics & Dynamics</span>
      <span class="card-tag">Peer Instruction</span>
    </div>
  </article>

  <article class="card">
    <div class="card-header">
      <div>
        <h3 class="card-title">Governance & Student Publishing</h3>
        <div class="card-subtitle">Rutgers Hillel Executive Board</div>
      </div>
      <span class="card-date">2024 – 2026</span>
    </div>
    <p class="card-body">
      Served as Executive Vice President; authored elections governance handbook overseeing 400+ voters. Founded and directed a monthly campus publication distributed to 300+ readers, and launched a faculty-student mentorship network.
    </p>
    <div class="card-tags">
      <span class="card-tag">Executive Leadership</span>
      <span class="card-tag">Publication Editor</span>
      <span class="card-tag">Mentorship Programs</span>
    </div>
  </article>

</div>

<!-- ==========================================================================
     SECTION 5: Hobbies & Personal Interests
     Explanation:
     This section rounds out your portfolio with personal hobbies that 
     complement your scientific career—such as textile crafts (referencing 
     your work directing large-scale garment production), medical writing/scribing,
     science communication, and community programming.
     ========================================================================== -->
<h2 class="section-title">Hobbies & Personal Pursuits</h2>

<div class="grid-layout grid-two-col">

  <article class="card">
    <div class="card-header">
      <h3 class="card-title">Textile Arts & Creative Production</h3>
    </div>
    <p class="card-body">
      Having served as Director of Arts & Crafts overseeing the design and production of over 1,200 custom garments, I spend free time exploring textile crafting, pattern construction, and mixed-media design.
    </p>
  </article>

  <article class="card">
    <div class="card-header">
      <h3 class="card-title">Science Writing & Publication</h3>
    </div>
    <p class="card-body">
      Passionate about distilling dense genetic phenomena into accessible narratives. Beyond editing student journals, I enjoy reading scientific history, medical memoirs, and following emergent literature in gene editing and biotechnology.
    </p>
  </article>

  <article class="card">
    <div class="card-header">
      <h3 class="card-title">Community Organizing & Mentorship</h3>
    </div>
    <p class="card-body">
      Active in organizing educational programming and bringing people together—whether facilitating peer mentorship spaces, running collaborative workshops, or organizing community discussions.
    </p>
  </article>

  <article class="card">
    <div class="card-header">
      <h3 class="card-title">Clinical Shadowing & Health Literacy</h3>
    </div>
    <p class="card-body">
      Drawn to understanding patient experiences and healthcare communication through clinical scribing, medical documentation study, and volunteering.
    </p>
  </article>

</div>

<!-- ==========================================================================
     SECTION 6: Technical Laboratory & Analytical Tooling
     Explanation:
     Displays a quick-reference grid of your lab techniques, cell line work, 
     and computational tools directly from your resume.
     ========================================================================== -->
<h2 class="section-title">Technical Competencies</h2>

<div class="card" style="margin-top: 1rem;">
  <p style="margin: 0 0 0.75rem 0; font-weight: 600; color: #fff;">Molecular & Bench Techniques:</p>
  <div class="card-tags" style="margin-bottom: 1.25rem;">
    <span class="card-tag">RNA/DNA Extraction</span>
    <span class="card-tag">cDNA Synthesis</span>
    <span class="card-tag">RT-qPCR / qPCR</span>
    <span class="card-tag">Immunofluorescent Staining</span>
    <span class="card-tag">Binocular & Light Microscopy</span>
    <span class="card-tag">HEK & HT29 Cell Culture</span>
    <span class="card-tag">Quadrant Streaking</span>
    <span class="card-tag">Gram & Endospore Staining</span>
  </div>

  <p style="margin: 0 0 0.75rem 0; font-weight: 600; color: #fff;">Computational & Analytical Software:</p>
  <div class="card-tags">
    <span class="card-tag">RStudio</span>
    <span class="card-tag">GraphPad Prism</span>
    <span class="card-tag">Microsoft Excel (Advanced Data Integrity)</span>
    <span class="card-tag">Medical Scribing & Documentation</span>
  </div>
</div>

<footer style="text-align: center; margin-top: 4rem; color: var(--text-muted); font-size: 0.85rem;">
  <p>&copy; Meira Barenholtz. Built with Markdown & CSS.</p>
</footer>

</div>
