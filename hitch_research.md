# HITCH

> Community‑Driven Reward‑Token Hitchhiking App & Movement

---

## 🌍 Project Vision

**HITCH** is not just a ride-sharing application — it's a **cultural shift** that transforms everyday travel into a communal adventure. Users—**Riders (Hitchers)** and **Pilots (Drivers)**—share rides for short to medium distances (500 m–200 km) and earn **reward tokens** instead of cash. Tokens unlock real-world rewards from partner brands, fostering exploration, sustainability, and social connection.

We want HITCH to become an **everyday habit**, not just an app, by weaving gamified features, community storytelling, and social status into the fabric of urban mobility.

---

## 🚀 Core Motives

- 🧭 **Promote Adventure & Connection:** Turn commutes into shared experiences.
- 🤝 **Foster Trust & Community:** Build reputations through transparent ratings and stories.
- 🎁 **Empower Through Rewards:** Reward eco-friendly travel with brand-sponsored perks.
- 🛡 **Safety & Reliability:** Prioritize verified users, real-time tracking, and SOS features.
- 🔄 **Everyday Engagement:** Make HITCH a daily ritual with streaks, leaderboards, and social sharing.

---

## 🧠 Key Features & Engagement Mechanics

### 1. Core Ride Functionality

- **Live Map View:** Discover Pilots/Riders within a 2 km radius.
- **Role Toggle:** Instantly switch between Rider and Pilot modes.
- **Secure Onboarding:** KYC, selfie verification, GDPR-compliant data handling.

### 2. Reward & Token System

- **Earn Tokens:** 10 tokens per verified ride; bonuses for distance, streaks, referrals.
- **Token Categories:** Food, Travel Gear, Clothing, Coupons.
- **Instant Redemption:** 100 tokens = ₹100 voucher or product; 200 tokens unlock premium offers.
- **Affiliate Model:** Brands subsidize redemptions and pay 10% commission on vouchers.

### 3. Habit-Forming Social Features

- **Ride Stories:** Share short, story-like posts after rides (with photos, text). Others can react or comment, building rapport.
- **Leaderboards:** Regional and corridor-based rankings for “Top Pilots,” “Eco Warriors” (highest CO₂ saved), and “Explorers” (distinct routes covered).
- **Streaks & Milestones:** Daily/weekly ride streaks unlock bonus tokens and exclusive badges.
- **Badges & Titles:** Earn titles like **“Campus Champion,” “City Voyager,” “Eco Hero”** displayed on profile and map pins.
- **Referral Leagues:** Friendly group challenges—invite friends, form teams, compete for most rides or tokens.

### 4. Community & Discovery

- **Geo‑Tagged Meetups:** Scheduled group rides or events flagged on the map for community gatherings.
- **Collaborative Routes:** Users can propose popular adventure routes; top-voted routes become “HITCH Trails” with special rewards.
- **In-App Feeds:** See nearby ride stories, leaderboards, and limited-time local deals.

### 5. Safety & Anti-Cheating

- **Geofencing & Haversine Checks:** Ensure rides meet distance and uniqueness criteria.
- **Real‑Time SOS & Live-Share:** One-tap emergency alerts to contacts and on-duty support.
- **Review & Audit:** Combined AI and manual audits flag suspicious behavior; trust scores adjust dynamically.

---

## 📂 Detailed Directory Structure

Below is a refined code organization showing exactly where each feature lives:

```
app/
├── onboarding.tsx          # Role selection, KYC splash
├── map/
│    ├── index.tsx          # Live Map View (pilot/rider markers)
│    ├── RideRequest.tsx    # Request & confirm ride flow
│    └── RideStatus.tsx     # Active ride status & route
├── stories/
│    └── RideStories.tsx    # Story feed & create story UI
├── leaderboard/
│    └── Leaderboard.tsx    # Leaderboards & badges display
├── feeds/
│    └── CommunityFeed.tsx  # In-app feeds for meetups & deals
└── (tabs)/
     ├── rides.tsx          # Ride history & milestones
     ├── rewards.tsx        # Token wallet & redemption UI
     └── profile.tsx        # User profile, streaks, trust score, edit

components/
├── RoleToggle.tsx          # Rider/Pilot switch
├── RadarNotification.tsx   # Pilot radar-like alerts
├── TokenProgressCard.tsx   # Token category progress
├── RewardModal.tsx         # Redemption modal
├── StoryCard.tsx           # Single ride story UI
├── Badge.tsx               # Badge & title component
├── StreakTracker.tsx       # Streak & milestone component
└── MeetupPin.tsx           # Geo-tagged event marker

hooks/
└── useRideData.ts          # Ride API hook (create/join/status)
└── useRewardData.ts        # Reward API hook
└── useLeaderboards.ts      # Leaderboard data hook

backend/
├── controllers/
│    ├── authController.js  # Auth, profile, role logic
│    ├── rideController.js  # Ride create/join/nearby/complete
│    ├── rewardController.js# Token earn/redeem logic
│    ├── storyController.js # Ride stories CRUD
│    └── leaderboardController.js # Leaderboard & badge logic
├── models/
│    ├── User.js            # User schema (role, tokens, trust)
│    ├── Ride.js            # Ride schema (geo, status)
│    ├── Reward.js          # Reward schema (token counts)
│    ├── Story.js           # Ride story schema
│    └── Badge.js           # Badge & milestone schema
├── routes/
│    ├── authRoutes.js      # /register, /login, /me, /update
│    ├── rideRoutes.js      # /rides endpoints
│    ├── rewardRoutes.js    # /rewards endpoints
│    ├── storyRoutes.js     # /stories endpoints
│    └── leaderboardRoutes.js # /leaderboards endpoints
├── middleware/
│    ├── auth.js            # JWT verification
│    ├── antiCheat.js       # Geofence & duplicate ride prevention
│    └── rateLimit.js       # Throttle sensitive endpoints
└── server.js               # App setup & route mounting
```

