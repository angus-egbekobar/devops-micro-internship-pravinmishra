# Assignment 5 — Publish a Docker Container on Docker Hub

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

In this assignment, you will publish a Dockerized React application to Docker Hub, remove the local image tags, pull the image again from Docker Hub, and run it to verify that it can be downloaded and deployed from a container registry.

---

# Task 1 — Publish a Docker Image to Docker Hub

## Goal

Tag a locally built React image, publish it to Docker Hub, remove the local copy, pull it again from Docker Hub, and run it successfully.

### Evidence

#### Screenshot 1 — Public Docker Hub Repository

Add a screenshot of Docker Hub showing your newly created public repository:

```text
my-react-app
```


![alt text](image-71.png)
---

#### Screenshot 2 — Successful Docker Login

Add a screenshot of the terminal showing:

```text
Login Succeeded
```

Ensure that your full name is visible and that no password, Personal Access Token, or device code is exposed.


![alt text](image-72.png)
---

#### Screenshot 3 — Correctly Tagged Image

Add a screenshot of the terminal showing:

```bash
docker image ls <YOUR_DOCKERHUB_USERNAME>/my-react-app
```

The output must show the `latest` tag.


![alt text](image-74.png)
---

#### Screenshot 4 — Successful Docker Push

Add a screenshot of the terminal showing successful completion of:

```bash
docker push <YOUR_DOCKERHUB_USERNAME>/my-react-app:latest
```

The output must include a pushed status or image digest.


![alt text](image-75.png)
---

#### Screenshot 5 — Published `latest` Tag in Docker Hub

Add a screenshot of your Docker Hub repository showing the uploaded `latest` image tag.


![alt text](image-76.png)
---

#### Screenshot 6 — Local Image Removed and Pulled Again

Add a screenshot of the terminal showing:

- The targeted local image tags removed
- Successful `docker pull` output
- `docker image ls` showing the pulled image


![alt text](image-77.png)
---

#### Screenshot 7 — Running Pulled Image

Add a screenshot of the terminal showing:

```bash
docker ps
```

The output must show the running `react-container` with:

```text
0.0.0.0:80->80/tcp
```


![alt text](image-78.png)
---

#### Screenshot 8 — React Application in Browser

Add a browser screenshot showing the React application at:

```text
http://52.90.157.13
```

Ensure that the VM public IP is visible in the address bar. Add your full name as a clear caption directly below the screenshot.


![alt text](image-79.png)
---

# Docker Hub Repository URL

**Repository URL:** https://hub.docker.com/repository/docker/angusegbekobar/my-react-app/general

---

# Registry and Image Tagging Notes

Write a short explanation covering:

- Why image tagging is required before pushing to Docker Hub
- Why a container registry is useful in DevOps workflows
- Why production deployments should use versioned image tags instead of relying only on `latest`

Write your explanation here.
### Why image tagging is required before pushing to Docker Hub

 * A locally built image has a short name like my-react-app, which tells Docker nothing about where it should go. Docker Hub identifies an image by username/repository:tag, so the image has to be tagged with that full name before a push. For example, docker tag my-react-app angusegbekobar/my-react-app:latest gives it the angusegbekobar namespace that Docker Hub checks against your login. Without it, docker push fails with an access or “repository does not exist” error, because Docker would try to push to a namespace you don’t own. The tag also tells the registry which version of the image you are uploading.

 ### Why a container registry is useful in DevOps workflows

* A registry is a central, shared store for images. Once an image is pushed, any machine with access can pull it, including teammates, CI/CD pipelines, staging servers and production servers. This means the exact image that was built and tested is the one that gets deployed, instead of rebuilding from source on every machine and risking differences. Registries also keep a history of versions, which makes rollbacks easy, and they support access control, automated builds and vulnerability scanning. They are the link between building an image in CI and running it in production.

### Why production deployments should use versioned tags instead of only latest

* latest is just a default tag name, not a guarantee of the newest or the safest image. It is a moving label that points to whatever was pushed last, so the same latest can mean different things on different days or different servers. That makes deployments unpredictable and hard to reproduce, and a node that pulls fresh may run a different version from one that cached an older image. Rolling back is also hard, because the previous latest has been overwritten. Versioned tags such as v1.2.0, a build number or a Git commit hash identify exactly one image, so you can see what is running, repeat a deployment, audit changes and roll back by redeploying the earlier tag. A common practice is to push both a version tag and latest, and to deploy only the version tag.
---

# LinkedIn Requirement

## Goal

Create a LinkedIn post about publishing a Docker container image to Docker Hub.

Include:

- Assignment title: **Publish a Docker Container Image to Docker Hub**
- Your Docker Hub repository URL
- What you published
- How you verified the remote image by pulling and running it
- Key learning outcomes

### Evidence

#### LinkedIn Post URL

Paste your LinkedIn post URL here:

https://lnkd.in/p/euydkx7s

---

#### LinkedIn Post Screenshot

Add a screenshot of the published LinkedIn post here.
![alt text](image-80.png)
---

# Submission Instructions

- Complete all steps in sequence.
- Include Screenshots 1–8 exactly as specified.
- Include your Docker Hub repository URL.
- Include the Registry and Image Tagging Notes.
- Include the LinkedIn post URL and screenshot.
- Ensure that your full name is visible in all terminal screenshots.
- Add your full name as a clear caption below the browser screenshot.
- Do not expose passwords, Personal Access Tokens, device codes, credentials, or other sensitive information.

---

# Completion Checklist

- [ ] Public `my-react-app` repository created
- [ ] Docker login completed successfully
- [ ] `react-multistage:latest` tagged correctly
- [ ] Image pushed to Docker Hub
- [ ] `latest` tag verified in Docker Hub
- [ ] Targeted local image tags removed
- [ ] Image pulled again from Docker Hub
- [ ] Pulled image runs successfully
- [ ] React application is accessible through the VM public IP
- [ ] Docker Hub repository URL included
- [ ] Registry and image-tagging notes completed
- [ ] LinkedIn post URL and screenshot included
- [ ] All required screenshots included
- [ ] Full name visible in terminal screenshots
- [ ] Browser screenshot has a full-name caption
- [ ] No passwords, tokens, or credentials exposed
---

## 📌 About DMI & CloudAdvisory

DevOps Micro Internship (DMI) is a project-based DevOps program run by Pravin Mishra (The CloudAdvisory) focused on real-world execution, systems thinking, and career readiness.

It helps learners build strong DevOps foundations with hands-on experience.

---

## 📌 Resources

- 🌐 DMI Official Website: https://dmi.pravinmishra.com?utm_source=github&utm_medium=readme  
- 🎓 University: https://university.pravinmishra.com?utm_source=github&utm_medium=readme  
- 💬 Discord Community: https://discord.pravinmishra.com?utm_source=github&utm_medium=readme  
- 📝 Blog: https://dmi.pravinmishra.com/blog?utm_source=github&utm_medium=readme  
- ▶️ YouTube Playlist: https://www.youtube.com/playlist?list=PLFeSNDtI4Cho  
- 🔗 Pravin Mishra (LinkedIn): https://www.linkedin.com/in/pravin-mishra-aws-trainer/  
- 🏢 CloudAdvisory (LinkedIn): https://www.linkedin.com/company/thecloudadvisory/

---

*This submission is part of DevOps Micro Internship (DMI) — Agentic AI Track.*
