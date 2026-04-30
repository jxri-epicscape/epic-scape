# Epic Scape

> **A visitor engagement and data platform for public spaces.**

Epic Scape activates museums, libraries, parks and other public venues by guiding visitors through interactive, location-bound experiences. The game mechanic is the delivery method — what venues subscribe to is activated visitors and real-time behavioural data.

> *You are the character.*

---

## How It Works

### For the player
The experience starts with a QR code. No app download, no registration, no ads. The player opens the experience directly in their mobile browser and begins exploring the space by solving location-bound puzzles. Each puzzle is tied to the real environment — architecture, history, objects, stories. The experience takes approximately 25–30 minutes and works for individuals, pairs and groups of all ages.

### For the venue
The venue subscribes to a monthly plan and receives a fully built, hands-on experience tailored to their space and story. Epic Scape handles all technical implementation, content scripting and onboarding. The venue then gets a custom analytics dashboard showing how visitors move through the space, where they spend time, which puzzles were hardest, and how long sessions last.

For venues seeking interactive, experiential content for their visitors, Epic Scape offers a ready-built solution: a track that turns the venue itself into the medium.

---

## Live Deployments

A few examples of tracks currently live:

###  Esplanade Park, Helsinki — *The Authors' Park*
Three statues of Finnish authors stand among the lime trees of Helsinki's central park, each facing the same direction. Players walk the park from west to east, solving puzzles tied to the statues, the benches and a small pool at the eastern end. The hidden message: a single word the writers leave behind for every generation.

