<p align="center">
  <a href="https://pakua.app/" target="_blank"><img src="./images/logo.svg" width="150" alt="Pakua App"></a>
</p>

<h1 align="center">Pakua App</h1>

<p align="center">
  A slick web app for downloading audio and video from YouTube as MP3 or MP4.<br>
  Express + <code>ytdl-core</code> back end, hand-written HTML/CSS/JS front end.
</p>

<p align="center">
  <a href="https://pakua.app/">🌐 Live Site</a> •
  <a href="#-features">✨ Features</a> •
  <a href="#-quick-start">🚀 Quick Start</a> •
  <a href="#-api">🔌 API</a> •
  <a href="#-structure">🏗️ Structure</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Node.js-Express_4-339933?logo=nodedotjs" alt="Node.js + Express 4">
  <img src="https://img.shields.io/badge/ytdl--core-4.11-FF0000?logo=youtube" alt="ytdl-core">
  <img src="https://img.shields.io/badge/SweetAlert2-10-F27474" alt="SweetAlert2">
  <img src="https://img.shields.io/badge/Firebase-Analytics-FFCA28?logo=firebase" alt="Firebase Analytics">
</p>

---

## 🌟 Highlights

- 🎧 **MP3 and MP4 downloads** from a pasted YouTube link
- 🎨 **Slick UI** with light and dark theme (choice remembered in `localStorage`)
- 🪶 **Tiny stack** - one Express file serving a static single-page front end

## ✨ Features

- Slick UI design and elements
- Mp3 and Mp4 download (`/downloadmp3`, `/downloadmp4`)
- Light and Dark theme toggle
- URL validation with friendly toast messages (SweetAlert2)
- Original video title used as the downloaded file name
- Firebase Analytics, jQuery and a "Buy me a coffee" button loaded from their CDNs

## 🚀 Quick Start

```bash
npm install
PORT=3000 npm start      # → http://localhost:3000
```

`PORT` is read from the environment (no default), so it must be set. `dotenv` is installed, so a local `.env` file is a convenient place for it, but `index.js` does not load it by itself.

> The front end in `js/script.js` calls the hosted API at `https://pakua-app.herokuapp.com`. Change the `serverURL` constant to `''` or your own origin to use your local server.

## 📦 Scripts

| Script          | Description                         |
| --------------- | ----------------------------------- |
| `npm start`     | Run `node index.js`                 |

## 🔌 API

| Method | Endpoint                | Description                                          |
| ------ | ----------------------- | ---------------------------------------------------- |
| GET    | `/downloadmp3?url=<yt>` | Streams the best audio-only track as `<title>.mp3`   |
| GET    | `/downloadmp4?url=<yt>` | Streams the best video+audio format as `<title>.mp4` |

An invalid YouTube URL returns `400`.

## 🏗️ Structure

```
index.js          # Express server: static files + download endpoints
index.html        # Single-page UI
css/style.css     # Styles incl. light/dark themes
js/script.js      # Theme switch, validation, download trigger
images/           # logo.svg, background.svg, premium-icon.svg
```

## ⚙️ Configuration

| Variable | Purpose                          |
| -------- | -------------------------------- |
| `PORT`   | Port the Express server listens on |

The Firebase web config embedded in `index.html` is a public client-side config (identifies the project, does not grant privileged access).

## 🚀 Deployment

Any Node host works (the production front end points at a Heroku-hosted API). Set `PORT`, run `npm start`.

## ⚠️ Disclaimer

Downloading content from YouTube may violate YouTube's Terms of Service or copyright law. Use only for content you own or have permission to download. `ytdl-core` is no longer maintained, so downloads may break when YouTube changes.

## 📄 License

`package.json` declares ISC; no LICENSE file is included in the repository.

## 👤 Author

**Chalii wa UX/UI** - [@chaliiwaui](https://github.com/chaliiwaui)

- 📧 Email: me@makindajackson.com
- 💼 LinkedIn: [Jackson Makinda](https://linkedin.com/in/makindajack)
- 🎨 Dribbble: [@makindajack](https://dribbble.com/makindajack)
- 🐦 Twitter: [@makindajack](https://twitter.com/makindajack)

Original project author listed in `package.json`: [JemCdo](https://github.com/JemCdo).

---

Built with ❤️ in Dar es Salaam, Tanzania 🇹🇿
