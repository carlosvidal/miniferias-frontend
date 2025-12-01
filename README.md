# Miniferias Frontend

Frontend Web App for Miniferias Live Shopping Platform built with Vue 3, Vite, Tailwind CSS, and Agora SDK.

🔗 **Production**: https://mini.feria.live
📦 **Backend Repository**: https://github.com/carlosvidal/miniferias-backend

---

## 🚀 Features

- 🎨 **Modern UI**: Tailwind CSS with mobile-first design
- 🔐 **Authentication**: Login, Register, Password Reset
- 📺 **Live Streaming**: Agora SDK integration for real-time video
- 💬 **Real-time Chat**: Supabase Realtime messaging
- 🛒 **Shopping Cart**: Add products, manage cart
- 📦 **Order Management**: Create and track orders
- 👥 **Multi-role Interface**: Admin, Exhibitor, Visitor views
- 📅 **Event Calendar**: Browse and subscribe to events
- 🔔 **Push Notifications**: OneSignal integration
- 🖼️ **Image CDN**: Cloudflare Images optimization
- ⚡ **Performance**: Fast builds and HMR with Vite
- 📱 **Responsive**: Mobile, tablet, and desktop support

---

## 🛠️ Tech Stack

- **Vue 3** - Composition API
- **Vite** - Build tool & dev server
- **Tailwind CSS** - Utility-first styling
- **Pinia** - State management
- **Vue Router** - Client-side routing
- **Agora SDK** - Live streaming
- **Supabase** - Real-time subscriptions
- **Axios** - HTTP client
- **OneSignal** - Push notifications
- **Heroicons** - Icon library

---

## 📋 Prerequisites

- **Node.js** 18+
- **Backend API** running at http://localhost:3000 or deployed

Backend repository: https://github.com/carlosvidal/miniferias-backend

---

## 🛠️ Local Development Setup

### 1. Install dependencies

```bash
npm install
```

### 2. Configure environment variables

Copy `.env.example` to `.env` and configure:

```bash
cp .env.example .env
```

### 3. Update environment variables

```env
# Backend API
VITE_API_URL=http://localhost:3000/api

# Supabase (same as backend)
VITE_SUPABASE_URL=https://xxxxx.supabase.co
VITE_SUPABASE_ANON_KEY=eyJhbGc...

# Agora (same as backend)
VITE_AGORA_APP_ID=xxxxx

# Cloudflare Images (same as backend)
VITE_CLOUDFLARE_IMAGES_ACCOUNT_HASH=xxxxx

# OneSignal (same as backend)
VITE_ONESIGNAL_APP_ID=xxxxx
```

### 4. Start development server

```bash
npm run dev
```

The app will be available at: http://localhost:5173

---

## 🚀 Deployment to Coolify

This repository is configured for **auto-deploy from GitHub** to Coolify (similar to Netlify).

### Quick Deploy

1. **Create Application** in Coolify
   - Type: **Application (Dockerfile)**
   - Repository: `carlosvidal/miniferias-frontend`
   - Branch: `main`
   - Dockerfile: Auto-detected (`Dockerfile`)
   - Port: `80`
   - Domain: `mini.feria.live`

2. **Add Environment Variables**
   - Required: `VITE_API_URL`, `VITE_SUPABASE_URL`, `VITE_SUPABASE_ANON_KEY`, `VITE_AGORA_APP_ID`, `VITE_CLOUDFLARE_IMAGES_ACCOUNT_HASH`, `VITE_ONESIGNAL_APP_ID`
   - Important: Set `VITE_API_URL=https://backend.feria.live/api`

3. **Enable Auto-Deploy**
   - Settings → Deployment → Enable "Deploy on Push"
   - Now every `git push` to `main` will auto-deploy! 🎯

4. **Deploy**
   - Click "Deploy"
   - Wait for build to complete (3-5 minutes)
   - Access your app at: https://mini.feria.live

### Build Configuration

The Dockerfile uses a **multi-stage build**:
1. **Stage 1**: Build the Vue app with Vite
2. **Stage 2**: Serve static files with Nginx

The `nginx.conf` includes:
- SPA routing (fallback to index.html)
- Gzip compression
- Security headers
- Static asset caching

---

## 📦 Build for Production

### Build the app

```bash
npm run build
```

Output directory: `dist/`

### Preview production build locally

```bash
npm run preview
```

---

## Project Structure

```
src/
├── assets/          # Static assets
├── components/      # Reusable components
│   ├── shared/      # Shared components
│   ├── events/      # Event components
│   ├── booths/      # Booth components
│   └── ...
├── composables/     # Vue composables
│   └── useAgora.js  # Agora streaming composable
├── router/          # Vue Router configuration
├── services/        # API services
│   ├── api.js       # Axios instance & API calls
│   └── supabase.js  # Supabase client
├── stores/          # Pinia stores
│   ├── auth.js      # Authentication store
│   ├── events.js    # Events store
│   └── cart.js      # Shopping cart store
├── views/           # Page components
│   ├── auth/        # Login, Register
│   ├── admin/       # Admin views
│   ├── exhibitor/   # Exhibitor views
│   └── ...
├── App.vue          # Root component
└── main.js          # App entry point
```

## Features Implementation Status

### ✅ Implemented
- Authentication (Login/Register)
- Event listing and detail views
- Booth listing
- Shopping cart
- Responsive navigation
- Role-based routing
- Loading states

### 🚧 In Development
- Booth detail with live stream
- Real-time chat
- Product catalog
- Order checkout
- Admin dashboard
- Exhibitor dashboard
- Live streaming controls

## Deployment

### Netlify

1. Build command: `npm run build`
2. Publish directory: `dist`
3. Add environment variables in Netlify dashboard

## License

MIT