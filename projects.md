---
layout: cv
title: Projects
---

<style>
  /* Project sections */
  .project-section {
    margin-bottom: 3em;
  }
  
  .project-section h2 {
    font-weight: 700;
    font-size: 1.8em;
    margin-bottom: 0.5em;
    text-align: center;
  }
  
  .project-section h3 {
    font-weight: 600;
    font-size: 1.2em;
    margin-top: 1.5em;
    margin-bottom: 0.5em;
    text-transform: none;
  }
  
  /* Image placeholder */
  .project-image {
    width: 100%;
    max-width: 800px;

    background-color: #f0f0f0;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 1.5em auto;
    color: #999;
    font-style: italic;
  }
  
  /* Tech stack badges */
  .tech-stack {
    margin-top: 1em;
    padding: 1em;
    background-color: #f8f9fa;
    border-left: 4px solid #007bff;
  }
  
  .tech-stack strong {
    display: block;
    margin-bottom: 0.5em;
    color: #333;
  }
  
  /* Paragraphs */
  .project-section p {
    margin-bottom: 1em;
    line-height: 1.7;
  }
  
  /* Links */
  .project-section a {
    color: #007bff;
    text-decoration: none;
    border-bottom: 1px solid transparent;
    transition: border-bottom 0.2s;
  }
  
  .project-section a:hover {
    border-bottom: 1px solid #007bff;
  }
  
  /* Download button */
  .download-btn {
    display: inline-block;
    padding: 0.5em 1em;
    background-color: #5865F2;
    color: white !important;
    border-radius: 5px;
    text-decoration: none;
    margin: 1em 0;
    transition: background-color 0.3s;
  }
  
  .download-btn:hover {
    background-color: #4752C4;
    border-bottom: none;
  }
</style>

<h1 style="text-align: center;">Projects</h1>

{% include contact.html %}

<hr class="cv-divider">

<!-- TrueNAS Server Project -->
<section class="project-section">
  <h2>TrueNAS Server</h2>
  
  <div class="project-image">
  <img src="{{ site.baseurl }}/assets/images/truenas.png" alt="TrueNAS Dashboard" style="width: 100%; height: auto;">
    </div>
  
  <p>A repurposed Dell Optiplex server running <a href="https://www.truenas.com/truenas-scale/" target="_blank">TrueNAS Scale</a> with two 6TB Toshiba N300 drives in a redundant configuration. The system minimizes power consumption while maintaining remote availability through Wake-on-LAN, cron automation, and <a href="https://www.wireguard.com/" target="_blank">WireGuard VPN</a>.</p>
  
  <h3>The Challenge</h3>
  <p>I needed a solution for sharing large video files 1-2 times per month with remote users, while balancing drive longevity, power efficiency, and security. The server needed to be accessible from outside the home network without exposing the entire network to security risks.</p>
  
  <h3>Implementation</h3>
  <p>The drives were configured as Windows SMB shares, with the OS running on a dedicated SSD for fast boot times. Remote access was implemented using <a href="https://www.wireguard.com/" target="_blank">WireGuard</a>, an open-source VPN solution, with client configurations generated through the <a href="https://github.com/wg-easy/wg-easy" target="_blank">wg-easy</a> plugin for TrueNAS Scale.</p>
  
  <p>Strict routing rules ensure the VPN connection only accesses the NAS—no port forwarding or gateway routing to the home network. Users simply enable the VPN app and connect as if they were on the local network.</p>
  
  <p>I configured the BIOS and network interface for Wake-on-LAN using <a href="https://www.depicus.com/wake-on-lan/" target="_blank">Depicus</a> magic packets. A cron job automatically shuts down the system after 30 minutes of network inactivity, optimizing for HDD wear while maintaining availability when needed.</p>
  
  <div class="tech-stack">
    <strong>Tools & Technologies:</strong>
    <a href="https://www.truenas.com/truenas-scale/" target="_blank">TrueNAS SCALE</a> (Debian-based), systemd, cron, <a href="https://www.wireguard.com/" target="_blank">WireGuard</a>, Wake-on-LAN, BIOS configuration, Bash scripting
  </div>
