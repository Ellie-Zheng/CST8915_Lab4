# CST8915 Lab 4 - CST8915 Full-stack Cloud-native Development: Introduction to Docker

- **Student Name**: Ellie Zheng
- **Student ID**: 041078727
- **Course**: CST8915 Full-stack Cloud-native Development
- **Semester**: Fall 2026

---

## Demo Video

🎥 [Watch Demo Video](https://youtu.be/BlrukRsQ1tA)

## Reflection Questions

### What are the main differences between a Docker image and a Docker container?

A Docker image is a saved template that contains an application and everything it needs to run, acting as a static, read-only blueprint of the application code, environment, and dependencies. A container is a runnable, isolated instance created from that image, with a thin writable layer for changes made while it runs. For example, in this lab, I used a single image as a blueprint to start three separate Python containers `app1`, `app2`, `app3` running simultaneously.

### Explain how Docker's layered architecture improves efficiency

Docker builds an image in layers and can reuse layers that have not changed. When I changed `app.py`, Docker reused the layers for the base image and the dependencies in requirements.txt. It only needed to rebuild the parts affected by my code change, which saved time.

### Why does each container get its own writable layer?

Each container gets its own writable layer so it can make changes without changing the shared image or other containers. I started two separate containers, `app1` and `app2`, from the same image. After I added a line to app.py in `app1`, the file in app2 still showed its original content. This showed me that the change stayed in `app1`.

### What are the benefits of using Docker Compose over running containers individually?

Docker Compose let me define the Flask app and Redis together in one file. I could start and manage both with a few commands instead of setting up each container separately. It also connected them so the app could use Redis to keep track of page visits.
