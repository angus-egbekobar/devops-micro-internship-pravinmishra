# Assignment 3 — Deployments: From Basics to Rolling Updates

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

Create an NGINX Deployment, configure RollingUpdate, update the container image, roll back to the previous revision, and scale the workload.

---

# Task 0 — Pre-check: Remove the Assignment 02 ReplicaSet

## Goal

Confirm that you are connected to your learning cluster and remove the previous ReplicaSet and its managed Pods before starting this lab.

### Evidence

No screenshots required.

---

# Task 1 — Set Up the Working Directory

## Goal

Create and enter the dedicated Deployment lab directory.

### Evidence

#### Screenshot 01 — Output of `pwd` showing the directory ending in `/k8s-labs/deployments`


![alt text](image-19.png)--

# Task 2 — Create the Basic Deployment

## Goal

Create a two-replica NGINX Deployment and verify the automatically managed ReplicaSet and Pods.

### Evidence

#### Screenshot 02 — Completed basic `nginx-deployment.yaml` showing two replicas and the initial NGINX image


![alt text](image-20.png)
---

#### Screenshot 03 — Successful apply output and verification output showing the Deployment, its automatically created ReplicaSet, and two Pods with `1/1` under `READY` and `Running` under `STATUS`


![alt text](image-21.png)
---

# Task 3 — Configure the RollingUpdate Strategy

## Goal

Configure RollingUpdate to maintain the desired available replica count during an image update.

### Evidence

#### Screenshot 04 — Updated YAML showing `RollingUpdate`, `maxSurge: 1`, and `maxUnavailable: 0`


![alt text](image-22.png)
---

#### Screenshot 05 — Successful apply output and Deployment details showing the configured rolling-update strategy


![alt text](image-23.png)
---

# Task 4 — Perform and Roll Back an Image Update

## Goal

Update NGINX to 1.23.1, observe the rollout, and return to the previous stable revision.

### Evidence

#### Screenshot 06 — Image-update command and rollout status showing successful completion


![alt text](image-24.png)
---

#### Screenshot 07 — ReplicaSet output showing the previous and updated ReplicaSets, and Deployment details showing `nginx:1.23.1`


![alt text](image-25.png)
---

#### Screenshot 08 — Rollback command and rollout status showing successful completion


![alt text](image-26.png)
---

#### Screenshot 09 — Rollout history and Deployment details showing the restored `nginx:1.21.1` image


![alt text](image-27.png)
---

# Task 5 — Scale the Deployment

## Goal

Scale the workload to five replicas and return it to two.

### Evidence

#### Screenshot 10 — Scale-up command and output showing five Pods with `1/1` under `READY` and `Running` under `STATUS`


![alt text](image-28.png)
---

#### Screenshot 11 — Scale-down command and output showing the final two Pods with `1/1` under `READY` and `Running` under `STATUS`


![alt text](image-29.png)
---

# Task 6 — Share Your Kubernetes Deployment Progress on WhatsApp Status

## Goal

Share your Kubernetes Deployment learning progress on WhatsApp Status, including your generated DMI leaderboard progress link.

### Steps

1. Go to the DMI Leaderboard.
2. Find your name and select **Share your progress**.
3. Click the **WhatsApp icon**.
4. Copy the automatically generated leaderboard message containing your rank and progress link.
5. Open WhatsApp and go to **Updates**.
6. Create a new text Status.
7. Copy and paste the message below.
8. Insert the generated leaderboard message in the indicated place.
9. Review and publish your Status.

### WhatsApp Status Message

I practiced Kubernetes Deployments as part of my DevOps learning journey! 🚀

Today, I deployed NGINX, configured rolling updates, updated the container image, and rolled back to the previous version.

I also scaled my Deployment from two Pods to five and back to two!

[PASTE YOUR GENERATED LEADERBOARD MESSAGE AND LINK HERE]

#DMIByPravinMishra #DevOps #Kubernetes

### Evidence

#### Screenshot 12 — Published WhatsApp Status showing your Kubernetes Deployment message and generated DMI leaderboard progress link

Add your screenshot here.

A draft or editing screen is not sufficient.

---

# Lab Summary

Write a short note explaining how Deployments manage ReplicaSets, perform rolling updates and rollbacks, and scale Pods.


A Deployment in Kubernetes is a higher-level abstraction that manages ReplicaSets and ensures Pods run reliably.

Managing ReplicaSets:
Deployments automatically create and update ReplicaSets, which in turn maintain the desired number of Pod replicas. When you update a Deployment, Kubernetes generates a new ReplicaSet and gradually shifts traffic from the old one to the new one.

Rolling Updates:
Deployments perform rolling updates by incrementally replacing Pods from the old ReplicaSet with Pods from the new one. This minimizes downtime and ensures continuous availability during upgrades.

Rollbacks:
If something goes wrong, Deployments support rollbacks to previous ReplicaSet revisions. This allows you to quickly restore a stable version of your application.

Scaling Pods:
Deployments make scaling easy — you can increase or decrease the number of replicas with a single command (kubectl scale deployment <name> --replicas=N). Kubernetes ensures the desired number of Pods are running at all times.
---

# Submission Instructions

- Include all required screenshots, numbered 01–12.
- Ensure screenshots are clear and readable.
- Submit the final `nginx-deployment.yaml` containing two replicas, the initial NGINX image, and the configured RollingUpdate strategy.
- Complete the Lab Summary in your own words.
- Include evidence of your published WhatsApp Status.
- Do not expose passwords, tokens, private keys, or kubeconfig credentials.

---

# Completion Checklist

- [ ] Completed Task 0
- [ ] Created the deployments directory (Screenshot 01)
- [ ] Created the basic two-replica NGINX Deployment manifest (Screenshot 02)
- [ ] Applied the Deployment and verified its ReplicaSet and two running Pods (Screenshot 03)
- [ ] Added RollingUpdate with `maxSurge: 1` and `maxUnavailable: 0` (Screenshot 04)
- [ ] Applied and verified the rolling-update strategy (Screenshot 05)
- [ ] Updated NGINX to 1.23.1 and confirmed rollout completion (Screenshot 06)
- [ ] Inspected the ReplicaSets and verified the updated image (Screenshot 07)
- [ ] Rolled back the update and confirmed rollout completion (Screenshot 08)
- [ ] Reviewed rollout history and verified the restored image (Screenshot 09)
- [ ] Scaled to five running Pods (Screenshot 10)
- [ ] Scaled back to two running Pods (Screenshot 11)
- [ ] Published the WhatsApp Status with the generated leaderboard progress link (Screenshot 12)
- [ ] Submitted the final `nginx-deployment.yaml`
- [ ] Included screenshots 01–12
- [ ] Completed the Lab Summary
- [ ] No sensitive data exposed

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