</section>

<hr class="cv-divider">

<!-- Discord Bot Project -->
<section class="project-section">
  <h2>Discord Chatbot with Image Manipulator</h2>
  
  <a href="https://discord.com/oauth2/authorize?client_id=850845944698241075&permissions=2147534848&integration_type=0&scope=bot+applications.commands" class="download-btn" target="_blank">Add Bot to Your Server</a>
  
  <p><em>Usage: Post an image in your server and type /wojak</em></p>
  
  <div class="project-image">
  <img src="{{ site.baseurl }}/assets/images/wojak.png" alt="TrueNAS Dashboard" style="width: 100%; height: auto;">
    </div>
  
  <p>A <a href="https://discord.com/developers/docs/intro" target="_blank">Discord bot</a> that fetches the last image sent in a channel, uploads it to <a href="https://imgur.com/" target="_blank">Imgur</a>, and overlays it with a pointing Wojak meme using <a href="https://cloudinary.com/" target="_blank">Cloudinary</a>—all deployed on <a href="https://workers.cloudflare.com/" target="_blank">Cloudflare Workers</a> at zero cost. The bot also includes a simple calculator function.</p>
  
  <h3>Cloudflare Workers & Deployment</h3>
  <p>The bot's core logic runs on <a href="https://workers.cloudflare.com/" target="_blank">Cloudflare Workers</a>, a serverless platform that handles Discord interactions, Cloudinary transformations, and image processing. Deployment is managed through <a href="https://developers.cloudflare.com/workers/wrangler/" target="_blank">Wrangler</a>, Cloudflare's CLI tool, which builds and deploys the worker automatically.</p>
  
  <p>The setup and registration scripts use <a href="https://nodejs.org/" target="_blank">Node.js</a> to interact with the <a href="https://discord.com/developers/docs/intro" target="_blank">Discord API</a> and register slash commands. <a href="https://www.npmjs.com/" target="_blank">npm</a> manages project dependencies and tools.</p>
  
  <h3>Discord & Imgur API Integration</h3>
  <p>The bot registers slash commands and fetches messages through Discord's API. When a user posts an image, the bot uploads it to <a href="https://imgur.com/" target="_blank">Imgur</a> via their API, which provides a permanent URL and image dimensions (width and height) needed for processing.</p>
  
  <p>Imgur serves as an intermediary because <a href="https://cloudinary.com/" target="_blank">Cloudinary</a> doesn't recognize Discord's ephemeral media URLs. This permanent hosting enables dynamic transformations.</p>
  
  <h3>Cloudinary Image Processing</h3>
  <p><a href="https://cloudinary.com/" target="_blank">Cloudinary</a> handles the dynamic image transformations. After retrieving the Imgur URL, the bot passes it to Cloudinary where the pointing Wojak overlay is applied. The overlay scales dynamically based on the original image dimensions from Imgur's metadata, ensuring proper proportions regardless of the input image size.</p>
  
  <h3>Calculator Function</h3>
  <p>The bot includes a calculator feature that handles mathematical expressions. Since Cloudflare Workers disallow code generation from strings (like <code>eval()</code>) for security reasons, I built a custom parser and evaluator to safely process mathematical expressions.</p>
  
  <div class="tech-stack">
    <strong>Tools & Technologies:</strong>
    <a href="https://workers.cloudflare.com/" target="_blank">Cloudflare Workers</a>, <a href="https://developers.cloudflare.com/workers/wrangler/" target="_blank">Wrangler</a>, <a href="https://nodejs.org/" target="_blank">Node.js</a>, <a href="https://www.npmjs.com/" target="_blank">npm</a>, <a href="https://discord.com/developers/docs/intro" target="_blank">Discord API</a>, <a href="https://imgur.com/" target="_blank">Imgur API</a>, <a href="https://cloudinary.com/" target="_blank">Cloudinary API</a>
  </div>
