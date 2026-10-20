# Assignment 3 — Docker Networking

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

In this assignment, you will explore Docker network types and deploy applications using different networking modes: the default bridge network, a custom bridge network for microservices, multiple networks for a multi-tier architecture, and host networking.

---

# Task 1 — Deploy a Standalone Application Using Docker Bridge Network

## Goal

List Docker networks, verify/pull the Nginx image, run an Nginx container (`myweb`) on the default bridge network with port 80 mapped, and verify it's reachable from a browser via the VM's public IP.

### Evidence

#### Screenshot 1 — Output of `docker network ls`


![alt text](image-17.png)
---

#### Screenshot 2 — Output of `docker images`


![alt text](image-18.png)
---

#### Screenshot 3 — Output of `docker search nginx`


![alt text](image-19.png)
---

#### Screenshot 4 — Successful `docker pull nginx` (if applicable)


![alt text](image-20.png)
---

#### Screenshot 5 — Output of `docker ps` showing the running `myweb` container


![alt text](image-21.png)
---

#### Screenshot 6 — Browser displaying the Nginx Welcome Page using the Public IP address


![alt text](image-22.png)
---

# Task 2 — Connect Multiple Containers Using a Custom Bridge Network

## Goal

Create a custom bridge network `mynetwork`, build and run a Node/Express `frontend` container and an Nginx `backend` container on it, and verify they can communicate by container name.

### Evidence

#### Screenshot 1 — Output of `docker network create mynetwork`


![alt text](image-23.png)
---

#### Screenshot 2 — Output of `docker network ls`


![alt text](image-24.png)
---

#### Screenshot 3 — Frontend Dockerfile


![alt text](image-25.png)
---

#### Screenshot 4 — Successful `docker build` for the frontend


![alt text](image-26.png)
---

#### Screenshot 5 — Output of `docker ps` showing the frontend container


![alt text](image-27.png)
---

#### Screenshot 6 — Output of `docker ps` showing both frontend and backend containers


![alt text](image-28.png)
---

#### Screenshot 7 — Output of `docker network inspect mynetwork`


![alt text](image-29.png)
---

#### Screenshot 8 — Successful `curl http://<Public-IP>` showing "Hello from Frontend"


![alt text](image-30.png)
---

#### Screenshot 9 — Successful `curl backend` output from the frontend container showing the Nginx Welcome Page


![alt text](image-32.png)
---

# Task 3 — Deploy a Multi-Tier Application Using Multiple Docker Networks

## Goal

Build a three-tier app (frontend, backend, MongoDB) across `backend-network` (backend ↔ database) and `frontend-network` (frontend ↔ backend), and verify data flows end to end.

### Evidence

#### Screenshot 1 — Creation of `backend-network`


![alt text](image-33.png)
---

#### Screenshot 2 — Creation of `frontend-network`


![alt text](image-34.png)
---

#### Screenshot 3 — Project folder structure


![alt text](image-35.png)
---

#### Screenshot 4 — Database Dockerfile


![alt text](image-36.png)
---

#### Screenshot 5 — Backend Dockerfile


![alt text](image-37.png)
---

#### Screenshot 6 — Frontend Dockerfile


![alt text](image-38.png)
---

#### Screenshot 7 — Successful Docker image builds (database, backend, frontend)


![alt text](image-39.png)
---

#### Screenshot 8 — Running containers (`docker ps`)


![alt text](image-40.png)
---

#### Screenshot 9 — Output of `docker network inspect backend-network`


![alt text](image-41.png)
---

#### Screenshot 10 — Output of `docker network inspect frontend-network`


![alt text](image-44.png)
---

#### Screenshot 11 — Browser showing the frontend application


![alt text](image-45.png)
---

#### Screenshot 12 — Successful `curl api` from the frontend container


![alt text](image-46.png)
---

#### Screenshot 13 — MongoDB connection using `mongosh`


![alt text](image-49.png)
---

#### Screenshot 14 — Successful document insertion


![alt text](image-48.png)
---

#### Screenshot 15 — Successful retrieval of the inserted document


![alt text](image-50.png)
---

# Task 4 — Deploy an Application Using Docker Host Network Mode

## Goal

Deploy an Nginx container (`fastapp`) using Host Network Mode and verify it's reachable without explicit port mapping, then confirm the `NetworkMode` and clean up.

### Evidence

#### Screenshot 1 — Output of `docker run --network host`


![alt text](image-51.png)
---

#### Screenshot 2 — Output of `docker ps` showing the running `fastapp` container


![alt text](image-52.png)
---

#### Screenshot 3 — Browser or terminal displaying the Nginx Welcome Page


![alt text](image-53.png)
---

#### Screenshot 4 — Output of `docker inspect fastapp | grep "NetworkMode"`


![alt text](image-54.png)
---

#### Screenshot 5 — Successful cleanup showing `docker stop fastapp` and `docker rm fastapp`


![alt text](image-55.png)
---

# LinkedIn Post (Optional)

## Goal

Create a LinkedIn post covering the assignment objective, networking modes explored, key learning outcomes, and a short reflection on Docker networking concepts.

## Evidence

#### LinkedIn Post URL

Paste your LinkedIn post URL here:


https://lnkd.in/p/ex6Q_Kyp
---

#### Screenshot — Published LinkedIn post


![alt text](image-56.png)
---

# Submission Instructions

- Add all required screenshots in your submission
- Full name must be visible in required screenshots
- Do not expose sensitive information

---

# Completion Checklist

- [ ] Task 1: Standalone app on default bridge network deployed and verified (Screenshots 1–6)
- [ ] Task 2: Custom bridge network with frontend/backend communication verified (Screenshots 1–9)
- [ ] Task 3: Multi-tier app across two networks deployed and verified end to end (Screenshots 1–15)
- [ ] Task 4: Host network mode deployment verified and cleaned up (Screenshots 1–5)
- [ ] No sensitive information exposed

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
