# CIS5500HW4A

A full-stack music app for CIS 5500 (Databases) at Penn, Homework 4. It browses a PostgreSQL database of songs and albums ("Swiftify") through an Express API and a React frontend.

## What it does

- **Home page** - song of the day, top songs, and top albums
- **Albums** - every album, plus a page for each album with its track list
- **Songs** - search and filter songs by title, duration, plays, danceability, energy, and valence
- **Song cards** - pop-up details for any song

## Stack

| Part | Tech |
|---|---|
| Database | PostgreSQL on AWS RDS |
| Server | Node.js, Express, `pg` |
| Client | React, React Router, MUI (Data Grid), Recharts |
| Tests | Jest + Supertest |

## API routes

| Route | Returns |
|---|---|
| `GET /author/:type` | author name or Penn key |
| `GET /random` | a random song (song of the day) |
| `GET /song/:song_id` | one song |
| `GET /album/:album_id` | one album |
| `GET /albums` | all albums |
| `GET /album_songs/:album_id` | songs on an album |
| `GET /top_songs` | songs ranked by plays (paginated) |
| `GET /top_albums` | albums ranked by plays (paginated) |
| `GET /search_songs` | songs filtered by title and feature ranges |
| `GET /playlist/entrance_songs` | a generated playlist |

All SQL lives in `server/routes.js`.

## Run it

Fill in the database info in `server/config.json`, then start the server and the client in two terminals:

```bash
cd server
npm install
npm start        # http://localhost:8080
```

```bash
cd client
npm install
npm start        # http://localhost:3000
```

Run the route tests:

```bash
cd server
npm test
```

## Layout

```
server/
  server.js        Express app and route registration
  routes.js        route handlers and SQL queries
  __tests__/       Jest tests for every route
client/src/
  pages/           HomePage, AlbumsPage, AlbumInfoPage, SongsPage
  components/      NavBar, LazyTable (paginated table), SongCard
  helpers/         duration and date formatting
```
