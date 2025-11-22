# Grocery-Delivery-Application

Monorepo containing backend (Node + Express + TypeScript) and mobile (Expo + React Native + TypeScript).

What's included
Backend: auth, products, uploads, orders, Stripe payments, FCM push notifications, Dockerfile, docker-compose.
Mobile: Expo app with Auth context, product screens, and instructions to setup push notifications.
Quick start (local)
Backend
Copy .env.example to .env and fill values:
PORT=5000
MONGO_URI=your_mongo_uri
JWT_SECRET=supersecret123
FIREBASE_PROJECT_ID=your-firebase-project
FIREBASE_PRIVATE_KEY="-----BEGIN PRIVATE KEY-----\nYOUR_KEY\n-----END PRIVATE KEY-----\n"
FIREBASE_CLIENT_EMAIL=xxxxx@your-project.iam.gserviceaccount.com
STRIPE_SECRET=sk_test_xxx
STRIPE_WEBHOOK_SECRET=whsec_xxx
Install & run:
cd backend
npm install
npm run dev
Mobile (Expo)
Open mobile and install deps:
cd mobile
npm install
npx expo start
Edit mobile/src/context/AuthContext.tsx API_URL to point to your machine (e.g. http://192.168.1.100:5000).
Docker (backend)
cd backend
docker-compose up --build
This starts backend + a local mongo service.

Push to GitHub (automated)
There is a helper script backend/create_github_repo.sh that uses the GH CLI. You must set GITHUB_TOKEN env var and have gh installed:

cd backend
export GITHUB_TOKEN=ghp_xxx
bash create_github_repo.sh my-grocery-repo
Notes
The repo includes example webhook and FCM usage. Configure Stripe webhook and Firebase service account in env.
For push notifications with Expo, follow Expo docs to configure credentials and use expo-notifications.
GroceryDeliveryApp
