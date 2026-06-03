# Roleplay Website - Development Roadmap

## What We're Building
A website where people can create their own roleplay worlds, join other worlds, and play characters together.

## The Phases (Do Them In This Order)

### PHASE 1: The Foundation (Weeks 1-2)
This is like building the basic structure before decorating.

**What to build:**
- A simple homepage that shows a list of fake worlds
- A database (storage system) that remembers world information
- The top navigation bar (+ button, recents, profile)
- Basic styling to make it look good

**Why start here?**
- It's the first thing users see
- Everything else depends on this working

---

### PHASE 2: World Creation & World Pages (Weeks 3-4)
Now users can actually CREATE worlds and see them.

**What to build:**
- The world creation form (name, image, mode, language, public/private)
- A world page that shows what's inside a specific world
- Save worlds to the database

**Why next?**
- Users need to be able to create worlds before using them
- This teaches you how data flows in and out

---

### PHASE 3: Persona System (Week 5)
Characters! Let users create roleplay characters.

**What to build:**
- Character creation form (name, description, images)
- A page showing all your characters
- Save characters to the database
- Connect characters to worlds

**Why next?**
- You need characters before people can chat
- This is a self-contained system you can test easily

---

### PHASE 4: Map & Rooms System (Week 6)
The locations and chatrooms where roleplay happens.

**What to build:**
- World creators can add locations (houses, schools, cafes, etc.)
- Each location has rooms (like different rooms in a house)
- Display the map
- Show which room you're in

**Why next?**
- This creates the "spaces" where people interact
- Messaging depends on being in a room

---

### PHASE 5: Messaging System (Week 7)
Users can chat with their characters.

**What to build:**
- Direct messages between characters
- Group chats for rooms
- Show messages in Modern Mode (SMS-like) and Old Mode (letters)
- Save messages to database

**Why next?**
- Now people can actually interact!
- The map/rooms system lets you show WHERE the chat happens

---

### PHASE 6: Social Feed System (Week 8)
Posts, reactions, and comments.

**What to build:**
- Create posts with characters
- Show posts on a feed (Instagram-style for Modern, newspaper for Old)
- Add reactions and comments
- Save posts to database

**Why next?**
- Uses same messaging and persona systems you already built
- Adds more community features

---

### PHASE 7: Calendar System (Week 9)
Track time and events in worlds.

**What to build:**
- Show current in-world date
- Create events on the calendar
- Display calendar in Modern Mode (digital app) and Old Mode (paper calendar)
- Save events to database

**Why next?**
- This is self-contained and doesn't depend on other features much
- Helps with world-building

---

### PHASE 8: Settings & Rules System (Week 10)
World rules and permissions.

**What to build:**
- World creators can write world rules
- Show settings page
- Control who can access private locations
- Save settings to database

**Why next?**
- Supports everything that came before
- Makes worlds safer and more organized

---

### PHASE 9: Polish & Modern vs. Old Mode (Weeks 11-12)
Make it look beautiful in both styles.

**What to build:**
- Modern Mode: Make everything look like phone apps
- Old Mode: Make everything look like a book/diary
- Add customization (wallpapers, colors, fonts, stickers)

**Why last?**
- Everything should work in both modes, so build the basics first
- This is about making it pretty, not about making it work

---

### PHASE 10: Testing & Fixing (Week 13+)
Find bugs and make everything work smoothly.

**What to do:**
- Test every feature
- Ask friends to try it
- Fix anything that doesn't work
- Make it faster

---

## The Tech Stack (The Tools We'll Use)

**Frontend (What Users See):**
- React or Vue.js (JavaScript framework - makes interactive pages)
- HTML & CSS (basic webpage structure and styling)

**Backend (The Brains):**
- Node.js with Express (JavaScript server)
- OR Python with Flask/Django (alternative)

**Database (Where We Store Everything):**
- MongoDB (stores data as documents, like filing cabinets)
- OR PostgreSQL (stores data in tables, like spreadsheets)

---

## File Structure (How Your Code is Organized)

```
Roleplay/
├── frontend/           (The website people see)
│   ├── pages/         (Different pages)
│   ├── components/    (Reusable pieces)
│   └── styles/        (Colors, fonts, layout)
├── backend/           (The server that handles data)
│   ├── routes/        (URL paths like /create-world)
│   ├── models/        (How data is structured)
│   └── controllers/   (The code that does things)
├── database/          (Setup for data storage)
└── docs/              (Documentation & guides)
```

---

## Key Definitions (Simple Explanations)

**Frontend:** The part users interact with (buttons, pages, etc.)
**Backend:** The secret code that handles data and logic
**Database:** Digital storage - like a super organized filing cabinet
**Component:** A reusable piece of code (like a button, card, etc.)
**Route:** A URL path on your website
**API:** A way for frontend and backend to talk to each other

---

## Success Metrics (How to Know You're Doing Well)

✅ Users can see worlds on the homepage
✅ Users can create new worlds
✅ Users can create characters
✅ Users can chat in rooms
✅ Worlds remember everything even after refreshing the page
✅ Modern and Old modes look completely different but work the same
