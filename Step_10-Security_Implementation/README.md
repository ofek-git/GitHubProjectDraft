# 🔐 Security Implementation – Secret Management

A critical aspect of modern application security is the proper handling of sensitive information such as database credentials, API keys, and authentication tokens. Instead of hardcoding these values in source code or embedding them into container images, they should be managed securely using a Secret Manager.

---

## 📌 Why Secret Management?

- Prevents exposing credentials in Git repositories.

- Reduces risk if containers/images are leaked.

- Provides central management and rotation of secrets.

## 🚀 Implementation



### 1. Define Secrets

For example, store your MongoDB connection string and JWT secret key in a secret manager.

Example with Docker Secrets:
```bash
create a secret from a local file

echo "mongodb://user:password@cluster-url/dbname" | docker secret create mongodb_uri -
echo "mySuperJWTsecret" | docker secret create jwt_secret -
```
Example with Kubernetes Secrets:
```bash
kubectl create secret generic app-secrets \
  --from-literal=MONGO_URI="mongodb://user:password@cluster-url/dbname" \
  --from-literal=JWT_SECRET="mySuperJWTsecret"
```
### 2. Use Secrets in the App
Docker (docker-compose.yml)
```yaml
version: "3.8"
services:
  app:
    image: myapp:latest
    secrets:
      - mongodb_uri
      - jwt_secret

secrets:
  mongodb_uri:
    external: true
  jwt_secret:
    external: true
```

Inside your app code, read them from environment variables or mounted files. Example (Node.js):
```js
const mongoUri = process.env.MONGO_URI || "/run/secrets/mongodb_uri";
const jwtSecret = process.env.JWT_SECRET || "/run/secrets/jwt_secret";
```
Kubernetes (deployment.yaml)
```yaml
env:
  - name: MONGO_URI
    valueFrom:
      secretKeyRef:
        name: app-secrets
        key: MONGO_URI
  - name: JWT_SECRET
    valueFrom:
      secretKeyRef:
        name: app-secrets
        key: JWT_SECRET
```
### 3. CI/CD Integration

In your CI/CD pipeline (GitHub Actions, GitLab CI, etc.), use environment secrets instead of plaintext values.

GitHub Actions example:
```yaml
env:
  MONGO_URI: ${{ secrets.MONGO_URI }}
  JWT_SECRET: ${{ secrets.JWT_SECRET }}
```
