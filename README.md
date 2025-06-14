# Project Documentation
This document details the complete technical process of deploying and managing the dynamic landing page project on an AWS EC2 instance, including server setup,web server configuration, deployment and version control.

# Project Setup
* Launched the AWS Management Console.
* Logged into the AWS Management Console.
* Navigated to the EC2 dashboard and launched a new Ubuntu Server 22.04 LTS instance- with the name tag **Alt-Cloud-Project-  01**
* Selected an instance type optimized for free tier
* Used an existing SSH key pair for secure access.
* Configured security group inbound rules to allow:
   * **SSH (port 22) for remote terminal access**
   * **HTTP (port 80) to serve web traffic**
   * **HTTPS (port 443) for secure connections** 
*Launched the instance and noted the public IP address for later use.

# Connecting to the Instance
* Connected using VS Code’s Remote - SSH extension with the command : **ssh -i "/C/Users/BUKOLA/Downloads/MY-Key-Pair.pem" ubuntu@myPublic Ip address**
* Verified successful SSH connection and server accessibility.

 # Server Setup
 * Updated package lists to get latest packGE info **sudo apt update**
 * Upgraded installed packages to the latest versions  **sudo apt upgrade -y**
 * Installed required package for web hosting **sudo apt install nginx -y**

 # Web Server Configuration (Nginx)
 * Enabled  nginx service to start on boot **sudo systemctl enable nginx**
 * Started nginx immediately - **sudo systemctl start nginx**
 * Verified nginx service status -** sudo systemctl status nginx**
 * Confirmed ngnix was serving the defualt web page by visiting the public Ip address in a browser.
 * Manually uploaded my landing page project file to the server's web root
 * Navigated to the Nginx default directory cd/var/www/html
 * Removed the default index.nginx-debian.html.file **sudo rm index.nginx-debian.html**
*  Copied my landing page files into **/var/www/html/**
 *  Restarted Nginx to serve the new landing page
 

### Frontend Development Process
The landing page was designed to be dynamic, clean and responsive with modern styling and interactivity:
* Structure-Built using semantic HTML5
* Sections included:Header with animated title and subtitle; content sections with heading and paragraphs.
  **STYLING**
### Custom color palette:
* Background:#f6f6f6
* Accent:#114B5F, #028090, #38D9A9
### CSS animations
* fadeIn for headers
* slideUp for content sections
* Added Interactive hover effects
* Used media queris to maintain readibility and accessibility across screen sizes
  
### Deployment
* Navigated to the web root
* Transferred projects files using Visual studio code Remote -SSH
* Opened VSCode--- Connected via SSH
* Dropped index.html,style.css and supporting files into /var/www/html
* Confirmed proper file permissions with **sudo chmod -R 755 /var/www.html**

 ### Testing
 * Visited the public IP in browser http://ec2-public ip
 * Confirmed:page loaded succesfully, animations and hover effects functioned correctly, fully responsive on mobile and     tablet 
 ### Git and Github Version Control
 * After building the landing page locally, i used Git Bash to intialise a Git repository and the fles to Github
  #### Steps taken:
 * Initialized Git in the project folder**git init**
 * Added all project files **git add .**
 * Committed with a message   **git commit -m "Initial commit -Altcloud file"**
 * Connected to remote Github Repository- **git remote add origin https://github.com/Adebukol8/SkyOps-Landing-Page.git**    * pushed the code to the main brach- Before pushing, i rebased and pulled to avoid confilt, as the remote haD A README file- **git pull --rebase origin main**
 * I then pushed the project - **git push origin main**
* This step ensured my local landing page files were properly hosted and tracked on Github.


### Hosting Information
During development and testing, the landing page was hosted on a public EC2 instance using its IPv4 address
**Public Ip: http://54.155.125.177/**

**Note: This Ip was temporarily used during development and may become unreachable once I shutdown my EC2  instance to avoid further billing.The final version of this project is deployed and accessible via Github pages:**
**LIVE URL: https://adebukol8.github.io/SkyOps-Landing-Page/**





 ## Challenges and Learnings
 * As a beginner, this project tested me in several ways:

- **Github & Verion Control**
  * At first, pushing to the GitHub repository was blocked due to conflicts with existing remote files (like the README). I learned how to fetch, pull, and rebase properly to keep my commit history clean and avoid overwriting others work.

 **CSS Animations & Hover Effects**  
  * Implementing smooth animations while keeping the design subtle yet attractive required trial and error. I had to balance color schemes, transitions, and responsive design so the landing page looks great on all devices.

 **Responsive Design**  
  * Making sure the page works seamlessly on different screen sizes was challenging, especially with typography scaling and layout shifts. Media queries helped a lot here.

 **Working with Remote Development**  
  * Using VS Code's Remote SSH extension allowed me to develop directly on the server. This experience was new to me and taught me the benefits and limitations of remote development workflows.

 **Honest Reflection**  
  * This project pulled me out of my comfort zone in both front-end design and deployment. I improved my problem-solving skills, patience with version control, and learned to write cleaner code and proper documentation of each step.

---


  