## 📌 Feature Breakdown & Daily Targets

**Week 1: Core Ride & Auth Flow**

- **Day 1:** Setup `authRoutes`, `authController`, JWT middleware, user model.
- **Day 2:** Build onboarding screen & RoleToggle component, integrate auth API.
- **Day 3:** Implement `rideRoutes` & `rideController` for create/join rides.
- **Day 4:** Develop Map index.tsx to call `/rides/nearby` and render markers.
- **Day 5:** Create RideRequest/RideStatus screens with API hooks.
- **Day 6:** Write `antiCheat` middleware for distance & uniqueness checks.
- **Day 7:** End-to-end testing of auth + ride flows; bugfix.

**Week 2: Rewards & Social Layers**

- **Day 8:** Build `rewardRoutes`, `rewardController`, and Reward model.
- **Day 9:** Implement rewards.tsx with TokenProgressCard and redemption modal.
- **Day 10:** Create `storyRoutes`, `storyController`, and Story model.
- **Day 11:** Develop RideStories.tsx and StoryCard; integrate CRUD flows.
- **Day 12:** Build leaderboardRoutes, leaderboardController, and Badge model.
- **Day 13:** Implement Leaderboard.tsx and Badge component UI.
- **Day 14:** Integrate StreakTracker component and milestone logic.

**Week 3: Community & Polishing**

- **Day 15:** Create CommunityFeed.tsx and MeetupPin component; story-driven feeds.
- **Day 16:** Add WebSocket or polling for real-time RadarNotification.
- **Day 17:** Implement profile edit and trust score logic in profile.tsx.
- **Day 18:** Add badge displays on map pins and feed stories.
- **Day 19:** Dark mode, localization, and accessibility checks.
- **Day 20:** Performance optimizations and code cleanup.
- **Day 21:** Final QA, write documentation, prepare for launch.

---

## 🛠 Tech Stack

- **Frontend:** React Native (Expo Router), TypeScript, Reanimated
- **Backend:** Node.js + Express, MongoDB (Mongoose)
- **Auth:** JWT, bcrypt; Role‑based access
- **Real‑Time:** WebSockets (ride requests, radar alerts)
- **Maps:** Google Maps API / Mapbox

---

## 📈 Growth & Engagement Roadmap

1. **Phase 1: Hyperlocal MVP**
   - Launch in one corridor (e.g., college campus)
   - Focus on core rides + basic rewards
2. **Phase 2: Habit Loop Activation**
   - Introduce streaks, leaderboards, ride stories
   - Partner with 5–10 local brands for token redemptions
3. **Phase 3: Scale & Monetize**
   - Expand to multiple corridors, cities
   - Roll out analytics dashboards for brand partners
4. **Phase 4: Community Expansion**
   - Geo‑tagged events, HITCH Trails, team leagues
   - International pilot launches in SE Asia

---

## 💼 Team Roles & Next Steps

| Developer | Focus Area                         |
| --------- | ---------------------------------- |
| Dev #1    | Auth & Profile + Ride Stories Feed |
| Dev #2    | Map & Ride Matching + Radar Alerts |
| Dev #3    | Rewards System + Leaderboards & UI |

**Immediate Task:** Finalize core Map + Ride flows, then layer on **stories** and **leaderboard** components before August internship.

---

## 📞 Contact & Collaboration

- **GitHub:** [https://github.com/yourusername/hitch](https://github.com/yourusername/hitch)
- **Slack:** #hitch-dev channel
- **Notion:** HITCH Roadmap & Specs

*Let’s build a movement, one ride at a time.*

