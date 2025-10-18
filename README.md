🎬 Nxt Watch Application
📖 Overview

Nxt Watch is a YouTube-like video streaming application built using React.
It includes authentication, routing, API integration, light/dark theme switching, and dynamic views for Home, Trending, Gaming, and Saved Videos.

This project demonstrates various React concepts including:

Routing

Protected Routes

State management

Context API

Cookies for authentication

API Integration

Conditional Rendering

Theming

🚀 Functionalities
🧑‍💻 Login Route

Initially, the app opens in Light theme.

When invalid credentials are provided → display the error message from the response.

When valid credentials are provided → navigate to Home Route.

Unauthenticated users trying to access protected routes (Home, Trending, Gaming, Saved Videos, or Video Details) are redirected to Login Route.

Authenticated users opening /login are redirected to Home Route.

Show/hide password feature implemented via checkbox.

Use JWT Token stored in cookies for authentication.

🏠 Home Route

On successful login, user lands on the Home page.

Fetch data using an HTTP GET request to Home Videos API URL with:

jwt_token from cookies

Query parameter search (initially empty)

Loader appears during data fetching.

Failure View appears if API fails.

Retry button re-fetches videos.

Users can search videos by keyword.

No Videos View shown when API returns an empty list.

Clicking a video navigates to Video Item Details Route.

Sidebar Navigation:

Home → /

Trending → /trending

Gaming → /gaming

Saved Videos → /saved-videos

🔥 Trending Route

Authenticated users only.

Fetch trending videos via API using jwt_token.

Show Loader during fetch.

On failure → show Failure View.

Retry button re-fetches data.

Sidebar navigation:

Home → /

Gaming → /gaming

Saved Videos → /saved-videos

🎮 Gaming Route

Authenticated users only.

Fetch gaming videos using jwt_token.

Show Loader during fetch.

On failure → show Failure View.

Retry button re-fetches videos.

Sidebar navigation:

Home → /

Trending → /trending

Saved Videos → /saved-videos

📺 Video Item Details Route

Authenticated users only.

Fetch video details by video_id from API using jwt_token.

Show Loader while fetching.

On failure → show Failure View.

Use react-player for video playback.

Buttons:

Like / Dislike / Save initially inactive.

Clicking Like activates it and deactivates Dislike.

Clicking Dislike activates it and deactivates Like.

Clicking Save adds the video to Saved list and changes text to “Saved”.

Clicking Saved again removes video from Saved list and changes text back to “Save”.

💾 Saved Videos Route

Authenticated users only.

If Saved Videos list is empty → show No Saved Videos Found View.

Display list of saved videos otherwise.

Sidebar navigation:

Home → /

Trending → /trending

Gaming → /gaming

Clicking a video opens its Video Details Route.

🚫 Not Found Route

When a random/invalid path is accessed → redirect to Not Found Route.

🧭 Header Functionalities

Clicking the website logo navigates to Home.

Theme icon button toggles Light/Dark mode.

Logout button opens a confirmation popup.

Cancel → closes popup (no navigation).

Confirm → navigates to Login Route.

