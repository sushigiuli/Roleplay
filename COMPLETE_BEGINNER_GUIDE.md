# 🎮 How to Build Your Roleplay Website - Complete Step-by-Step Guide

**This guide is written for a 13-year-old.** Follow every step exactly, clicking where it tells you to click.

---

## PART 1: Install the Programs You Need

This is like downloading games before you can play them!

### Step 1: Install Node.js

1. **Open your web browser** (Chrome, Firefox, Safari, Edge - any browser)
2. **Go to this website:** `https://nodejs.org`
3. **You'll see two big buttons.** Click the one that says **"LTS"** (it's usually on the left)
   - LTS means "Long Term Support" - it's the safe, stable version
4. **It will download a file.** Wait for it to finish.
5. **Click on the downloaded file** to start installing it
   - On Windows: Look for a file named something like `node-v20.x.x-x64.msi`
   - On Mac: Look for a file named something like `node-v20.x.x.pkg`
6. **Follow the installation wizard** - just click "Next" and "Install" until it's done
7. **Restart your computer** to make sure everything is installed

**To check if it worked:**
- Open your **Terminal** or **Command Prompt**
  - On Windows: Press `Windows Key + R`, type `cmd`, press Enter
  - On Mac: Press `Cmd + Space`, type `terminal`, press Enter
  - On Linux: Open Terminal from your applications
- Type this exactly: `node --version`
- Press Enter
- You should see a version number like `v20.10.0`

---

### Step 2: Install Visual Studio Code (Your Code Editor)

1. **Go to this website:** `https://code.visualstudio.com`
2. **Click the blue "Download" button** in the middle of the page
3. **Choose your operating system** (Windows, Mac, or Linux)
4. **Open the downloaded file** and follow the installation steps
5. **Click "Install"** and wait for it to finish
6. **Open Visual Studio Code** when it's done
   - You should see a welcome screen with a blue icon

---

### Step 3: Install Git

1. **Go to this website:** `https://git-scm.com`
2. **Click "Download"** (it will automatically detect your operating system)
3. **Open the downloaded file**
4. **Click "Next" through the installation**
5. **When asked about your editor**, make sure "Visual Studio Code" is selected
6. **Finish the installation**

**To check if it worked:**
- Open Terminal/Command Prompt again
- Type: `git --version`
- Press Enter
- You should see a version number

---

### Step 4: Create a GitHub Account

1. **Go to this website:** `https://github.com/signup`
2. **Click in the "Email" box** and type your email address
3. **Click "Create account"**
4. **You'll see a screen asking you to create a password.** Type a strong password
5. **Enter your username** - this is what people will see
   - Try something like `yourname-roleplay` or `yourname123`
   - (You already have one: `sushigiuli`)
6. **Confirm you're not a robot** (solve the puzzle if it asks)
7. **Click "Create account"**
8. **GitHub will send you an email.** Click the link in that email to verify

---

## PART 2: Set Up Your Project on Your Computer

### Step 1: Create a Folder for Your Project

1. **Open File Explorer** (Windows) or **Finder** (Mac)
2. **Go to your Documents folder**
3. **Right-click in the empty space** and select **"New Folder"**
4. **Name the folder:** `Roleplay`
5. **Double-click to open it**

---

### Step 2: Open Terminal in Your Project Folder

**On Windows:**
1. Press `Ctrl + L` to select the address bar in File Explorer
2. Type: `cmd`
3. Press Enter
4. You should see a black Terminal window

**On Mac:**
1. Open Terminal (Command + Space, type "terminal")
2. Type: `cd ~/Documents/Roleplay`
3. Press Enter

**On Linux:**
1. Right-click in your file manager and select "Open Terminal Here"

---

### Step 3: Create the Folder Structure

**In your Terminal, copy-paste these commands one at a time, pressing Enter after each:**

```bash
mkdir frontend
mkdir backend
mkdir database
mkdir docs
```

After each command, you'll see a new line appear. This is normal!

---

### Step 4: Set Up the Frontend (The Part Users See)

**In Terminal, type:**

```bash
cd frontend
npm create vite@latest . -- --template react
```

**It will ask:** "Need to install the following packages: create-vite@latest"

**Type:** `y` and press Enter

**Wait for it to finish.** You'll see lots of text appearing. This is normal!

**Then type:**

```bash
npm install
```

**Wait again.** This installs all the tools needed.

---

### Step 5: Set Up the Backend (The Brain of Your Website)

**In Terminal, go back to the main folder:**

```bash
cd ..
cd backend
```

**Then type:**

```bash
npm init -y
```

This creates a configuration file. Just press Enter if it asks any questions.

**Then install what the backend needs:**

```bash
npm install express cors dotenv
```

Wait for it to finish.

---

### Step 6: Create Your First Files

**Go back to your main folder:**

```bash
cd ..
```

**Open Visual Studio Code with your project:**

```bash
code .
```

Visual Studio Code should open with your project. On the left side, you should see your folders listed.

---

## PART 3: Build the Homepage (Phase 1)

