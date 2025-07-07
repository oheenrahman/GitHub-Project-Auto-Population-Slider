# GitHub Project Showcase Slider

A lightweight, responsive component that fetches your latest GitHub repositories with the GitHub REST API and presents them in a sleek Swiper.js carousel.

---

## 📸 Preview

Each repo is shown as an Open Graph image card, followed by the project name, description, and a “View on GitHub →” link.

Check it out here: https://oheenrahman.com/

---

## 🔧 Features

- 🎠 **Swiper.js** slider with autoplay, keyboard navigation, pagination, and next/prev arrows  
- 🔗 Live data from the GitHub API (up to 100 repos)  
- 🛑 Skips forks and archived projects automatically  
- 🖼 Clean, responsive card design with subtle drop-shadows  
- 📱 Mobile-first layout; shows two slides ≥ 900 px wide  

---

## 🚀 How it Works

1. `script.js` requests your repositories:
   ```js
   const endpoint = `https://api.github.com/users/${username}/repos?per_page=100&sort=updated`;
   ```

2. Filters out forks and archived repos:
   ```js
   const projects = repos.filter(r => !r.fork && !r.archived);
   ```

3. Builds a `<div class="swiper-slide">` for each repo containing:
   - GitHub Open Graph image (`https://opengraph.githubassets.com/1/<user>/<repo>`)
   - Project name and description
   - Link to the repo

4. Initializes Swiper with autoplay, pagination, keyboard control, and breakpoints.

---

## 🛠 Tech Stack

| Purpose       | Tech                                  |
|---------------|----------------------------------------|
| Carousel / UI | [Swiper.js](https://swiperjs.com/)     |
| Data source   | GitHub REST API                        |
| Scripting     | Vanilla JavaScript (ES6+)              |
| Styling       | Custom CSS                             |

---

## 📂 File Structure

```
├── index.html   # (Sample markup shown below)
├── script.js    # Fetch & render GitHub repos
└── style.css    # Swiper & card styling
```

---

## ⚙️ Setup

1. **Add the HTML** somewhere in your page:

   ```html
   <div class="projectsSwiper swiper">
     <div class="swiper-wrapper" id="projects-wrapper"></div>

     <!-- Controls -->
     <div class="swiper-button-next"></div>
     <div class="swiper-button-prev"></div>
     <div class="swiper-pagination"></div>
   </div>
   ```

2. **Include Swiper, CSS, and JS**:

   ```html
   <!-- Swiper CSS -->
   <link rel="stylesheet"
         href="https://cdn.jsdelivr.net/npm/swiper/swiper-bundle.min.css" />

   <!-- Your custom styles -->
   <link rel="stylesheet" href="style.css" />

   <!-- Swiper JS -->
   <script src="https://cdn.jsdelivr.net/npm/swiper/swiper-bundle.min.js"></script>

   <!-- Repo-fetching script -->
   <script src="script.js" defer></script>
   ```

3. **Update the username** (optional):  
   Inside `script.js`, change:

   ```js
   const username = ["username"];
   ```

   to your GitHub handle.

---

## 🧩 Customization Tips

| Want to…                        | Change this                                 |
|---------------------------------|----------------------------------------------|
| Show more slides on desktop     | `breakpoints` in `new Swiper({...})`         |
| Tweak card size or shadow       | `.swiper-slide img` block in `style.css`     |
| Alter autoplay speed            | `autoplay.delay` (ms) in Swiper config       |
| Use a dark/light theme toggle   | Add CSS variables & switch with JS           |

---

## 🛡️ License

Released under the **MIT License**. See `LICENSE` for details.

---

## 💡 Author

Built with ❤️ by **[@oheenrahman](https://github.com/oheenrahman)** — feel free to fork, star, and improve!
