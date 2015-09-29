---
layout: post
title: Blogging for free with Ghost blog on Amazon EC2 Instance with your domain
date: '2014-03-31 21:34:01'
---

<img class="aligncenter" alt="" src="http://devdala.files.wordpress.com/2014/03/fritz-lang-m-1931-dvdrip-sirius-share-cd2-avi_20110910_025346-362.jpg" width="512" height="432" />

I will walkthrough the steps of blogging for free with Ghost blog on Amazon EC2, well sort of. No, it's not tumblr.

<a href="https://ghost.org/" target="_blank">Ghost</a> is a <a href="http://nodejs.org/" target="_blank">nodejs</a> based simple blogging platform. It was born in kickstarter.

I really like it. It's <em>simple</em> yet <strong>beautiful</strong>.

There are two ways to use ghost, first one is that just go to their site and create an account, after that you will have a blog with a domain &lt;your_name&gt;.ghost.io; second option is to download the source code from the site and host in your instance. Second option is more geeky. So I have gone for it.

Here is a list of things I needed to do in order to setup your own ghost instance:
<ul>
	<li>Create an <a href="http://aws.amazon.com/" target="_blank">aws</a> account, no credit card needed.</li>
	<li>Go to EC2 and create an Ubuntu (I use ubuntu at home so easier for me. However nodejs can run on any platform) instance and run it</li>
	<li>Get the IP address of the instance</li>
	<li>Connect with ssh (Don't forget to download your security group key value pair.)</li>
	<li>Forward your ports for outer connections for example: 80 which is default HTTP port</li>
	<li>Install nodejs <code>sudo apt-get install node</code></li>
	<li>Install legacy nodejs whichi will be needed to setup ghost. Some npm packages failed for me to install. <code>sudo apt-get install node-legacy</code></li>
	<li>Install node package manager npm <code>sudo apt-get install npm</code></li>
	<li>Download latest <a href="https://ghost.org/download/" target="_blank">ghost source code</a> from its site</li>
	<li>scp that zip file to your instance from your computer. Or alternatively you can do a wget in the ssh-ed instance</li>
	<li>
<pre>wget https://ghost.org/zip/ghost-0.4.2.zip</pre>
</li>
</ul>
<ul>
	<li>Install unzip and unzip the zip file<code>sudo apt-get install unzip</code></li>
	<li><code>unzip ghost-0.4.2.zip</code></li>
	<li>cd to ghost unzipped directory where core folder is. Run: <code>npm install --production</code></li>
	<li>
<pre>npm start</pre>
</li>
	<li>Stop the server - Ctrl + C</li>
	<li>Now there are two ways to redirect requests to ghost. First of all, make sure you opened your port 80 which is default port for the HTTP requests. If you want to connect your blog via &lt;IP_ADDRESS&gt; not via &lt;IP_ADDRESS&gt;:8080 (ugh ugly), you need to do this. You can do this operations under aws console on security groups -&gt; Inbounds</li>
	<li>After forwarding port 80, you need to say the instance that if a request comes to 80, ghost should handle it. This part is tricky.
<ul>
	<li>Install nginx which is a lightweight server to handle requests.</li>
	<li>
<pre>sudo apt-get install nginx</pre>
</li>
	<li><a href="http://stevemason.org/install-ghost-with-ec2-running-ubuntu-13-10/" target="_blank">Do the nginx magic</a> - Many thanks for this pal</li>
	<li>Go to &lt;IP_ADDRESS&gt;:80/ or &lt;IP_ADDRESS&gt;. They are basically same. Because default HTTP request is from port 80.</li>
	<li>My additional steps
<ul>
	<li>Nginx default page started to show up every time I go to my instance's address even though it must route requests from port 80 to localhost:2368/ (my ghost instance running there on the machine).</li>
	<li>To disable this, I did an ugly hack.</li>
	<li>
<pre>sudo nano /etc/nginx/sites-available/default</pre>
</li>
	<li>I changed first server to listen port 81 instead of port 80.</li>
	<li>
<pre>sudo service nginx restart</pre>
</li>
</ul>
</li>
</ul>
</li>
</ul>
<h2>Steps to connect this instance to your domain</h2>
<ul>
	<li>Buy a domain from <a href="godaddy.com" target="_blank">godaddy.com</a> or anywhere you want</li>
	<li>Create a totally free <a href="cloudflare.com" target="_blank">cloudflare.com</a> account - there are other alternatives. I found this the easiest.</li>
	<li>Put your domain in cloudflare and let it scan your nameservers</li>
	<li>After a while it will give you nameservers to assign to domain.</li>
	<li>Go to godaddy domain control panel or whatever provider you have and change the default nameservers to given cloudflare ones</li>
	<li>It will take some to pick it up. After making it active, go to cloudflare DNS settings</li>
	<li>Add a new A attribute with the IP of your amazon EC2 instance. It means that whenever you type your domain address, it will be responsed through your server which is running on EC2 instance in the address of &lt;IP_ADDRESS&gt;:80/ That's why we put a lot of effort to run the ghost on port 80. It's impossible to assign other ports on domains as far as I know. At least for http requests.</li>
	<li>After propagation which may take quite some time, go to your domain and check your awesome ghost blog.</li>
	<li>Congrats you have a Ghost blog on Amazon EC2!</li>
	<li>For example check mine: <a href="websitem.co" target="_blank"><strong>websitem.co</strong></a></li>
</ul>
<h2>[OPTIONAL] To change ghost default running port:</h2>
<ul>
	<li>cd to your ghost directory</li>
	<li>there is a file called config.example.js, create a copy and name it as config.js</li>
	<li>
<pre>cp config.example.js config.js</pre>
</li>
	<li>
<pre>nano config.js</pre>
</li>
	<li>At line ~40, there is "port: '2368'", change it to "port: '8080'"</li>
</ul>