<h1>🚀 Project Overview</h1>

<p><strong>
This project demonstrates how to host a static HTML/CSS/JS website on an AWS EC2 Linux instance using NGINX as the web server.  
The setup includes:
</strong></p>

<ul>
  <li><strong>EC2 Instance (Ubuntu/Amazon Linux)</strong></li>
  <li><strong>NGINX Web Server</strong></li>
  <li><strong>Static Website Deployment</strong></li>
  <li><strong>Secure access using SSH</strong></li>
  <li><strong>Network configuration with TCP/IP, HTTP, and Security Groups</strong></li>
</ul>

<hr/>

<h1>🛠️ Tech Stack</h1>
<ul>
  <li><strong>AWS EC2 – Compute hosting</strong></li>
  <li><strong>NGINX – Web server for serving static content</strong></li>
  <li><strong>HTML/CSS/JS – Frontend static website</strong></li>
  <li><strong>SSH – Secure shell for remote access</strong></li>
  <li><strong>TCP/IP – Network communication</strong></li>
  <li><strong>HTTP/HTTPS – Web protocols</strong></li>
</ul>

<hr/>

<h1>📁 Project Structure</h1>

<pre>
<code>
/project-root
│── index.html
│── styles/
│── scripts/
└── README.md
</code>
</pre>

<hr/>

<h1>🧩 Steps to Host Static Website on AWS EC2 Using NGINX</h1>

<h2>1️⃣ Launch EC2 Instance</h2>
<ul>
  <li><strong>Choose Ubuntu or Amazon Linux</strong></li>
  <li><strong>Create/Download Key Pair (.pem)</strong></li>
  <li><strong>Configure Security Group</strong></li>
  <li><strong>Allow SSH (port 22)</strong></li>
  <li><strong>Allow HTTP (port 80)</strong></li>
  <li><strong>(Optional) Allow HTTPS (port 443)</strong></li>
</ul>

<h2>2️⃣ Connect to EC2 Using SSH</h2>

<pre>
<code>ssh -i "your-key.pem" ubuntu@your-public-ip</code>
</pre>

<h2>3️⃣ Install & Start NGINX</h2>

<pre>
<code>
sudo apt update
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
</code>
</pre>

<p><strong>Verify:</strong></p>
<pre><code>http://your-public-ip</code></pre>

<h2>4️⃣ Deploy Static Website</h2>

<p><strong>Remove default NGINX page:</strong></p>
<pre><code>sudo rm -f /var/www/html/index.nginx-debian.html</code></pre>

<p><strong>Copy your website files:</strong></p>
<pre><code>sudo cp -r * /var/www/html/</code></pre>

<p><strong>Restart NGINX:</strong></p>
<pre><code>sudo systemctl restart nginx</code></pre>

<hr/>

<h1>🔐 Security Protocols Used</h1>

<h3>✔ SSH (Secure Shell)</h3>
<p><strong>Used for secure remote login to the EC2 instance using a key pair instead of passwords.</strong></p>

<h3>✔ TCP/IP</h3>
<p><strong>Handles the network communication between the client (browser) and the AWS server.</strong></p>

<h3>✔ HTTP</h3>
<p><strong>Default protocol used to serve the website on port 80.</strong></p>

<h3>✔ Security Groups</h3>
<p><strong>Firewall rules to allow:</strong></p>
<ul>
  <li><strong>SSH (22)</strong></li>
  <li><strong>HTTP (80)</strong></li>
  <li><strong>(Optional) HTTPS (443)</strong></li>
</ul>

<hr/>

<h1>🌍 Access Your Website</h1>
<pre><code>http://&lt;your-public-ip&gt;</code></pre>

<hr/>

<h1>📦 Deployment Notes</h1>
<ul>
  <li><strong>If old page loads → clear browser cache or restart NGINX.</strong></li>
  <li><strong>Make sure security group allows port 80.</strong></li>
  <li><strong>Ensure the HTML file is named index.html.</strong></li>
</ul>
