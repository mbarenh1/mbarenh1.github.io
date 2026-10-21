<!--write the index.md code for me to create a personal website on github. I want a dark background, my headshot, and a section about my interests-->

---
Meira Tovah Barenholtz
---

<style>
  :root {
    --bg-color: #0f172a;
    --card-bg: #1e293b;
    --text-main: #e2e8f0;
    --text-muted: #94a3b8;
    --accent: #38bdf8;
    --border: #334155;
  }

  body {
    background-color: var(--bg-color);
    color: var(--text-main);
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 2rem 1rem;
  }

  .container {
    max-width: 780px;
    margin: 0 auto;
  }

  header {
    text-align: center;
    padding-bottom: 2rem;
    border-bottom: 1px solid var(--border);
    margin-bottom: 2rem;
  }

  .headshot {
    width: 160px;
    height: 160px;
    border-radius: 50%;
    object-fit: cover;
    border: 3px solid var(--accent);
    box-shadow: 0 4px 14px rgba(0, 0, 0, 0.4);
    margin-bottom: 1rem;
  }

  h1 {
    font-size: 2rem;
    margin: 0.5rem 0 0.25rem 0;
    color: #f8fafc;
  }

  .subtitle {
    color: var(--accent);
    font-size: 1.05rem;
    font-weight: 500;
    margin-bottom: 0.75rem;
  }

  .bio {
    color: var(--text-muted);
    max-width: 620px;
    margin: 0 auto;
    font-size: 0.98rem;
  }

  section {
    margin-bottom: 2.5rem;
  }

  h2 {
    color: #f8fafc;
    border-bottom: 2px solid var(--border);
    padding-bottom: 0.4rem;
    margin-bottom: 1rem;
    font-size: 1.35rem;
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 1rem;
  }

  .card {
    background: var(--card-bg);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 1.2rem;
  }

  .card h3 {
    margin-top: 0;
    color: var(--accent);
    font-size: 1.05rem;
  }

  .card ul {
    margin: 0;
    padding-left: 1.2rem;
    color: var(--text-main);
    font-size: 0.92rem;
  }

  .card li {
    margin-bottom: 0.35rem;
  }

  <footer>
  <p>© 2026 Meira Tovah Barenholtz • Hosted on GitHub Pages</p>
</footer>

</style>

<div class="container">

  <header>
    <img src="headshot.jpg" alt="Meira Tovah Barenholtz" class="headshot">
    <h1>Meira Tovah Barenholtz</h1>
    <div class="subtitle">M.Sc. Student in Computational Biology | Weizmann Institute of Science</div>
    <p class="bio">
      Working at the intersection of computational modeling, genomics, and cellular metabolism. 
      Background in genetics and molecular biology with a focus on quantitative data analysis and biological systems.
    </p>
  </header>

  <section>
    <h2>Interests & Focus Areas</h2>
    <div class="grid">
      <div class="card">
        <h3>Computational Biology & Genomics</h3>
        <ul>
          <li>Genomic data visualization & modeling</li>
          <li>Statistical genetics and sequence analysis</li>
          <li>Algorithm design in Python & R</li>
        </ul>
      </div>

      <div class="card">
        <h3>Molecular & Cellular Systems</h3>
        <ul>
          <li>Cellular metabolism and bioenergetics</li>
          <li>Host-microbe metabolic interactions</li>
          <li>Quantitative assay development</li>
        </ul>
      </div>

      <div class="card">
        <h3>Creative & Personal Pursuits</h3>
        <ul>
          <li>Visual arts, painting, and morphological analysis</li>
          <li>Espresso and Moka brewing methods</li>
          <li>Analog and digital portrait photography</li>
        </ul>
      </div>
    </div>
  </section>

  <section>
    <h2>Technical Toolkit</h2>
    <div class="card">
      <p style="margin: 0; font-size: 0.95rem;">
        <strong>Languages & Frameworks:</strong> Python, R (tidyverse, ggplot2), Git/GitHub, Markdown<br>
        <strong>Methods:</strong> Statistical Hypothesis Testing, Exploratory Data Analysis, Quantitative Real-Time PCR, Fluorescence Microscopy
      </p>
    </div>
  </section>

  <footer>
    <p>© 2026 Meira Tovah Barenholtz • Hosted on GitHub Pages</p>
  </footer>

</div>
