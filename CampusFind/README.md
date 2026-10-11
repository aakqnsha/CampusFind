# CampusFind — APSIT Lost & Found

A front-end prototype for the A. P. Shah Institute of Technology campus community. Students can browse lost/found listings and submit an item with an optional photo.

## Problem statement
Students frequently lose personal belongings within college campuses. Finding these items can be difficult when there is no centralized platform for reporting lost or found belongings.

CampusFind aims to simplify this process by allowing students to report items and browse existing listings through a single website.

## Objectives
- Develop a user-friendly lost and found website.
- Allow users to report lost and found items.
- Implement item searching and category filtering.
- Use Git and GitHub for version control and collaboration.
- Containerize the website using Docker.
- Automate project checks and Docker image building using GitHub Actions.

## Pages
- `index.html` — landing page
- `listings.html` — search, status filters, category filter and listings
- `report.html` — lost/found submission form with optional image upload

## Current prototype behaviour
HTML, CSS and JavaScript. Listings are saved in the browser's localStorage, so they are available only in that browser/profile and do not sync between students/devices. Photos must be JPG, PNG or WEBP and under 2 MB. This is a prototype, not a connected production database.

## Run locally
Open `index.html` in a browser, or run a local static server from this folder. Docker serves the pages through Nginx:

```bash
docker build -t campusfind .
docker run --rm -p 8080:80 campusfind
```

Then open `http://localhost:8080`. GitHub Actions checks required files and builds the Docker image.

## Future database upgrade
For shared listings across APSIT students, add a small backend (for example Python Flask) and MySQL database. Store item details and image filenames/URLs in MySQL; store uploaded images in an uploads directory or object storage rather than in a database text field. Add server-side validation and moderation before public deployment.
