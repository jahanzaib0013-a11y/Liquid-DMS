# Full Auth — Express Authentication API

A production-style authentication backend built with **Express**, **MongoDB (Mongoose)** and **JWT**. It implements the full account lifecycle — registration with email verification, login, logout, protected routes and role-based access — with a clean, layered folder structure.

## Features

- Register / login / logout with **JWT access + refresh tokens** (httpOnly cookies)
- **Email verification** and password reset flows (Nodemailer templates)
- **Role-based access control** with route guards
- Password hashing with **bcrypt**
- Centralized **error handler**, **request validation** (Joi) and **auth** middleware
- Layered architecture: `routes → controllers → models` with `middlewares`, `validations`, `utils`

## Tech Stack

| Layer    | Choice                             |
| -------- | ---------------------------------- |
| Runtime  | Node.js + Express                  |
| Database | MongoDB (Mongoose ODM)             |
| Auth     | JWT (jsonwebtoken), bcrypt         |
| Mail     | Nodemailer                         |
| Validation | Joi                              |

## Getting Started

```bash
git clone <your-repo-url>
cd full-auth
npm install
```

Create a `.env`:

```
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/fullauth
JWT_SECRET=change_me
JWT_REFRESH_SECRET=change_me_refresh
EMAIL_HOST=smtp.example.com
EMAIL_USER=you@example.com
EMAIL_PASS=app_password
CLIENT_URL=http://localhost:3000
```

Run:

```bash
npm run dev      # nodemon
npm start        # production
```

## Project Structure

```
src/
  app.js
  routes/         # auth routes + index router
  controllers/    # auth controller logic
  models/         # Mongoose schemas (mongodb)
  middlewares/    # authentication, errorHandler, requestValidator
  validations/    # request validation
  emailTemplates/ # verification / reset emails
  libs/ utils/ constants/ schemas/
```

## Security Note

This project was hardened against the npm supply-chain typosquatting wave (Sept 2026): a malicious `http` package was identified and removed in favour of Node's built-in equivalent. See the commit history for the remediation.

## Author

Jahanzaib Iftikhar
