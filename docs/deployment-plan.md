# Deployment Plan – Plantura Experience Day

## 1. Overview
The goal of this deployment is to provide a containerized, operationally reliable environment for the provided Node.js application. The approach emphasizes simplicity, clarity, and production-inspired practices while remaining appropriate for a time-boxed experience-day exercise.

The solution is designed to be easy to run, easy to reason about, and easy to demonstrate for Dev, QA, and Product stakeholders.

## 2. Proposed Architecture
A simple three-tier containerized architecture will be implemented using Docker Compose:

- Frontend: Static assets served via Nginx built from a Node.js 22 build stage.
- Backend: Node.js 22 REST API service.
- Database: MongoDB running as a stateful container.

All services will communicate over an isolated Docker bridge network, with only the required endpoints exposed.

## 3. MoSCoW Prioritization

### Must Have (Core Deliverables)
Essential capabilities required for a functional and production-inspired deployment.

- Containerization using multi-stage Docker builds for both Backend and Frontend.
- Orchestration using a single-command startup via docker compose up.
- Connectivity through a private container network for secure Backend-to-Database communication.
- Configuration using environment-based values following 12-Factor App principles with .env files.
- Observability via a lightweight /health endpoint on the Backend for service validation.

### Should Have (Operational Quality)
Improvements that enhance reliability and operational clarity without significantly increasing complexity.

- Container-level recovery using Docker restart policies such as unless-stopped.
- Backend startup gated on MongoDB service health.
- Centralized application logs via standard output and error streams managed by Docker.

### Could Have (Bonus Enhancements)
Optional enhancements implemented if time allows.

- Nginx acting as a simple reverse proxy for cleaner routing.
- Docker volumes for MongoDB data persistence.
- Manual failure simulation to validate container restart behavior.

### Won’t Have (Explicitly Out of Scope)
Deliberately excluded to keep scope aligned with the experience-day timebox.

- Multiple environments such as dev, qa, or prod, or CI/CD pipelines.
- Kubernetes or advanced container orchestration platforms.
- Automated testing frameworks.
- Advanced monitoring or alerting stacks such as Prometheus or Grafana.
- Production-grade authentication, authorization, or TLS termination.

## 4. Execution Timeline
- Wednesy -Morning: Finalize and commit the deployment plan.
- Wednesday- Afternoon: Implement Dockerfiles and Docker Compose configuration.
- Thursday-Afternoon: Validation, resilience checks, and documentation updates.
- Friday: Demo and technical walkthrough.

