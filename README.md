# Property Lookup

A full-stack mobile application for searching property information by owner name. This repository contains both the backend API and mobile client source code.

---

## Contents

- **backend/**: Node.js + Express API with PostgreSQL database integration
- **mobile/**: React Native mobile application
- **scripts/**: Data ingestion and maintenance scripts
- **.github/**: CI/CD workflows for GitHub Actions

---

## Getting Started

Follow these steps to run the project locally.

### Prerequisites

- [Node.js](https://nodejs.org/) v18+
- [Docker](https://www.docker.com/) (for PostgreSQL)
- [Yarn](https://yarnpkg.com/) or npm

### Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/property-lookup.git
cd property-lookup
```

### Environment Variables

Create a `.env` file in the root:

```dotenv
# .env
DATABASE_URL=postgres://user:pass@localhost:5432/propertydb
PORT=3000
```

### Run the Backend

```bash
cd backend
yarn install    # or npm install
# Start PostgreSQL with Docker:
docker run --name prop-db -e POSTGRES_USER=user -e POSTGRES_PASSWORD=pass \
  -e POSTGRES_DB=propertydb -p 5432:5432 -d postgres:15

yarn start      # or npm start
```

### Load Initial Data

```bash
cd scripts
node load-parcels.js data/parcels.csv
```

### Run the Mobile App

```bash
cd mobile
yarn install
npx react-native run-android  # or run-ios
```

## Project Structure

```
property-lookup/
├─ backend/
│  ├─ src/
│  │  ├─ controllers/
│  │  ├─ models/
│  │  ├─ routes/
│  │  └─ index.js
│  ├─ scripts/
│  ├─ tests/
│  └─ package.json
├─ mobile/
│  ├─ src/
│  └─ package.json
├─ data/
│  └─ parcels.csv
├─ .github/workflows/ci.yml
├─ .gitignore
└─ README.md
```

## Contributing

Contributions are welcome! Please open issues or pull requests against the `main` branch.


