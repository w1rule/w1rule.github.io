---
layout: cv
title: CV
---
<style>
  .cv-title {
    font-weight: 700;
    font-size: 2.5em;
    margin-bottom: 1em;
  }
  /* Make the main title prominent */
  h1 {
    font-weight: 700;
    font-size: 2em;
    margin-bottom: 0.5em;
  }
  p {
    font-size: .85em;
  }
  
  /* Section headers */
  .cv-section h2 {
    font-weight: 700;
    font-size: 1.5em;
    margin-bottom: 1em;
  }
  
  /* Company names */
  .cv-role h3 {
    font-weight: 700;
    font-size: 1.3em;
    margin-bottom: 0.3em;
  }
  
  /* Job titles and dates */
  .cv-meta {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    font-weight: 600;
    font-size: .9em;
    margin-bottom: 0.5em;
  }

  .cv-meta-unbold {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    font-size: .9em;
    margin-bottom: 0.5em;
  }

  /* Skills list */
  .cv-list li {
    margin-bottom: 0.5em;
    line-height: 1.6;
  }
</style>

<h2 class="cv-title" style="text-align: center;">Curriculum Vitæ</h2>
<p style="text-align: center;">
  <a href="/assets/files/cv.pdf">Full Version</a>
</p>

{% include contact.html %}

<hr class="cv-divider">

<section class="cv-section">
  <h2 style="text-align: center;">Skills and Interests:</h2>

  <ul class="cv-list">
    <li>Business Development/Analysis (Market research, cost analysis, risk evaluation).</li>
    <li>Networks (layers, cloud, protocols, domains) and data-intensive distributed systems (PySpark, DataFrames, Big Data).</li>
    <li>Python, C, SQL, R, Scheme, Bash scripting, version control (Git, Bitbucket), Jira / Agile.</li>
    <li>Relational database design (SQLite, MySQL).</li>
    <li>Hardware research, system comparison, and software evaluation.</li>
    <li>Application design (UX, user flows, user needs).</li>
  </ul>
</section>

<hr class="cv-divider">

<section class="cv-section">
  <h2 style="text-align: center;">Work Experience:</h2>

  <div class="cv-role">
    <h3>StingerTech.ca</h3>
    <div class="cv-meta">
    <span class="job-title">Web Developer</span>
    <span class="job-dates">June 2024 – Present</span>
    </div>
    <p>
      I worked on local data center production using <a href="https://www.truenas.com/">TrueNAS</a>. Web development using <a href="https://tailwindcss.com/">Tailwind CSS</a>, and many other focused IT related tasks.
    </p>
  </div>

  <div class="cv-role">
    <h3>Toronto-Dominion Bank</h3>
    <div class="cv-meta">
    <span class="job-title">Cloud / DevOps Engineer (Co-op)</span>
    <span class="job-dates">May 2023 – Dec 2023</span>
    </div>
    <p>
      I worked on data center automation (NX-OS server YAML template automation using
      <a href="https://jinja.palletsprojects.com/en/3.1.x/">Jinja2</a>),
      completed Implementing and Administering Cisco Solutions (CCNA) v2.0, and researched/documented TD's SilverPeak and Aruba/ClearPass Zero-Touch Provisioning branch office network solution. 
    </p>
  </div>

  <div class="cv-role">
    <h3>Toronto-Dominion Bank</h3>
    <div class="cv-meta">
    <span class="job-title">Business Systems Analyst (Co-op)</span>
    <span class="job-dates">Sep 2022 – Dec 2022</span>
    </div>
    <p>
      I supported TD's <a href="https://www.ncino.com/">nCino</a> implementation by writing tests
      and standards. I also assisted in refining and validating legacy variables for migration
      to <a href="https://www.salesforce.com/ca/">Salesforce</a>.
    </p>
  </div>

  <div class="cv-role">
    <h3>ZeMaas</h3>
    <div class="cv-meta">
    <span class="job-title">QA Analyst (Co-op)</span>
    <span class="job-dates">Jan 2022 – Apr 2022</span>
    </div>
    <p>
      I contributed to documentation, test and requirement writing, application design,
      market research, cost analysis, and UX improvements.
    </p>
  </div>

  <div class="cv-role">
    <h3>Toronto Transit Commission</h3>
    <div class="cv-meta">
    <span class="job-title">IT Technical Specialist (Co-op)</span>
    <span class="job-dates">May 2021 – Aug 2021</span>
    </div>
    <p>
      I maintained equipment failure databases and managed PC/server hardware,
      software, applications, and peripheral devices.
    </p>
  </div>
</section>

<hr class="cv-divider">

<section class="cv-section">
  <h2 style="text-align: center;">Education:</h2>

  <div class="cv-role">
    <h3>University of Waterloo</h3>
    <div class="cv-meta-unbold">
    <span class="job-title">BMath (Co-op), Minor in Computing </span>
    <span class="job-dates">2019 – 2024</span>
    </div>
  </div>

  <div class="cv-role">
    <h3>TCPHS</h3>
    <div class="cv-meta-unbold">
    <span class="job-title">OSSD & IB Diploma </span>
    <span class="job-dates">2015 – 2019</span>
  </div>

<hr class="cv-divider">

<section class="cv-section">
  <h2 style="text-align: center;">Other:</h2>
  <p>
    Media production (video and photo editing using Premiere, Photoshop, XD).
    3rd Dan Black Belt in Taekwondo. Former piano player (RCMP Level 10).
  </p>
</section>
