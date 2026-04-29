<div align="center">
<h1>📄 Rapid-OCR 🔍</h1>

[![Codacy Badge](https://app.codacy.com/project/badge/Grade/b8aaeed0115c45f08d6e75600e538324)](https://app.codacy.com/gh/R0mb0/Rapid_OCR/dashboard?utm_source=gh&utm_medium=referral&utm_content=&utm_campaign=Badge_grade)
[![pages-build-deployment](https://github.com/R0mb0/Rapid_OCR/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/R0mb0/Rapid_OCR/actions/workflows/pages/pages-build-deployment)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/R0mb0/Rapid_OCR)
[![Open Source Love svg3](https://badges.frapsoft.com/os/v3/open-source.svg?v=103)](https://github.com/R0mb0/Rapid_OCR)
[![MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/license/mit)
[![Donate](https://img.shields.io/badge/PayPal-Donate%20to%20Author-blue.svg)](http://paypal.me/R0mb0)

<p>
A lightning-fast, privacy-first web app for offline text extraction. Paste (Ctrl+V) or drop any image to instantly generate plain text and a searchable PDF entirely within your browser using Tesseract.js. No server uploads required. Fast, secure, and ready to use! 🚀
</p>

<div align="center">
  <a href="http://paypal.me/R0mb0">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://github.com/R0mb0/Support_the_dev_badge/blob/main/Badge/SVG/Support_the_dev_badge_Dark.svg">
      <source media="(prefers-color-scheme: light)" srcset="https://github.com/R0mb0/Support_the_dev_badge/blob/main/Badge/SVG/Support_the_dev_badge_Light.svg">
      <img alt="Saved you time? Support the dev" src="https://github.com/R0mb0/Support_the_dev_badge/blob/main/Badge/SVG/Support_the_dev_badge_Default.svg">
    </picture>
  </a>
</div>


## [👉 Click here to launch the app! 👈](https://r0mb0.github.io/Rapid_OCR/)

[![01.png](https://github.com/R0mb0/Rapid_OCR/blob/main/Readme_imgs/01.png)](https://r0mb0.github.io/Rapid_OCR/)
[![02.png](https://github.com/R0mb0/Rapid_OCR/blob/main/Readme_imgs/02.png)](https://r0mb0.github.io/Rapid_OCR/)
[![03.png](https://github.com/R0mb0/Rapid_OCR/blob/main/Readme_imgs/03.png)](https://r0mb0.github.io/Rapid_OCR/)

</div>
<hr>

<h2>🚀 Features</h2>
<ul>
<li><strong>Instant Ctrl+V Support</strong>: No need to click through clunky upload menus. Just copy an image to your clipboard and paste it directly into the app to start the extraction.</li>
<li><strong>Searchable PDF Generation</strong>: Doesn't just give you raw text! It magically overlays invisible text boxes over the original image, generating a fully searchable and selectable PDF on the fly.</li>
<li><strong>Multi-Language Support</strong>: Automatically recognizes and processes multiple European languages simultaneously (English, Italian, French, Spanish, German), handling special characters flawlessly.</li>
<li><strong>100% Client-Side & Private</strong>: Built entirely with HTML, CSS, and Vanilla JavaScript. Your images and documents are processed locally in your browser. Nothing is ever uploaded to a cloud server.</li>
<li><strong>Offline Capable</strong>: Run the app entirely without an internet connection using local assets and language packs.</li>
</ul>

<h2>🛠️ How it works</h2>
<ol>
<li><strong>Initialization:</strong> Upon loading or pasting an image, the app initializes a local <code>Tesseract.js</code> Web Worker, loading the necessary language data packs into the browser's memory.</li>
<li><strong>Processing:</strong> The image data is passed to the Web Assembly (WASM) core of Tesseract, which scans the pixels, recognizes characters, and calculates the layout.</li>
<li><strong>Concurrent Output:</strong> Tesseract simultaneously returns both the extracted raw text and the ArrayBuffer data for the PDF document.</li>
<li><strong>Blob Conversion:</strong> The app instantly converts the PDF data into a Blob, creating a downloadable file directly from your browser memory, while displaying the text on-screen concurrently.</li>
</ol>

<h2>🏆 What makes it special?</h2>
<ul>
<li><strong>Zero-Setup Friction</strong>: Designed to be an immediate utility tool. You don't need to log in, select languages from dropdowns, or wait in server queues. Paste and go.</li>
<li><strong>Modern UI/UX</strong>: Clean, responsive design powered by Tailwind CSS that keeps you informed of the OCR progress every step of the way without visual clutter.</li>
</ul>

<h2>💡 Why use this project?</h2>
<ul>
<li><strong>For Sensitive Documents</strong>: The perfect solution when you need to extract text from private documents, bank statements, or confidential notes, and you don't trust free online OCR services that might store and harvest your files.</li>
</ul>

<h2>⚡ Getting Started</h2>

<h3>Online</h3>
<p>Simply open the <a href="https://r0mb0.github.io/Rapid_OCR/">Live Demo link</a> on any browser, paste an image, and grab your text!</p>

<h3>Testing Locally & Offline (Python Web Server)</h3>
<p>If you have downloaded the repository to use it completely offline, you cannot simply double-click the <code>index.html</code> file. Because the app uses advanced Web Workers to process images, modern browsers block them from running via the standard <code>file:///</code> protocol due to CORS security restrictions.</p>
<p>To run it locally, you need to spin up a quick local web server. The easiest way is using <strong>Python</strong>.</p>

<h4>1. Install Python (if you don't have it)</h4>
<ul>
<li><strong>Windows:</strong> Open PowerShell as Administrator and run: <br><code>choco install python</code> <br><em>(Requires <a href="https://chocolatey.org/">Chocolatey</a>)</em></li>
<li><strong>macOS:</strong> Open Terminal and run: <br><code>brew install python</code> <br><em>(Requires <a href="https://brew.sh/">Homebrew</a>)</em></li>
<li><strong>Linux (Debian/Ubuntu):</strong> Open Terminal and run: <br><code>sudo apt update && sudo apt install python3</code></li>
</ul>

<h4>2. Launch the Local Server</h4>
<ol>
<li>Open your terminal or command prompt.</li>
<li>Navigate to the folder where you extracted this project (e.g., <code>cd path/to/RapidOCR</code>).</li>
<li>Run the following command:
<ul>
<li>On Windows: <code>python -m http.server 8000</code></li>
<li>On Mac/Linux: <code>python3 -m http.server 8000</code></li>
</ul>
</li>
<li>Open your browser and type <code>http://localhost:8000</code> in the address bar. The app is now running securely and fully offline!</li>
</ol>

<h2>⚠️ Troubleshooting: Language Loading</h2>
<p>
  If the OCR seems stuck at "Loading..." during your very first run on the live version, ensure your internet connection is active so the browser can cache the Tesseract language data files. Once cached, subsequent runs will be instantaneous. If you are running the offline local server version, ensure your <code>tessdata</code> folder contains all the downloaded <code>.traineddata.gz</code> files.
</p>

<br>

<a href="https://github.com/R0mb0/Crafted_with_AI">
<picture>
<source media="(prefers-color-scheme: dark)" srcset="https://github.com/R0mb0/Crafted_with_AI/blob/main/Badge/SVG/CraftedWithAIDark.svg">
<source media="(prefers-color-scheme: light)" srcset="https://github.com/R0mb0/Crafted_with_AI/blob/main/Badge/SVG/NotMadeByAILight.svg">
<img alt="Crafted with AI" src="https://github.com/R0mb0/Crafted_with_AI/blob/main/Badge/SVG/CraftedWithAIDefault.svg">
</picture>
</a>
