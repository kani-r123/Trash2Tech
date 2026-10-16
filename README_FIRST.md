# Trash2Tech — ready-made practical starter

This project is intended to reduce typing and let you reuse one project for:
- Experiment 5: Spring Boot + JPA database operations
- Experiment 6: basic JWT login demonstration
- Experiment 7: React frontend calling Spring Boot
- Experiment 8: Docker/GitHub deployment preparation
- Assignment A1: portfolio + CRUD API
- Assignment A2: registration/login + JPA/JWT starter
- Assignment A3: React SPA
- Assignment A4: integrated full-stack deployment preparation

## Important honesty note
This is a starter/demo, not a guarantee that every requirement is complete for every teacher's rubric. It uses H2 by default so it can run without a separately installed database. The MySQL profile is included, but MySQL requires a running MySQL server and credentials. JWT code is a learning/demo implementation; do not use it as production authentication without review.

## Browser-only route
1. Open GitHub in your browser and create a new repository named `Trash2Tech`.
2. Upload the contents of this ZIP (extract it first).
3. Open the repository and choose `Code` -> `Codespaces` -> `Create codespace on main` if your account offers Codespaces.
4. In the Codespaces terminal, follow the commands in `RUN_IN_CODESPACES.md`.
5. If Codespaces is not available on your account, use a college computer/lab with Java 17, Maven, and Node.js installed, or ask your group member to run the backend and share screenshots/output.

## Project structure
- `backend/` Spring Boot REST API, CRUD, H2/JPA and a demo JWT endpoint
- `frontend/` React SPA calling the API
- `RUN_IN_CODESPACES.md` execution guide
- `Dockerfile` backend container starter
