```markdown
SkillSync

SkillSync is a real-world platform designed to help organizations manage, assess, and visualize employee skills, certifications, and team readiness. It enables team leads and HR managers to identify gaps, build efficient teams, and make informed staffing decisions.

Tech Stack

Backend
- Golang 1.22
- PostgreSQL
- Hasura GraphQL Engine
- go-graphql-client
- JWT Authentication

Frontend
- Vue 3 with Nuxt 3
- Vite
- Apollo Client
- VeeValidate
- Tailwind CSS

DevOps
- Docker and Docker Compose

Features

- Secure authentication with JWT
- Role-based access (Admin, Manager, Employee)
- Skill profile management
- Certification uploads
- Team creation and member assignment
- Skill gap analysis and search
- GraphQL API with Hasura
- Real-time updates using GraphQL subscriptions
- Fully responsive frontend

## Project Structure

```

/backend
/auth-server
/frontend
/nuxt-app
/hasura
/migrations
/metadata
docker-compose.yml
.env.example

```

Getting Started

Prerequisites

- Docker
- Docker Compose
- Go 1.22
- Node.js v18+

Setup

```
git clone https://github.com/yourusername/skillsync.git
cd skillsync
cp .env.example .env
docker-compose up --build
```

Services

| Service        | URL                                            |
| -------------- | ---------------------------------------------- |
| Frontend       | [http://localhost:3000](http://localhost:3000) |
| Hasura Console | [http://localhost:8080](http://localhost:8080) |
| Auth Server    | [http://localhost:5000](http://localhost:5000) |
| Postgres       | localhost:5432                                 |

Authentication Flow

1. User logs in through the frontend
2. Credentials sent to Go auth server
3. Server validates and issues JWT
4. Frontend stores token and attaches it to GraphQL requests
5. Hasura applies permissions based on the token

Database Schema

```
users(id, name, email, role)
skills(id, name, category)
user_skills(id, user_id, skill_id, proficiency, years_experience)
teams(id, name, manager_id)
team_members(team_id, user_id)
certifications(id, user_id, name, url, issued_at)
```

Testing

```
cd backend/auth-server
go test ./...

cd frontend/nuxt-app
yarn test
```

Deployment

SkillSync can be deployed on any Docker-compatible platform.

