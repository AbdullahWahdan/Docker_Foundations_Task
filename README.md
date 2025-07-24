# 🐳 Docker Fundamentals Team Project

A collaborative project to explore core Docker concepts including containerization, images, volumes, networks, Compose, and container lifecycle management.

This repo contains all deliverables for a 9-part Docker training lab, managed and executed by a 4-member team.

---

## 📦 Project Structure

Each task is organized into its own folder:

| Task No. | Topic                                | Output File(s)                 |
|----------|--------------------------------------|--------------------------------|
| 1        | VM vs. Container Comparison           | `vm_vs_container.md`           |
| 2        | Namespaces & cgroups Overview         | `namespaces_cgroups.md`        |
| 3        | Docker Install & Daemon Tour          | `docker_info_annotated.md`     |
| 4        | Hello-World Container Demo            | `hello-world.cast`             |
| 5        | Dockerfile Basics                     | `Dockerfile`, image pushed     |
| 6        | Compose Services (web + db)           | `docker-compose.yml`           |
| 7        | Container Lifecycle & Clean-up        | `lifecycle_report.md`          |
| 8        | Recap Slides & Quiz                   | `recap_slides.pptx`, `quiz.md` |
| 9        | Guided Lab Instructions               | `lab_instructions.md`          |

---


## ⚙️ How to Run the Compose App

> Make sure [Docker](https://www.docker.com/products/docker-desktop) is installed.

```bash
# Clone this repo
git clone https://github.com/<your-org>/docker-team-project.git
cd docker-team-project/6_compose_services

# Run the Compose setup
docker-compose up --build

# Tear down
docker-compose down
