# Share Places

A social app for sharing places: sign up with a profile picture, add places with a photo, address and description, see each place on a map, and browse other users' places. Built with **React 18, TypeScript and Redux Toolkit (RTK Query)**, backed by a Node/Express/MongoDB API.

**Live demo:** [share-places-eta.vercel.app](https://share-places-eta.vercel.app) · You can browse users and their places without an account. Sign up to add your own.
**Back end:** [Abdel-Fadeel/Share-Places-API](https://github.com/Abdel-Fadeel/Share-Places-API)

## Features

- **Auth.** Sign up with an image upload and log in. The JWT is kept in `localStorage` with auto-logout when it expires, and a custom `useAuth` hook plus context share it.
- **Users page** showing every user with their avatar and place count.
- **Places per user,** with an image, address and description, and a **map view** (React Leaflet / OpenStreetMap) in a modal.
- **Add, edit and delete places.** Only the owner can edit or delete, and delete asks for confirmation.
- **Data fetching and caching** with RTK Query (`usersApi`, `placesApi`), including automatic cache invalidation after mutations.
- **Reusable UI kit:** custom form inputs with validation, image upload with preview, modal, backdrop, side drawer, spinner and error modal.
- **Protected routes** that change with the auth state.

## Tech stack

| | |
|---|---|
| UI | React 18, CSS Modules |
| Language | TypeScript |
| State and data | Redux Toolkit + RTK Query, React Context |
| Routing | React Router 6 |
| Maps | Leaflet + React Leaflet |
| HTTP | RTK Query `fetchBaseQuery`, Axios |
| Tooling | Create React App, env-cmd |
| Hosting | Vercel (front end), Render (API), MongoDB Atlas |

## Getting started

Run the [API](https://github.com/Abdel-Fadeel/Share-Places-API) on port 5000 first, then:

```bash
git clone https://github.com/Abdel-Fadeel/Share-Places.git
cd Share-Places
npm install
npm start
```

Then open http://localhost:3000. `.env.development` points `REACT_APP_BASE_URL` to `http://localhost:5000/api/v1`, and `.env.production` points it to the deployed API.

| Command | What it does |
|---|---|
| `npm start` | Start the dev server with `.env.development` |
| `npm run build` | Production build (uses `.env.production`) |
| `npm test` | Run tests |

## Project structure

```
src/
├── users/        # Users list, Auth page
├── places/       # UserPlaces, NewPlace, UpdatePlace, PlaceItem, Map
├── shared/       # UI kit (FormElements, UIElements, Navigation), auth context, hooks, validators
└── store/        # Redux store + RTK Query APIs (usersApi, placesApi)
```

## Author

**Abdel-Fadeel Hamdy**, Front-End Engineer · [GitHub](https://github.com/Abdel-Fadeel)
