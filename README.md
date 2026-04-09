# API Sandbox

![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![CRA](https://img.shields.io/badge/Create_React_App-5-09D3AC?style=flat-square&logo=createreactapp&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)
![Browser Only](https://img.shields.io/badge/Runs_In-Browser-orange?style=flat-square&logo=googlechrome&logoColor=white)

A browser-based HTTP client that works like Postman — without the desktop app. Build and test API requests directly in your browser, with your data staying local the entire time.

> **Note:** Because this runs entirely in-browser, some things Postman handles natively (cross-origin requests, restricted headers, custom TLS certs) aren't possible here. See [Browser Limitations](#browser-limitations) for details.

---

## Getting Started

```bash
npm install
npm start
```

Open [http://localhost:3000](http://localhost:3000). The app hot-reloads on changes.

---

## Features

### Request Builder

Supports all HTTP methods with full control over query parameters, headers, cookies, redirect behavior, and per-request settings (timeout, cache policy, credentials, CORS mode).

**Body types:**
- JSON
- Raw text (XML, HTML, etc.)
- Form-data (including file uploads)
- x-www-form-urlencoded
- GraphQL
- Binary

### Authentication

Built-in helpers for Bearer Token, Basic Auth, API Key (header or query param), and Digest (best-effort). Auth is automatically injected — no need to handcraft headers manually.

### Environments & Variables

Create named environments with key-value pairs (secrets supported). Use `{{variable}}` syntax anywhere in the URL, params, headers, or body. Switch environments from the sidebar.

### Tabs, History & Collections

- **Tabs** — Multi-tab workspace with unsaved-change indicators
- **History** — Last 100 requests, replayable with one click
- **Collections** — Save requests into folders, import/export as JSON

### Response Viewer

View responses in three modes:

| Mode | Description |
|------|-------------|
| Pretty | Collapsible JSON tree with search |
| Raw | Unformatted response body |
| Preview | Rendered HTML |

Also shows status code, duration, size, final URL, and response headers. Response body can be downloaded directly.

### Code Export

Generate ready-to-use code snippets for:
- cURL
- JavaScript Fetch
- Axios
- Node.js (native `http`)
- Python Requests
- PHP cURL

### Tests

Write lightweight assertions against any response:
- Status code
- Response time
- Header presence
- Body contains / does not contain
- JSONPath exists / equals
- Array length

---

## Browser Limitations

This app runs entirely client-side, which comes with some constraints compared to a native API client:

| Limitation | Detail |
|------------|--------|
| **CORS** | Cross-origin APIs that don't send permissive CORS headers will block requests. Use a server-side proxy for full compatibility. |
| **Restricted headers** | Browsers silently block headers like `Host`, `User-Agent`, `Content-Length`, etc. |
| **Cookies** | No access to a persistent cookie jar; limited compared to native clients. |
| **TLS / certificates** | Custom certificate stores aren't supported in-browser. |
| **Digest / OAuth** | Partial support only — some flows require low-level primitives the browser doesn't expose. |

---

## Scripts

| Command | Description |
|---------|-------------|
| `npm start` | Dev server on port 3000 |
| `npm test` | Jest in watch mode |
| `npm run build` | Production build → `build/` |
| `npm run eject` | Ejects CRA config (irreversible) |

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| UI | React 19, Tailwind CSS 3 |
| Icons | Lucide React |
| Build | Create React App (react-scripts 5) |
| Requests | `fetch` + `AbortController` |
| Persistence | `localStorage` |
| Testing | Jest, React Testing Library |

---

## Privacy

No data leaves your browser. All requests, history, environments, and collections are stored in `localStorage`. Nothing is sent to any server unless you explicitly export and share your collections.

---

## License

MIT

---

[Live demo](https://ClaudeMaxUser.github.io/API-Sandbox/)