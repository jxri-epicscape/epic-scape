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

Epic Scape was founded in 2024 by **Jyri Puhakka** — a self-taught full-stack game designer with 15+ years as a special education teacher, certified work supervisor, and game-based learning consultant. Epic Scape is where these threads meet: learning, mystery, and movement — small moments of wonder where puzzles and the world around us come alive in unexpected ways.

The platform has been deployed in museums, libraries and city parks across Finland, with over 1,400 players and a 4/5 average rating.

---

## Get in Touch

If you're a developer, designer or someone who finds this interesting — we're always open to a conversation. Whether it's a collaboration, a technical question or just curiosity about how this works in practice, feel free to reach out.

📧 [jyri@epicscape.game](mailto:jyri@epicscape.game)
🌐 [www.epicscape.game](https://www.epicscape.game)
