# Setup and Deployment

Hosting your website involves preparing files, selecting a hosting provider, connecting your domain, and uploading your project to a live server. This process is known as **deployment**.

## 1. Steps to Host a Website

### **Step 1: Build Your Website**

Create your project using HTML, CSS, JavaScript, or frameworks like React, Node.js, etc.  
Ensure your files are organized, for example:

```text
/project-folder
├── index.html
├── about.html
├── styles.css
├── script.js
└── /images
```

### **Step 2: Choose a Hosting Provider**

Select a hosting type based on your website:

- **Static website:** Netlify, Vercel, GitHub Pages  
- **Dynamic / Full-stack app:** Render, Railway, AWS, DigitalOcean  
- **WordPress site:** Bluehost, Hostinger  

### **Step 3: Get a Domain Name**

Purchase a domain name (e.g., `yourname.com`) from:

- Domain registrars like **Namecheap**, **GoDaddy**, or **Google Domains**  
- Some hosting providers include a **free domain** in their plans  

### **Step 4: Connect Domain to Hosting**

To link your domain with your hosting server, update the **DNS records**:

| Record Type | Purpose | Example |
|--------------|----------|----------|
| **A Record** | Points domain to server IP | `example.com → 192.168.1.1` |
| **CNAME** | Points subdomain to another domain | `www → example.com` |
| **MX** | Handles email routing | `mail.example.com` |

**Note:** DNS changes can take up to **24–48 hours** to fully update (DNS propagation).

### **Step 5: Upload Website Files**

There are several ways to upload your project files:

#### **Option 1: File Manager (via cPanel)**

1. Log in to your hosting cPanel.  
2. Open **File Manager** → `public_html` folder.  
3. Upload your files and extract (if zipped).  
4. Visit your domain to see your live website.

#### **Option 2: FTP (File Transfer Protocol)**

1. Install an FTP client like **FileZilla**.  
2. Enter your FTP credentials from your hosting account.  
3. Connect to the server.  
4. Drag and drop your website files to the server’s root folder.  

#### **Option 3: Git-Based Deployment**

For providers like **Netlify**, **Vercel**, or **Render**:

1. Push your project to **GitHub / GitLab / Bitbucket**.  
2. Link your repository to the hosting platform.  
3. The platform automatically deploys your site on every push.  

## 2. Deployment for Full-Stack Projects

### **Frontend + Backend Example**

If you built a MERN stack app:

- **Frontend (React):** Host on **Vercel** or **Netlify**.  
- **Backend (Node.js/Express):** Host on **Render** or **Railway**.  
- **Database:** Use **MongoDB Atlas** or **Firebase**.  

**Steps:**

1. Deploy backend → get API URL (e.g., `https://api.render.com`).  
2. Update frontend `.env` or config with API URL.  
3. Deploy frontend → site connects to live backend.  

## 3. Continuous Deployment (CD)

Most modern hosts like **Vercel**, **Netlify**, and **Render** support automatic deployment:

- Whenever you push new code to GitHub → your live website updates automatically.  
This is known as **Continuous Deployment** or **CI/CD**.

## 4. Verifying Deployment

After deployment:

- Visit your website URL (e.g., `https://myproject.netlify.app`).  
- Check responsiveness and loading speed.  
- Test all links, forms, and APIs.  
- Enable **SSL (HTTPS)** from your hosting dashboard.  

## 5. Common Deployment Issues

| Issue | Cause | Solution |
|--------|--------|-----------|
| Site not loading | Wrong DNS setup | Verify A/CNAME records |
| Files not visible | Uploaded to wrong directory | Use `public_html` or root folder |
| Changes not updating | Cached version | Clear cache / redeploy |
| SSL not working | Not enabled | Activate SSL from dashboard |
| 404 Errors | Wrong paths | Check file names and routes |
