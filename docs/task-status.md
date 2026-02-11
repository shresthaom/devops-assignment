# Task Status and Work Breakdown

This document tracks the implementation progress for the Plantura Experience Day deployment, structured using MoSCoW prioritization. Tasks are ordered to reflect the recommended execution sequence.

---

## Must Have Tasks (Core Deliverables)

These tasks are required for a functional, demo-ready deployment.

Status legend:
- [ ] Not started
- [x] Completed
- [~] In progress

1. Repository and documentation setup
   - [x] Clone provided GitHub repository
   - [x] Create docs directory
   - [x] Create deployment plan document
   - [x] Create task status document

2. Application containerization
   - [ ] Create Backend Dockerfile using Node.js 22
   - [ ] Create Frontend Dockerfile with multi-stage build
   - [ ] Validate container builds locally

3. Docker Compose orchestration
   - [ ] Define services for frontend, backend, and MongoDB
   - [ ] Configure private bridge network
   - [ ] Expose required ports only
   - [ ] Enable single-command startup using docker compose up

4. Configuration and connectivity
   - [ ] Define environment variables for backend configuration
   - [ ] Configure MongoDB connection via environment variables
   - [ ] Exclude .env file from version control

5. Basic observability
   - [ ] Implement backend /health endpoint
   - [ ] Verify health endpoint via container networking

---

## Should Have Tasks (Operational Quality)

These tasks improve reliability and operational clarity.

1. Self-healing and recovery
   - [ ] Configure Docker restart policies for all services
   - [ ] Validate container auto-restart on failure

2. Dependency management
   - [ ] Add MongoDB health check
   - [ ] Gate backend startup on database readiness

3. Logging
   - [ ] Ensure backend logs are written to stdout/stderr
   - [ ] Verify logs via docker compose logs

---

## Could Have Tasks (Bonus Enhancements)

These tasks are optional and implemented only if time permits.

1. Routing and access
   - [ ] Introduce Nginx reverse proxy for unified entry point
   - [ ] Simplify frontend-to-backend routing

2. Data persistence
   - [ ] Configure Docker volume for MongoDB data
   - [ ] Validate data persistence across container restarts

3. Resilience validation
   - [ ] Manually stop backend container
   - [ ] Observe and document restart behavior
   - [ ] Capture findings for documentation

---

## Won’t Have Tasks (Out of Scope)

The following are intentionally excluded for this exercise.

- Multiple environments such as dev, qa, or prod
- CI/CD pipelines or GitHub Actions
- Automated testing frameworks
- Kubernetes or advanced orchestration
- Advanced monitoring or alerting stacks
- Production-grade authentication, authorization, or TLS

---


