# Docker Syllabus

A complete, structured learning path for Docker — from running your first container to building images, composing multi-service apps, securing supply chains, and shipping production-ready container workflows.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 6-10 Weeks](https://img.shields.io/badge/Duration-6--10%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![Docker: Engine + Compose](https://img.shields.io/badge/Docker-Engine%20%2B%20Compose-2496ED)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: Images, Containers & Lifecycle](#phase-2-images-containers--lifecycle)
- [Phase 3: Dockerfiles & Image Builds](#phase-3-dockerfiles--image-builds)
- [Phase 4: Volumes, Networks & Environment Management](#phase-4-volumes-networks--environment-management)
- [Phase 5: Docker Compose](#phase-5-docker-compose)
- [Phase 6: Development Workflows & Build Optimization](#phase-6-development-workflows--build-optimization)
- [Phase 7: Registries, Image Publishing & CI](#phase-7-registries-image-publishing--ci)
- [Phase 8: Security & Supply Chain Basics](#phase-8-security--supply-chain-basics)
- [Phase 9: Debugging, Observability & Performance](#phase-9-debugging-observability--performance)
- [Phase 10: Production Patterns & Orchestration Readiness](#phase-10-production-patterns--orchestration-readiness)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> Docker is easiest to learn if you already understand the basics of the command line, processes, filesystems, ports, and environment variables. You do **not** need Kubernetes first. In fact, you should not touch Kubernetes until Docker basics are solid.

- Basic command line / terminal usage
- A development machine with Docker installed
- Familiarity with at least one programming language or web stack
- Curiosity about how apps run outside your local machine

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Understand what containers are and how Docker fits into development workflows.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is Docker | A platform for packaging and running applications in isolated containers |
| 2 | Container vs VM | Containers share the host kernel, VMs emulate full machines |
| 3 | Docker Architecture | Docker Engine, CLI, images, containers, registries |
| 4 | Installation | Docker Desktop vs Docker Engine and verifying setup |
| 5 | First Container | `docker run hello-world` and what it proves |
| 6 | Container Fundamentals | Isolation, portability, reproducibility, ephemeral processes |
| 7 | Docker Use Cases | Local development, CI, packaging, deployment, background jobs |

> [!TIP]
> Learn Docker by running real containers immediately. The core ideas become much clearer once you inspect a live container instead of only reading definitions.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install Docker and run your first container
- [ ] Explain the difference between an image and a container
- [ ] Explain container vs virtual machine at a high level

</details>

---

## Phase 2: Images, Containers & Lifecycle

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Learn the commands and mental model behind day-to-day Docker usage.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Pulling Images | `docker pull` and trusted image sources |
| 2 | Running Containers | `docker run`, foreground vs detached mode |
| 3 | Basic Flags | `-p`, `-e`, `-v`, `--name`, `--rm`, `-it` |
| 4 | Inspecting State | `docker ps`, `docker images`, `docker inspect`, `docker logs` |
| 5 | Starting / Stopping | `start`, `stop`, `restart`, `rm`, lifecycle management |
| 6 | Exec into Containers | `docker exec -it` for troubleshooting and debugging |
| 7 | Tags & Versions | Why tags matter and why `latest` is not a strategy |
| 8 | Cleanup | Removing unused containers, images, volumes, networks carefully |

> [!IMPORTANT]
> Containers are disposable runtime instances. If the container disappears, anything stored only inside the writable container layer is gone too.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Run a real service image like Nginx or Postgres
- [ ] View logs and inspect metadata for a running container
- [ ] Explain what disappears when a container is removed

</details>

---

## Phase 3: Dockerfiles & Image Builds

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Learn how to package your own application instead of only running someone else's image.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Dockerfile Basics | `FROM`, `WORKDIR`, `COPY`, `RUN`, `CMD`, `ENTRYPOINT` |
| 2 | Build Context | What gets sent during `docker build` and why `.dockerignore` matters |
| 3 | Layers & Cache | How Docker builds incrementally and when cache invalidates |
| 4 | Base Images | Choosing minimal, trustworthy images |
| 5 | Multi-Stage Builds | Smaller production images with separate build and runtime stages |
| 6 | Environment Variables | `ENV`, build args, and runtime config separation |
| 7 | Exposed Ports | `EXPOSE` vs actual port publishing |
| 8 | Reproducibility | Pinning base versions and deterministic builds |

> [!TIP]
> The first useful Dockerfile habit is ordering steps so expensive dependency installs stay cached when application code changes.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Write a Dockerfile for a small app
- [ ] Use `.dockerignore` to reduce build context
- [ ] Convert a basic Dockerfile into a multi-stage build

</details>

---

## Phase 4: Volumes, Networks & Environment Management

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Learn how containers communicate, store persistent data, and receive configuration.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Bind Mounts | Mapping local files into containers for development |
| 2 | Named Volumes | Persistent container data that survives restarts and replacements |
| 3 | Networks | Bridge networks, service discovery, container-to-container communication |
| 4 | Ports | Internal container ports vs published host ports |
| 5 | Environment Variables | Runtime configuration and secrets awareness |
| 6 | Health Checks | Detecting when services are actually ready |
| 7 | One Process / One Concern | Designing containers around clean responsibilities |
| 8 | Stateful vs Stateless Containers | What should and should not live in the container filesystem |

> [!CAUTION]
> Treat container filesystems as ephemeral unless the data is explicitly stored in a volume or external service.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Persist database data with a named volume
- [ ] Connect two containers on a custom network
- [ ] Explain bind mounts vs named volumes

</details>

---

## Phase 5: Docker Compose

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Coordinate multiple services in one repeatable local environment.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Compose File Basics | Services, images, build, ports, volumes, networks |
| 2 | Multi-Service Stacks | App + database + cache + worker style setups |
| 3 | Dependency Ordering | Startup race conditions and health-aware readiness |
| 4 | Compose Commands | `docker compose up`, `down`, `logs`, `exec`, `ps` |
| 5 | Override Files | Environment-specific Compose setups |
| 6 | Profiles | Optional services for dev/test workflows |
| 7 | Named Volumes in Compose | Persistent data in team-shared dev environments |
| 8 | Compose for Teams | Reproducible onboarding and local parity |

> [!IMPORTANT]
> Compose is where Docker becomes genuinely useful for application development. A good Compose setup can remove hours of setup friction from every new developer.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Run a multi-service application with Compose
- [ ] Add a health check or dependency strategy
- [ ] Explain why Compose improves local development consistency

</details>

---

## Phase 6: Development Workflows & Build Optimization

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Make Docker practical for iterative day-to-day development.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Live Reload Patterns | Bind mounts, watch mode, containerized dev servers |
| 2 | Dependency Caching | Structuring builds for faster feedback |
| 3 | BuildKit | Modern Docker build features and performance improvements |
| 4 | Dev vs Prod Images | Different goals for local iteration and deployed runtime |
| 5 | Multi-Platform Builds | Building for different CPU architectures |
| 6 | Layer Hygiene | Avoiding bloated images and accidental cache busting |
| 7 | Image Size Reduction | Smaller bases, multi-stage builds, fewer packages |
| 8 | Repeatable Tooling | Using containers for CLI tools and ephemeral tasks |

> [!TIP]
> The best Docker workflow is the one that developers will actually keep using. Fast rebuilds and clear config matter more than clever container tricks.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Speed up a slow image build
- [ ] Separate development and production build concerns
- [ ] Explain what BuildKit changes about builds

</details>

---

## Phase 7: Registries, Image Publishing & CI

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Learn how images move through a real delivery pipeline.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Registries | Docker Hub, private registries, organizational image storage |
| 2 | Tagging Strategy | Semantic tags, environment tags, immutable references |
| 3 | Push / Pull Workflows | Publishing built images and consuming them elsewhere |
| 4 | CI Integration | Building and testing images in GitHub Actions or similar CI |
| 5 | Cache in CI | Faster pipeline builds without sacrificing correctness |
| 6 | Metadata & Labels | Adding useful image metadata and provenance |
| 7 | Release Automation | Build once, tag once, promote safely |
| 8 | Artifact Discipline | Treating images as deployment artifacts, not ad hoc outputs |

> [!IMPORTANT]
> If tags are mutable and undocumented, deployments become ambiguous. Treat image naming and tagging as part of your release process, not an afterthought.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Build and push an image to a registry
- [ ] Design a tagging strategy that supports rollback
- [ ] Add an image build step to CI

</details>

---

## Phase 8: Security & Supply Chain Basics

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Learn how to reduce risk in containerized systems.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Trusted Base Images | Official images, publisher trust, update discipline |
| 2 | Minimal Images | Smaller attack surface and fewer dependencies |
| 3 | Non-Root Containers | Running processes with reduced privileges |
| 4 | Secret Handling | Keeping secrets out of Dockerfiles and images |
| 5 | Vulnerability Scanning | Detecting risky packages and outdated layers |
| 6 | SBOM / Provenance Concepts | Knowing what is inside an image and where it came from |
| 7 | Patch Strategy | Rebuild frequency and dependency refresh habits |
| 8 | Runtime Hardening | Capabilities, read-only filesystems, network restrictions |

> [!WARNING]
> Baking secrets into images is one of the fastest ways to create a long-lived security problem. If it lands in the image, assume it will leak eventually.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Run a container as a non-root user
- [ ] Explain why smaller base images are safer
- [ ] Identify one unsafe secret-handling pattern and replace it

</details>

---

## Phase 9: Debugging, Observability & Performance

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Diagnose problems when containers do not behave the way you expect.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Logs | Container logs, stream following, and log routing basics |
| 2 | Shell Debugging | `docker exec`, temporary tools, inspecting the filesystem |
| 3 | Resource Limits | CPU, memory, OOM kills, and contention |
| 4 | Health & Readiness | Distinguishing "running" from "actually healthy" |
| 5 | Startup Failures | Dependency timing, bad env vars, wrong entrypoints |
| 6 | Network Debugging | Ports, DNS, service names, reachability inside Compose networks |
| 7 | Image Analysis | Layer inspection and size debugging |
| 8 | Container Performance | Avoiding unnecessary rebuilds and oversized runtimes |

> [!TIP]
> When debugging Docker problems, determine first whether the issue is build-time, startup-time, runtime config, networking, or application code. That classification saves a lot of wasted effort.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Debug a failing container startup
- [ ] Inspect logs and environment configuration
- [ ] Diagnose a container networking issue in a multi-service stack

</details>

---

## Phase 10: Production Patterns & Orchestration Readiness

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 8-10 Hours](https://img.shields.io/badge/Time-8--10%20Hours-yellow)

> Use Docker as a solid foundation for deployment and platform thinking.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Stateless App Design | Twelve-factor style thinking and replaceable containers |
| 2 | Horizontal Scaling Concepts | Replicas, load balancing, and service separation |
| 3 | Reverse Proxies & TLS | Where ingress fits around containers |
| 4 | Background Workers | Separating web, jobs, schedulers, and queues |
| 5 | Data Services | Handling databases and state outside app containers responsibly |
| 6 | Deployment Patterns | Blue/green, rolling updates, image promotion strategies |
| 7 | Compose vs Orchestrators | Knowing when Docker alone is enough and when it isn't |
| 8 | Kubernetes Readiness | What knowledge transfers and what new complexity appears |

> [!TIP]
> Docker is not a deployment strategy by itself. It is a packaging and runtime primitive. Production success still depends on architecture, networking, secrets, storage, and rollout design.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Describe a production deployment architecture using containers
- [ ] Explain where Docker ends and orchestration begins
- [ ] Design a containerized system with separate app, worker, and database responsibilities

</details>

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Treating a container like a VM | Leads to bad process, state, and config assumptions | Treat containers as isolated, disposable processes |
| 2 | Storing important data inside the container filesystem | Data disappears when containers are recreated | Use volumes or external services |
| 3 | Using huge base images casually | More vulnerabilities, slower pulls, slower builds | Start with minimal, appropriate base images |
| 4 | Skipping `.dockerignore` | Build context becomes slow and leaks junk into builds | Exclude unnecessary files deliberately |
| 5 | Putting secrets in Dockerfiles | Secrets get baked into image layers | Inject secrets at runtime or through secure tooling |
| 6 | Running everything as root | Expands blast radius for security issues | Use non-root users when possible |
| 7 | Blindly using `latest` tags | Builds and deployments become non-deterministic | Pin versions and document upgrade policy |
| 8 | Building one giant container for the whole stack | Hard to scale, debug, and update | Split app, DB, cache, and workers into separate services |
| 9 | Ignoring health checks | Containers appear "up" when the app is not actually ready | Add readiness and health logic where appropriate |
| 10 | Optimizing image size before understanding the workflow | Can hurt iteration speed without real value | Fix correctness first, then optimize intentionally |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is the difference between an image and a container?**
   - An image is a packaged template. A container is a running instance of that image.

2. **How is a container different from a virtual machine?**
   - Containers share the host OS kernel and are lighter. VMs emulate an entire machine and carry their own guest OS.

3. **Why are containers useful in development?**
   - They make environments reproducible, reduce setup drift, and package dependencies consistently.

4. **What is a Dockerfile?**
   - A text file of instructions used to build an image.

5. **What is Docker Compose used for?**
   - It defines and runs multi-container applications like app + database + cache stacks.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **Why use multi-stage builds?**
   - They separate build-time tooling from runtime output, resulting in smaller and cleaner production images.

2. **What is the difference between a bind mount and a named volume?**
   - A bind mount maps a host path directly. A named volume is managed by Docker and is typically better for persistent service data.

3. **Why shouldn't you rely on the `latest` tag?**
   - It is mutable and ambiguous, which makes builds and deployments harder to reproduce and roll back.

4. **How do containers communicate with each other in Compose?**
   - They share a Docker network and can resolve each other by service name.

5. **What makes an image build slow?**
   - Large build contexts, cache invalidation, heavy dependency installs, poor Dockerfile ordering, and oversized base images.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **How do you improve container supply-chain security?**
   - Use trusted base images, pin versions, scan for vulnerabilities, rebuild regularly, avoid secret leakage, and track image provenance.

2. **How do you debug a container that exits immediately?**
   - Inspect logs, check the entrypoint and command, validate environment configuration, and reproduce with an interactive shell or a simplified startup command.

3. **When is Docker Compose not enough in production?**
   - When you need robust scheduling, service discovery at scale, advanced rollout strategies, and cluster-level orchestration across many hosts.

4. **Why run processes as non-root in containers?**
   - It reduces privilege and limits the blast radius if the application or image is compromised.

5. **What does good production container design look like?**
   - Small focused images, clear service boundaries, externalized state, secure config, observable runtime behavior, and reproducible builds.

</details>

---

## Practice Projects

### Project 1: Run Off-the-Shelf Services
![Phase 1-2](https://img.shields.io/badge/After-Phase%201--2-green)

**What you'll build:** A local environment using ready-made Nginx, Redis, or Postgres images.

**Skills practiced:** `docker run`, ports, logs, inspection, lifecycle commands.

---

### Project 2: Containerize a Real App
![Phase 3-4](https://img.shields.io/badge/After-Phase%203--4-yellow)

**What you'll build:** A Dockerfile for a small web app or API, including env vars and persistent storage.

**Skills practiced:** Dockerfiles, volumes, networks, config management.

---

### Project 3: Multi-Service Compose Stack
![Phase 5-6](https://img.shields.io/badge/After-Phase%205--6-yellow)

**What you'll build:** A full local stack with app, database, cache, and optional worker using Compose.

**Skills practiced:** Compose, health checks, development workflows, build optimization.

---

### Project 4: Registry + CI Pipeline
![Phase 7-8](https://img.shields.io/badge/After-Phase%207--8-orange)

**What you'll build:** A pipeline that builds, scans, tags, and pushes an image automatically.

**Skills practiced:** Registries, CI, tagging, security basics.

---

### Project 5: Production-Style Container Platform
![Phase 9-10](https://img.shields.io/badge/After-Phase%209--10-red)

**What you'll build:** A production-minded architecture document and runnable stack with monitoring, rollout strategy, and security constraints.

**Skills practiced:** Everything from all phases — your Docker graduation project.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [Docker Get Started](https://docs.docker.com/get-started/) | Official learning path for Docker fundamentals |
| [Docker Workshop](https://docs.docker.com/get-started/workshop/) | Hands-on official tutorial from first concepts to Compose |
| [Docker Build](https://docs.docker.com/build/) | Official build system docs including BuildKit and multi-platform images |
| [Docker Compose Quickstart](https://docs.docker.com/compose/gettingstarted/) | Best official Compose entry point |
| [Dockerfile Best Practices](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/) | High-signal guidance on building safe, lean images |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [Play with Docker](https://labs.play-with-docker.com/) | Browser-based Docker environment for instant practice |
| [Docker Workshop](https://docs.docker.com/get-started/workshop/) | Guided official hands-on path |
| [KillerCoda Docker Labs](https://killercoda.com/) | Interactive terminal labs for Docker scenarios |

### Video / Channels

| Video / Channel | Why Watch |
|----------------|-----------|
| [Docker](https://www.youtube.com/@Docker) | Official updates, demos, and ecosystem walkthroughs |
| [TechWorld with Nana](https://www.youtube.com/@TechWorldwithNana) | Clear DevOps and Docker explanations |
| [freeCodeCamp](https://www.youtube.com/@freecodecamp) | Long-form free Docker and DevOps courses |

### Tools & Extensions

| Tool | Why You Need It |
|------|----------------|
| [Docker Desktop](https://www.docker.com/products/docker-desktop/) | Easiest local Docker setup on desktop operating systems |
| [Docker VS Code Extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker) | Container, image, and Compose support in VS Code |
| [Dive](https://github.com/wagoodman/dive) | Inspect image layers and wasted space |
| [Hadolint](https://github.com/hadolint/hadolint) | Lint Dockerfiles for common issues |
| [Docker Scout](https://docs.docker.com/scout/) | Security and image analysis tooling from Docker |

### Further Reading

| Resource | Format |
|----------|--------|
| [Docker Introduction](https://docs.docker.com/get-started/introduction/) | Official conceptual introduction |
| [Docker Compose Concepts](https://docs.docker.com/get-started/docker-concepts/the-basics/what-is-docker-compose/) | Focused explanation of why Compose exists |

---

[Back to Main Syllabus](../README.md)
