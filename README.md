# 🍳 AI Recipe Generator

An intelligent full-stack recipe generation app powered by Google Gemini AI. Add ingredients from your pantry and get personalized, detailed recipes instantly — complete with nutrition info, cooking tips, and meal planning features.

![License](https://img.shields.io/badge/license-MIT-green)
![Node](https://img.shields.io/badge/node-%3E%3D18.0.0-brightgreen)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-blue)
![React](https://img.shields.io/badge/React-18-61DAFB)

---

## ✨ Features

- 🤖 **AI Recipe Generation** — Generate detailed recipes using Google Gemini AI based on available ingredients
- 🥗 **Pantry Management** — Track your pantry items and get notified about expiring ingredients
- 📅 **Meal Planning** — Plan your weekly meals with an interactive calendar
- 🛒 **Shopping List** — Auto-generate shopping lists from your meal plans
- 🔐 **Authentication** — Secure JWT-based user authentication
- 📊 **Nutrition Info** — Detailed nutritional breakdown for every recipe
- 💡 **Cooking Tips** — AI-generated tips to make every dish better

---

## 🛠️ Tech Stack

### Frontend
- **React 18** — UI library
- **Vite** — Build tool
- **Axios** — HTTP client
- **React Router** — Client-side routing

### Backend
- **Node.js** — Runtime environment
- **Express.js** — Web framework
- **JWT** — Authentication
- **Google Gemini AI** (`@google/genai`) — Recipe generation

### Database
- **PostgreSQL** — Relational database (hosted on Neon)

### Deployment
- **Render** — Backend and frontend hosting
- **Neon** — Managed PostgreSQL database

---

## 📁 Project Structure

```
AI-Recipe-Generator/
├── backend/
│   ├── config/
│   │   └── schema.sql          # Database schema
│   ├── controllers/            # Route controllers
│   ├── routes/                 # API routes
│   │   ├── auth.js
│   │   ├── users.js
│   │   ├── pantry.js
│   │   ├── recipes.js
│   │   ├── mealPlans.js
│   │   └── shoppingList.js
│   ├── utils/
│   │   └── gemini.js           # Gemini AI integration
│   ├── db.js                   # Database connection
│   ├── migrate.js              # Database migrations
│   └── index.js                # Entry point
│
└── frontend/
    └── ai-recipe-generator/
        ├── src/
        │   ├── api/            # Axios config
        │   ├── components/     # Reusable components
        │   ├── pages/          # Page components
        │   └── main.jsx
        ├── .env
        └── vite.config.js
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js >= 18
- PostgreSQL or a [Neon](https://neon.tech) account
- [Google Gemini API key](https://aistudio.google.com/app/apikey)

### 1. Clone the repository

```bash
git clone https://github.com/muazkhan72/AI-Recipe-Generator.git
cd AI-Recipe-Generator
```

### 2. Setup the backend

```bash
cd backend
npm install
```

Create a `.env` file in the `backend/` folder:

```env
DATABASE_URL=your_neon_postgresql_connection_string
GEMINI_API_KEY=your_google_gemini_api_key
JWT_SECRET=your_jwt_secret_key
NODE_ENV=development
PORT=8000
```

Run database migrations:

```bash
node migrate.js
```

Start the backend server:

```bash
npm run dev
```

### 3. Setup the frontend

```bash
cd frontend/ai-recipe-generator
npm install
```

Create a `.env` file in the frontend folder:

```env
VITE_API_URL=http://localhost:8000/api
```

Start the frontend:

```bash
npm run dev
```

The app will be running at `http://localhost:5173`

---

## 🌐 API Endpoints

### Auth
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | Register a new user |
| POST | `/api/auth/login` | Login and get JWT token |

### Recipes
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/recipes/generate` | Generate a recipe using AI |
| GET | `/api/recipes` | Get all saved recipes |
| DELETE | `/api/recipes/:id` | Delete a recipe |

### Pantry
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/pantry` | Get pantry items |
| POST | `/api/pantry` | Add a pantry item |
| PUT | `/api/pantry/:id` | Update a pantry item |
| DELETE | `/api/pantry/:id` | Delete a pantry item |

### Meal Plans
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/meal-plans` | Get meal plans |
| POST | `/api/meal-plans` | Create a meal plan |
| DELETE | `/api/meal-plans/:id` | Delete a meal plan |

### Shopping List
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/shopping-list` | Get shopping list items |
| POST | `/api/shopping-list` | Add item to shopping list |
| DELETE | `/api/shopping-list/:id` | Remove item |

---

## ☁️ Deployment

This project is deployed on **Render** with the following setup:

| Service | Type | Platform |
|---------|------|----------|
| Backend | Web Service | Render |
| Frontend | Static Site | Render |
| Database | PostgreSQL | Neon |

### Backend Environment Variables (Render)

```
DATABASE_URL       = your_neon_connection_string
GEMINI_API_KEY     = your_gemini_api_key
JWT_SECRET         = your_jwt_secret
NODE_ENV           = production
PORT               = 8000
CLIENT_URL         = https://your-frontend.onrender.com
```

### Frontend Environment Variables (Render)

```
VITE_API_URL = https://your-backend.onrender.com/api
```

> **Note:** After adding frontend env variables on Render, trigger a manual redeploy — Vite bakes env vars at build time.

---

## 🗄️ Database Schema

The app uses the following tables:

- `users` — User accounts
- `user_preferences` — Dietary preferences per user
- `pantry_items` — Pantry inventory per user
- `recipes` — Saved recipes
- `recipe_ingredients` — Ingredients per recipe
- `recipe_nutrition` — Nutritional info per recipe
- `meal_plans` — Weekly meal plans
- `shopping_lists_items` — Shopping list entries

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m "Add your feature"`
4. Push to the branch: `git push origin feature/your-feature`
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Muaz Khan**
- GitHub: [@muazkhan72](https://github.com/muazkhan72)

---

> Built with ❤️ using the PERN stack and Google Gemini AI