Now we're going to create the actual website pages!

### File 1: Create the World Card Component

**In Visual Studio Code:**

1. **Look at the left side** - you should see a folder tree
2. **Click the small arrow next to "frontend"** to expand it
3. **Click the arrow next to "src"** to expand it
4. **Right-click on "src"** and select **"New Folder"**
5. **Name it:** `components`
6. **Right-click on "components"** and select **"New File"**
7. **Name it:** `WorldCard.jsx`
8. **Click inside the file** and paste this code:

```javascript
import React from 'react';
import '../styles/WorldCard.css';

function WorldCard({ world }) {
  return (
    <div className="world-card">
      <div className="world-image">
        <img src={world.coverImage} alt={world.name} />
      </div>
      <div className="world-info">
        <h3>{world.name}</h3>
        <div className="world-meta">
          <span className="mode">{world.mode}</span>
          <span className="language">🌍 {world.language}</span>
        </div>
        <div className="world-stats">
          <span className="users">👥 {world.activeUsers} active</span>
          <span className={`visibility ${world.isPublic ? 'public' : 'private'}`}>
            {world.isPublic ? '🔓 Public' : '🔒 Private'}
          </span>
        </div>
      </div>
    </div>
  );
}

export default WorldCard;
```

9. **Press Ctrl + S** (or Cmd + S on Mac) to save

---

### File 2: Create the Styles Folder and CSS

1. **Right-click on "src"** and select **"New Folder"**
2. **Name it:** `styles`
3. **Right-click on "styles"** and select **"New File"**
4. **Name it:** `WorldCard.css`
5. **Paste this code:**

```css
.world-card {
  border: 1px solid #ddd;
  border-radius: 8px;
  overflow: hidden;
  cursor: pointer;
  transition: transform 0.3s ease;
  background: white;
}

.world-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.world-image {
  width: 100%;
  height: 200px;
  overflow: hidden;
}

.world-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.world-info {
  padding: 15px;
}

.world-info h3 {
  margin: 0 0 10px 0;
  font-size: 18px;
}

.world-meta {
  display: flex;
  gap: 10px;
  margin-bottom: 10px;
  font-size: 12px;
}

.mode {
  background: #e0e0ff;
  padding: 3px 8px;
  border-radius: 4px;
  color: #333;
}

.world-stats {
  display: flex;
  justify-content: space-between;
  font-size: 12px;
  color: #666;
}

.visibility.public {
  color: green;
}

.visibility.private {
  color: red;
}
```

6. **Save the file** (Ctrl + S)

---

### File 3: Create the Pages Folder

1. **Right-click on "src"** and select **"New Folder"**
2. **Name it:** `pages`
3. **Right-click on "pages"** and select **"New File"**
4. **Name it:** `Homepage.jsx`
5. **Paste this code:**

```javascript
import React, { useState } from 'react';
import WorldCard from '../components/WorldCard';
import '../styles/Homepage.css';

function Homepage() {
  // FAKE DATA - This is just for testing!
  // Later we'll get real data from the backend
  const [worlds] = useState([
    {
      id: 1,
      name: 'Enchanted Forest',
      coverImage: 'https://via.placeholder.com/300x200?text=Enchanted+Forest',
      mode: 'Old',
      language: 'English',
      activeUsers: 12,
      isPublic: true,
    },
    {
      id: 2,
      name: 'Cyberpunk City',
      coverImage: 'https://via.placeholder.com/300x200?text=Cyberpunk+City',
      mode: 'Modern',
      language: 'English',
      activeUsers: 28,
      isPublic: true,
    },
    {
      id: 3,
      name: 'Royal Palace',
      coverImage: 'https://via.placeholder.com/300x200?text=Royal+Palace',
      mode: 'Old',
      language: 'French',
      activeUsers: 5,
      isPublic: false,
    },
  ]);

  return (
    <div className="homepage">
      {/* Navigation Bar */}
      <nav className="navbar">
        <div className="nav-brand">Roleplay</div>
        <div className="nav-buttons">
          <button className="nav-btn create-btn" title="Create World">➕</button>
          <button className="nav-btn recents-btn" title="Recently Joined">🕐</button>
          <button className="nav-btn profile-btn" title="Profile">👤</button>
        </div>
      </nav>

      {/* Main Content */}
      <main className="main-content">
        <h1>Discover Worlds</h1>
        <div className="worlds-grid">
          {worlds.map(world => (
            <WorldCard key={world.id} world={world} />
          ))}
        </div>
      </main>
    </div>
  );
}

export default Homepage;
```

6. **Save the file** (Ctrl + S)

---

### File 4: Create Homepage Styles

1. **Right-click on "styles"** and select **"New File"**
2. **Name it:** `Homepage.css`
3. **Paste this code:**

