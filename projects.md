---
layout: cv
title: Projects
---

<h1 style="text-align: center;">Projects</h1>

{% include contact.html %}

<h2 style="text-align: center;">Discord Chatbot with Image Manipulator</h2>

[Download the bot](https://discord.com/oauth2/authorize?client_id=850845944698241075&permissions=2147534848&integration_type=0&scope=bot+applications.commands)

Post an image and type /wojak in a server.

This project is primarily a Discord bot that fetches the last image sent in a channel, uploads it to Imgur, and overlays it with a static image using Cloudinary completely for free. The bot is deployed on Cloudflare Workers, uses the Discord API to interact with Discord, and leverages various dependencies like Wrangler, Node.js, and npm. It is also a simple calculator.

<h3 style="text-align: center;">Cloudflare Workers/Wrangler/Dependencies</h3>
The bot’s core logic (interacting with Discord and Cloudinary, processing images, etc.) is handled in a Cloudflare Worker. Wrangler is used to manage, build, and deploy the Worker. Wrangler is Cloudflare’s CLI tool. The bot’s setup and registration scripts use Node.js to interact with the Discord API and register application commands. Additionally, Node.js handles HTTP requests to Imgur and Cloudinary, providing an environment to process and interact with images. Npm is used to manage the project’s dependencies and tools like Wrangler. 

<h3 style="text-align: center;">Discord/Imgur API</h3>
The bot interacts with Discord’s API to register commands, handle slash commands, and fetch messages in Discord channels. Imgur is used as the intermediary image hosting service. When a user sends an image in Discord, the bot uploads that image to Imgur via their API. The Imgur API provides an easy way to host images and retrieve dimensions (width and height), which are essential for further image processing. Since Cloudinary doesn't recognize ephemeral media, Imgur is used to upload the image fetched from Discord and provide a permanent URL that Cloudinary can use for transformations. 

<h3 style="text-align: center;">Cloudinary and Image Processing</h3>
Cloudinary is used for dynamic image transformations and overlays. After uploading an image to Imgur, the bot retrieves the image and passes it to Cloudinary, where the bot overlays a static image (a pointing Wojak image) on top of the uploaded image. The overlaid image is scaled dynamically to the posted image's dimensions via data from Imgur. The image is then finally sent in the chat.

<h3 style="text-align: center;">Calculator function</h3>
Fairly self explanatory except for code generation from strings disallowed in Cloudflare workers due to security issues. A simple parser/evaluator is made to compensate for this.

___________________________________________________________________________________________________________________________________________________________________________________

<h2 style="text-align: center;">This Website</h2>

This project is a personal portfolio website designed to showcase my professional skills, work experience, and educational background. It's built using modern static site generation tools and hosted on GitHub Pages with a custom domain from Namecheap. It utilizes Jekyll, custom CSS for styling, and various integrations for automation and optimization.

<h3 style="text-align: center;">Static Website Hosting with GitHub Pages</h3>
The site is hosted on GitHub Pages, a free hosting platform for static websites. By using GitHub Pages, I can publish updates by pushing changes to a specific branch in the repository. GitHub Pages automates the deployment process, making it quick and easy to keep the site up-to-date with minimal effort.

<h3 style="text-align: center;">Custom Domain with Namecheap</h3>
I use a custom domain registered with Namecheap. Namecheap's DNS configuration is integrated with GitHub Pages to map the domain to my GitHub-hosted site. Luckily there is documentation online for connecting a record and CNAME to the website.

<h3 style="text-align: center;">Jekyll for Site Generation</h3>
The website is built with Jekyll, a static site generator written in Ruby. Jekyll allows for easy content management using Markdown files, while generating the necessary HTML for a fully-functional website. With Jekyll, I also used:
   
- **Markdown:** For writing content (e.g., blog posts, project descriptions) in a clean, readable format.
- **Liquid Templating Engine:** For creating reusable components (e.g., headers, footers, and layouts) throughout the website.
- **Layouts and Partials:** Modularized layouts to ensure consistency across different pages, while still allowing customization when necessary.

<h3 style="text-align: center;">Github Actions Workflow</h3>
Once you set up the automated build process integrated with github, the site is automatically built and deployed with every commit, the configurations are stored in .github/workflows/jekyll.yml

<h3 style="text-align: center;">Custom Theme and Gemfiles</h3>
To customize the look of the website, I utilized a Jekyll theme installed via a Gemfile for easy dependency management. I added a few SVG icons from svgrepo and cut/modified elements from the original theme.
<h2 style="text-align: center;">Others</h2>

Fairly certain I'm not allowed to post school projects or the code I wrote for TD's data centers unless I want to get sued.

