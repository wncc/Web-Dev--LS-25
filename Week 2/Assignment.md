# Week 2 Assignment: Build a Mini YouTube Clone (Frontend Only)

## Objective

Create a **YouTube-inspired video app** using **React JS**. This is a **frontend-only** project where you will learn to build reusable components, manage state, use hooks like `useState` and `useEffect`, and handle layout with **Flexbox/Grid** — styled with either **Bootstrap** or **Tailwind CSS**.

No backend is involved — instead, you’ll use **sessionStorage** to simulate saving data (like likes and Watch Later).

---

## Core Requirements

> Your website must include all of the following:

### Layout

- **Navbar** with:
  - Site title/logo
  - Dummy search input
  - “Watch Later” button (show count if possible)
  
- **Video Feed (Home Page)**:
  - A grid/flex layout of **Video Cards**
  - Each card should include:
    - Thumbnail (placeholder image)
    - Video title
    - Channel name
    - Views + Time posted
    - ❤️ Like button
    - ➕ Add to Watch Later button

- **Watch Later Page**:
  - Shows only the videos marked “Watch Later”
  - Cards should look the same
  - Option to remove from list

- (Optional) **Sidebar** like YouTube (Home, Shorts, Subscriptions...)

- (Optional) **Footer** with:
  - Your name / © 2025 line
  - Social media or GitHub links (dummy)

---

## React Concepts to Use

- Functional components only
- Use `props` to pass data into components
- Use `useState` for:
  - Liking videos
  - Watch Later tracking
  - Dark/Light mode toggle (optional)
- Use `useEffect` + `setInterval` to show a **live timer**:
  - _Example_: “Time Spent on this site: X seconds”
  - This tracks how long the user has been exploring videos
- Use `react-router-dom` for page navigation (Home / Watch Later)

---

## Store Data in sessionStorage

All state (likes, watch later) should be saved to `sessionStorage` — no backend!

> Data will reset on page refresh. That’s expected!

To learn more about session framework and how it's used visit [**this**](https://docs.djangoproject.com/en/5.2/topics/http/sessions/) site.

## Suggested Folder Structure
<pre>
  src/
├── components/
│   ├── Navbar.jsx
│   ├── VideoCard.jsx
│   ├── Timer.jsx
├── pages/
│   ├── Home.jsx
│   └── WatchLater.jsx
├── data/
│   └── dummyVideos.js
├── App.jsx
└── index.js
</pre>
## Bonus Features (optional)
- **Dark / Light Mode Toggle**
- **Sidebar** with dummy nav links
- **Filter Bar** (e.g., Trending, Music, News)
- **Feedback on actions** (e.g., “Added to Watch Later ✅”)
- **Card Hover Animations**
- **Responsive Design** (media queries or framework classes)

---

## Sample Dummy Data (`dummyVideos.js`)

```js
export const videos = [
  {
    id: 1,
    title: "React Hooks Explained",
    channel: "CodeWithYou",
    views: "1.2M",
    time: "2 days ago",
    thumbnail: "https://via.placeholder.com/300x170",
  },
  {
    id: 2,
    title: "Flexbox in 10 minutes",
    channel: "CSSNinjas",
    views: "860K",
    time: "1 week ago",
    thumbnail: "https://via.placeholder.com/300x170",
  },
  // Add more!
];
```
You may generate and use placedholders from [here](https://smalldev.tools/placeholder-image-generator-online)
## Submission

- **Submit by the deadline** on the form provided  
- **Upload code to GitHub** and share the link  
- **Record a short video** demoing your features and submit it in the form  

---

##  Notes

- Use either **Bootstrap** or **Tailwind CSS** — just mention which one  
- Ensure your app **runs without any errors**  
- Focus on **clean UI**, **functional layout**, and **reusable components**
- You may also add other features which is not part of youtube and get as creative as you want but make sure to explain it in a README and in the video.  

---

**Good luck!**  
Let’s build something fun and functional!  
Feel free to reach out anytime if you’re stuck.



<p align="center"> Created with ❤️ by WnCC </p>