```css
.homepage {
  display: flex;
  flex-direction: column;
  height: 100vh;
  background: #f5f5f5;
}

.navbar {
  background: white;
  padding: 15px 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  border-bottom: 2px solid #ddd;
}

.nav-brand {
  font-size: 24px;
  font-weight: bold;
  color: #333;
}

.nav-buttons {
  display: flex;
  gap: 10px;
}

.nav-btn {
  width: 50px;
  height: 50px;
  border: none;
  border-radius: 50%;
  background: #f0f0f0;
  cursor: pointer;
  font-size: 20px;
  transition: background 0.3s ease;
}

.nav-btn:hover {
  background: #e0e0e0;
}

.main-content {
  flex: 1;
  overflow-y: auto;
  padding: 30px;
}

.main-content h1 {
  color: #333;
  margin-bottom: 20px;
}

.worlds-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 20px;
}

@media (max-width: 768px) {
  .worlds-grid {
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  }

  .navbar {
    padding: 10px 20px;
  }
}
```

4. **Save the file** (Ctrl + S)

---

### File 5: Update Your Main App

1. **In VS Code, look for the file called `App.jsx`** in the `src` folder
2. **Click on it to open it**
3. **Delete all the text inside**
4. **Paste this code:**

```javascript
import Homepage from './pages/Homepage';
import './App.css';

function App() {
  return <Homepage />;
}

export default App;
```

5. **Save the file** (Ctrl + S)

---

### File 6: Update App.css

1. **Look for the file called `App.css`** in the `src` folder
2. **Click on it to open it**
3. **Delete all the text inside**
4. **Paste this code:**

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
```

5. **Save the file** (Ctrl + S)

---

## PART 4: Run Your Website!

Now comes the fun part - seeing it work!

### Step 1: Start the Frontend

1. **Open Terminal** (if you don't have one open already)
2. **Navigate to your frontend folder:**

```bash
cd ~/Documents/Roleplay/frontend
```

(Or on Windows: `cd Documents\Roleplay\frontend`)

3. **Type this command:**

```bash
npm run dev
```

4. **Wait for it to finish loading.** You'll see something like:

```
VITE v5.0.0  ready in 123 ms

➜  Local:   http://localhost:5173/
```

---

### Step 2: Open Your Website in Your Browser

1. **Open your web browser** (Chrome, Firefox, etc.)
2. **In the address bar, type:** `http://localhost:5173`
3. **Press Enter**

**You should see your website with:**
- ✅ A navigation bar with 3 buttons (+ 🕐 👤)
- ✅ "Discover Worlds" as the heading
- ✅ Three world cards showing:
  - Enchanted Forest (Old Mode)
  - Cyberpunk City (Modern Mode)
  - Royal Palace (Old Mode, Private)

---

## PART 5: Understanding What You Built

### What Each File Does:

| File | What It Does |
|------|-------------|
| `WorldCard.jsx` | A reusable piece that shows ONE world card |
| `Homepage.jsx` | Shows all the world cards and the navigation |
| `WorldCard.css` | Makes the world cards look pretty (colors, spacing) |
| `Homepage.css` | Makes the homepage look pretty (layout, responsive) |
| `App.jsx` | The main file that runs your website |

### How It Works:

1. **App.jsx** loads the **Homepage**
2. **Homepage** creates fake world data
3. **Homepage** loops through each world and creates a **WorldCard** for each one
4. **CSS files** add all the styling (colors, sizes, animations)

---

## PART 6: Next Steps - What to Learn Next

Congratulations! You've built the homepage! 🎉

**Next, you'll learn to:**

1. **Create the Backend Server** - The "brains" that stores data
2. **Connect Frontend to Backend** - Make them talk to each other
3. **Create a Database** - Save worlds permanently
4. **Let Users Create Worlds** - The world creation form

**Follow the `DEVELOPMENT_ROADMAP.md` file to see all 10 phases!**

---

## Troubleshooting

### Problem: "npm: command not found"
- **Solution:** Node.js didn't install correctly. Restart your computer and try again.

### Problem: "Port 5173 already in use"
- **Solution:** Another program is using that port. Try:
  - Closing other browser tabs
  - Or restart your computer

### Problem: Website doesn't show up
- **Solution:**
  - Make sure Terminal is still running (you should see it in the background)
  - Check that you're going to `http://localhost:5173` (not `localhost:3000`)
  - Press Ctrl + C to stop, then run `npm run dev` again

### Problem: Website looks broken/no styling
- **Solution:**
  - Press F12 to open Developer Tools
  - Look for red error messages
  - Check that all your CSS file names match exactly

---

## Commands You Learned

```bash
node --version                    # Check if Node.js is installed
git --version                     # Check if Git is installed
mkdir foldername                  # Create a new folder
cd foldername                     # Go into a folder
npm init -y                       # Start a new Node.js project
npm install packagename           # Install a tool
npm run dev                       # Start your website (frontend)
npm start                         # Start your website (backend)
code .                           # Open VS Code in current folder
```

---

## You Did It! 🎉

You just built the homepage of your roleplay website!

Next time, we'll add:
- A backend server
- A real database
- World creation functionality
- User accounts

**Keep going - you're doing amazing!**