→ [espa.epicscape.game](https://espa.epicscape.game)

###  Rikhardinkatu Library, Helsinki — *The Panda's Tooth Mystery*
The library's main hall is home to a wooden panda that has lost a tooth — and with it, the library has fallen into chaos. The children's section, the archives, the elevator and the upper floors: each holds a clue. The library is Epic Scape's longest-running partnership: two years, three contract renewals.

→ [riku.epicscape.game](https://riku.epicscape.game)

Other past live tracks include festival activations (Love & Anarchy Film Festival), museum tracks (Punk Museum, Helsinki), and outdoor city tracks (Lahti's Matkustajasatama, Helsinki's Töölönlahti & Kaisaniemi).

---

## Key Features

| Feature | Description |
|---|---|
| Browser-based | Runs entirely in mobile browser — no app needed |
| Location-bound puzzles | Each puzzle tied to the physical environment |
| Multilingual | Multiple languages per track, player selects at start |
| AR integration | Augmented reality elements without a separate app |
| AI-assisted content | Dynamic player-facing responses powered by AI |
| Real-time dashboard | Supabase-powered analytics, PDF/CSV export |
| Memory layer *(in dev)* | Cookie-based cross-location place memorability tracking |

---

## Data & Analytics

Epic Scape collects anonymous session data per player. No personal information, email addresses or accounts are required or stored.

**Per session, the platform captures:**
- Player nickname (self-selected)
- Date and start time
- Total play time
- Estimated distance walked (metres)
- Hints used per puzzle
- Wrong answers per puzzle
- Puzzle completion events
- Player rating (1–5 stars)

**Dashboard metrics include:**
- Total players and players per day
- Average and total play time
- Average distance walked
- Hardest puzzles by wrong answer rate
- Puzzle completion funnel
- Session-level detail table

Data is accessible via a web dashboard with date filtering, CSV export and PDF report generation. Each venue has its own login and sees only their own data.

---

## Track Structure

Each Epic Scape track follows a modular puzzle structure.

**Standard track: 4 + 1**
Four location-bound sub-puzzles leading to one final puzzle that ties the narrative together. Estimated play time: 25–30 minutes.

**Extended track: 6 + 1** *(on request)*
Six sub-puzzles plus a final, designed as an hour-length experience. Tailored to the venue's specific space, story and audience.

**Each track includes:**
- Narrative framework and script by Epic Scape's game writer
- Puzzle design tailored to the physical space
- Hint system (players can request hints without losing progress)
- Multilingual content layer
- Staff onboarding documentation
- Launch social media materials

Epic Scape delivers each track as a fully finished premium content solution. An initial briefing session with the venue is typically all that is needed — Epic Scape handles all puzzle design, scripting and technical implementation end to end.

---

## Supported Venue Types

Epic Scape has been deployed in, or is designed for, the following venue types:

-  **Museums** — permanent and temporary exhibitions, indoor and outdoor
-  **Libraries** — public libraries, university libraries
-  **City parks and public spaces** — open-air routes, urban exploration
-  **Shopping centres** — indoor multi-floor routes, seasonal activations
-  **Conference and wellness centres** — team activities, customisable corporate experiences
-  **Festivals and events** — time-limited activations with custom branding
-  **Airports and transit hubs** — waiting time activation for travellers

---

## Pricing

**Epic Scape operates on a *Game-as-a-Service (GaaS)* monthly subscription model. The customer is the venue, not the player.**

---

## AI Integration

Epic Scape uses the **Anthropic Claude API** to generate dynamic, context-aware player-facing responses in real time. Rather than serving static text, the game engine constructs prompts based on the player's current puzzle state, location context and narrative position — and generates responses that feel alive and specific to that moment.

### How it works in practice

- Each puzzle step passes relevant context (location, narrative state, player progress) to the LLM via a Node.js proxy server
- The proxy handles API authentication, rate limiting and response formatting before returning content to the React/TypeScript frontend
- Prompt engineering controls tone, length and narrative voice — keeping responses consistent with the track's story world
- This approach eliminates manual content authoring for dynamic states, reducing track build time significantly

### Stack

| Layer | Technology |
|---|---|
| LLM | Anthropic Claude (claude-sonnet) via REST API |
| Proxy | Node.js (TypeScript) |
| Frontend | React + TypeScript |
| Database | Supabase (PostgreSQL) |
| Analytics | Custom dashboard with real-time Supabase queries |

---
## AR Integration

Epic Scape implements browser-native augmented reality using **MindAR** and **Three.js** — no app download required. When a player points their camera at a physical target in the real environment, the game overlays AR content directly in the mobile browser.

### How it works

- Image targets are compiled to `.mind` format and served via CDN
- **MindAR** handles real-time image recognition and anchor tracking via the device camera
- **Three.js** renders the AR overlay — banners, 3D objects or custom geometry — anchored to the detected target
- A custom render loop drives the scene; anchor callbacks (`onTargetFound` / `onTargetLost`) control visibility and puzzle state
- Once a target is locked for 2 seconds, the puzzle input form is revealed below the camera view

### Configuration

Each AR puzzle is fully configurable per track via the card data layer:

| Property | Description |
|---|---|
| `arMode` | `banner`, `cube`, or custom 3D shape |
| `arTargetSrc` | URL to compiled `.mind` image target |
| `arBannerText` | Text rendered on the AR overlay |
| `arFilterMinCF` / `arFilterBeta` | MindAR tracking sensitivity tuning |
| `arObjectShape` / `arObjectColor` | 3D object properties |

### Stack

| Layer | Technology |
|---|---|
| AR tracking | MindAR (image target recognition) |
| 3D rendering | Three.js (WebGL) |
| Camera access | `navigator.mediaDevices.getUserMedia` |
| Asset delivery | ImageKit CDN (`.mind` targets) |
| Frontend | React + TypeScript |

---

## Roadmap

**Currently live**
- [x] Browser-based experience engine
- [x] Real-time data dashboard (Supabase-powered, PDF/CSV export)
- [x] Multilingual support
- [x] AR element integration
- [x] Admin panel for venue management
- [x] AI-assisted content generation

**In development**
- [ ] Cookie-based cross-location memory layer
- [ ] Automated memory follow-up prompts across locations
- [ ] Platform for third-party track creation
- [ ] Enhanced analytics with comparative benchmarking

**Future vision**
- [ ] White-label solutions for partner organisations
- [ ] Nordic and European market expansion
- [ ] Business intelligence as a standalone product for venue operators

---

## About

Epic Scape is where learning, mystery, and movement meet. Founded by full-stack designer **Jyri Puhakka**, the platform distills 15 years of experience in special education and game-based consulting into a digital engine for physical exploration. Currently deployed in museums and city parks nationwide, it engaged over 1,400 players in the past year alone with an average rating of 4/5.

---

## Get in Touch

If you're a developer, designer or someone who finds this interesting — we're always open to a conversation. Whether it's a collaboration, a technical question or just curiosity about how this works in practice, feel free to reach out.

[jyri@epicscape.game](mailto:jyri@epicscape.game)
[www.epicscape.game](https://www.epicscape.game)

## Testing some new AI & AR tech – interested in a demo? Send me a DM!