</section>

<hr class="cv-divider">

<!-- Website Project -->
<section class="project-section">
  <h2>This Website</h2>
  
  <div class="project-image">
  <img src="{{ site.baseurl }}/assets/images/websiteo.png" alt="TrueNAS Dashboard" style="width: 100%; height: auto;">
    </div>
  
  <p>A personal portfolio website built with modern static site generation tools, hosted on <a href="https://pages.github.com/" target="_blank">GitHub Pages</a> with a custom domain from <a href="https://www.namecheap.com/" target="_blank">Namecheap</a>. The site showcases my professional experience, skills, and projects using <a href="https://jekyllrb.com/" target="_blank">Jekyll</a>, custom CSS, and automated deployment workflows.</p>
  
  <h3>Static Hosting with GitHub Pages</h3>
  <p>The site is hosted on <a href="https://pages.github.com/" target="_blank">GitHub Pages</a>, a free hosting platform for static websites. Updates are deployed automatically by pushing changes to the repository, making the development workflow seamless and efficient.</p>
  
  <h3>Custom Domain Configuration</h3>
  <p>I registered a custom domain through <a href="https://www.namecheap.com/" target="_blank">Namecheap</a> and configured the DNS settings to point to GitHub Pages using A records and CNAME entries. This gives the site a professional appearance while leveraging free hosting.</p>
  
  <h3>Jekyll Site Generation</h3>
  <p>The website is built with <a href="https://jekyllrb.com/" target="_blank">Jekyll</a>, a static site generator written in Ruby. Jekyll converts <a href="https://www.markdownguide.org/" target="_blank">Markdown</a> files into HTML, making content creation simple and maintainable.</p>
  
  <p>Key features include:</p>
  <ul>
    <li><strong>Markdown:</strong> Clean, readable format for writing content like project descriptions</li>
    <li><strong><a href="https://shopify.github.io/liquid/" target="_blank">Liquid Templating</a>:</strong> Reusable components (headers, footers, layouts) throughout the site</li>
    <li><strong>Modular Layouts:</strong> Consistent page structure with customization flexibility</li>
  </ul>
  
  <h3>GitHub Actions Workflow</h3>
  <p>The site uses <a href="https://github.com/features/actions" target="_blank">GitHub Actions</a> for automated build and deployment. Every commit triggers an automatic build process, with configurations stored in <code>.github/workflows/jekyll.yml</code>. This ensures the live site always reflects the latest changes.</p>
  
  <h3>Custom Theme & Styling</h3>
  <p>I'm using a customized version of the <a href="https://github.com/piazzai/cvless" target="_blank">cvless theme</a>, installed via a Gemfile for easy dependency management. Custom modifications include SVG icons from <a href="https://www.svgrepo.com/" target="_blank">SVG Repo</a> and adjusted CSS for improved typography and layout.</p>
  
  <div class="tech-stack">
    <strong>Tools & Technologies:</strong>
    <a href="https://jekyllrb.com/" target="_blank">Jekyll</a>, <a href="https://www.markdownguide.org/" target="_blank">Markdown</a>, <a href="https://shopify.github.io/liquid/" target="_blank">Liquid</a>, <a href="https://pages.github.com/" target="_blank">GitHub Pages</a>, <a href="https://github.com/features/actions" target="_blank">GitHub Actions</a>, <a href="https://www.namecheap.com/" target="_blank">Namecheap</a>, HTML/CSS, <a href="https://github.com/piazzai/cvless" target="_blank">cvless theme</a>
  </div>
</section>

<hr class="cv-divider">

<!-- Other Projects -->
<section class="project-section">
  <h2>Other Work</h2>
  
  <p>Fairly certain I'm not allowed to post school projects or the code I wrote for TD's data centers unless I want to get sued.</p>
</section>