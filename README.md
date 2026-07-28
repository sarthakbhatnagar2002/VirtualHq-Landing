<!-- Auto-generated README using AI RAG -->
<!-- Generated on: 2026-07-28T09:05:35.172Z -->

# VirtualHQ

VirtualHQ is an interactive, pixel-style virtual workspace web application designed to help remote teams connect, collaborate, and build in immersive environments. The application features a retro-futuristic dark mode interface built with React and Tailwind CSS, complete with user authentication, dynamic space feature highlights, pricing tiers, and video walkthrough demos.

---

## Features

- **Interactive Hero Showcase**: Toggle between different video demonstrations of the virtual office tour and team collaboration spaces.
- **Space & Feature Customization**: Explore key platform highlights like Space Creators, Universal Access, Ready-Made Venues, Instant Previews, and Collaborative Workspaces.
- **User Authentication**: Built-in Login and Sign-Up flows supporting user registration, credential validation, session persistence, and logout capabilities.
- **Dynamic Pricing Tiers**: Compare Free, Pro, and Enterprise subscription options with detailed feature breakdowns.
- **Client Reviews & Testimonials**: Showcase user feedback and experiences from industry professionals.
- **Responsive Navigation & Mobile Drawer**: Fully responsive layout optimized for desktop and mobile devices.

---

## Technology Stack

- **Core Library**: React 18 (`react`, `react-dom`)
- **Routing**: React Router DOM (`react-router-dom` v7)
- **Styling**: Tailwind CSS v3/v4 with PostCSS & Autoprefixer
- **Animations**: Framer Motion (`framer-motion`)
- **Icons**: Lucide React (`lucide-react`)
- **Build Tool**: Vite (`vite`)
- **Linter**: ESLint (`eslint`)

---

## Project Structure

```text
virtualr/
├── public/                 # Public assets (e.g., Logo.png)
├── src/
├── assets/             # Images, videos, and user profile pictures
├── components/         # React components (Navbar, Hero, Features, Workflow, Pricing, Reviews, Footer, Login, Signup)
├── constants/          # Static data (nav items, testimonials, features, pricing options, links)
├── App.jsx             # Main application layout and client-side routing
├── index.css           # Global Tailwind and font styles
└── main.jsx            # React DOM mounting entry point
├── .eslintrc.cjs           # ESLint configuration
├── .gitignore              # Git ignore rules
├── index.html              # HTML root template
├── package.json            # Project dependencies and npm scripts
├── postcss.config.js       # PostCSS configuration
├── tailwind.config.js      # Tailwind CSS configuration
└── vite.config.js          # Vite configuration
```

---

## Workflow

1. **Landing Page (`/`)**: 
   - Users land on the `HeroSection`, where they can watch feature videos.
   - Scrolling down reveals the `FeatureSection`, `Workflow`, `Pricing` plans, and client `Reviews`.
2. **Authentication Flow (`/Login`, `/signup`)**:
   - Users can register an account via the Sign-Up page (`/signup`), which communicates with a backend registration endpoint.
   - Upon successful registration, users can log in (`/Login`) with their credentials.
   - Session states are verified using protected requests (`http://localhost:5000/user/verify`) and sessions can be terminated via the logout button in the navigation bar.

---

## Installation

### Prerequisites
Make sure you have [Node.js](https://nodejs.org/) installed on your machine.

### Step-by-Step Setup

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd virtualr
   ```

2. **Install dependencies**:
   Using npm:
   ```bash
   npm install
   ```
   *(Or using your preferred package manager like yarn, pnpm, or bun)*

---

## Usage

### Running the Development Server
Start the local development server using Vite:
```bash
npm run dev
```
Open your browser and navigate to the local URL provided by Vite (typically `http://localhost:5173`).

### Building for Production
To build the optimized production assets:
```bash
npm run build
```

### Previewing the Production Build
To preview the production build locally:
```bash
npm run preview
```

### Linting
To run ESLint across the codebase:
```bash
npm run lint
```

---

## API Documentation

The frontend interacts with an external backend server (inferred to run locally at `http://localhost:5000`). Below are the endpoints consumed by the client components:

| Method | Endpoint | Description | Request Body / Credentials |
| :--- | :--- | :--- | :--- |
| `GET` | `http://localhost:5000/user/verify` | Verifies the current authenticated user session | `credentials: 'include'` |
| `POST` | `http://localhost:5000/user/login` | Authenticates user credentials | JSON: `{ username, password }`, `credentials: 'include'` |
| `POST` | `http://localhost:5000/user/register` | Registers a new user account | JSON: `{ username, email, password }`, `credentials: 'include'` |
| `POST` | `http://localhost:5000/user/logout` | Terminates the current user session | `credentials: 'include'` |

---

## Configuration

- **Tailwind CSS**: Configured in `tailwind.config.js` and `postcss.config.js`.
- **Backend API URL**: Currently hardcoded in components (`Login.jsx`, `Signup.jsx`, `Header.jsx`) pointing to `http://localhost:5000`. Ensure your backend service is running locally on port 5000 for authentication features to work properly.

---

## License

No license specified.
