# Run the project in a browser-based Codespace

## 1. Open the cloud workspace
Upload/extract the project into a GitHub repository, then create a Codespace from that repository. The project can run in a browser workspace; no local laptop installation is needed if Codespaces is available to you.

## 2. Start the backend
In the Codespaces terminal:

```bash
cd backend
chmod +x mvnw 2>/dev/null || true
./mvnw spring-boot:run
```

If the wrapper is not present/working, try `mvn spring-boot:run`. Wait until the terminal says the server has started.

Open the forwarded port 8080 from the Ports panel. Test:
- `GET /api/items`
- `GET /api/health`

## 3. Start the React frontend
Open a second terminal:

```bash
cd frontend
npm install
npm run dev -- --host 0.0.0.0
```

Open the forwarded port 5173. The frontend uses `/api` through the Vite proxy when both services run in the same Codespace.

## 4. Test CRUD
The page shows items. Use the form to add an item, then refresh. The backend stores records in H2 for the demo. Test endpoints with the browser for GET, or use the built-in frontend form for POST/DELETE.

## 5. Demo JWT
Use a REST client or curl from the terminal:
```bash
curl -X POST http://localhost:8080/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"username":"student","password":"demo123"}'
```
The response includes a demo token. This is a minimal classroom demonstration and is not production-ready. Do not use the demo credentials for real accounts.

## 6. MySQL variant (only if MySQL is actually running)
Set environment variables and activate the MySQL profile:
```bash
SPRING_PROFILES_ACTIVE=mysql \
DB_URL='jdbc:mysql://localhost:3306/trash2tech' \
DB_USER='root' \
DB_PASSWORD='your-local-password' \
./mvnw spring-boot:run
```
Create the database first: `CREATE DATABASE trash2tech;`. A database server must be reachable; changing the profile alone does not install or start MySQL.

## 7. Submission evidence
Take screenshots of:
- React SPA in browser
- `/api/items` JSON response
- successful create/delete operation
- login endpoint returning a token
- GitHub repository and README
- deployed URLs only if you actually deploy them

Do not claim MySQL or public deployment works unless you have tested it.
