# 🎄 Christmas Magic - GitHub Pages Version

An interactive 3D Christmas tree with your photos as ornaments!

## 🚀 Quick Start - Host on GitHub Pages (FREE)

### Step 1: Create GitHub Repository

1. Go to [github.com](https://github.com) and sign in
2. Click **"New repository"** (green button)
3. Name it: `christmas-magic` (or any name you like)
4. Select **Public**
5. Click **"Create repository"**

### Step 2: Upload Files

**Option A: Upload via GitHub Website**
1. Click **"uploading an existing file"**
2. Drag and drop these files:
   ```
   index.html
   images.json (optional)
   images/
     ├── 1.jpg
     ├── 2.jpg
     └── ... your photos
   ```
3. Click **"Commit changes"**

**Option B: Using Git Command Line**
```bash
# Clone your repo
git clone https://github.com/YOUR_USERNAME/christmas-magic.git
cd christmas-magic

# Copy files
cp /path/to/index.html .
mkdir images
cp /path/to/your/photos/*.jpg images/

# Push to GitHub
git add .
git commit -m "Add Christmas Magic"
git push
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top menu)
3. Click **Pages** (left sidebar)
4. Under "Source", select **"Deploy from a branch"**
5. Select branch: **main**, folder: **/ (root)**
6. Click **Save**
7. Wait 1-2 minutes...

### Step 4: Access Your Site! 🎉

Your site will be live at:
```
https://YOUR_USERNAME.github.io/christmas-magic/
```

---

## 📁 File Structure

```
christmas-magic/
├── index.html          # Main page (required)
├── images.json         # Image list (optional)
└── images/             # Your photos folder
    ├── 1.jpg
    ├── 2.jpg
    ├── 3.jpg
    └── ...
```

---

## 🖼️ Adding Your Photos

### Method 1: Numbered Images (Easiest)

1. Rename your photos to: `1.jpg`, `2.jpg`, `3.jpg`, etc.
2. Put them in the `images/` folder
3. Edit `index.html`, find this line:
   ```javascript
   const IMAGE_LIST = Array.from({length: 20}, (_, i) => `images/${i + 1}.jpg`);
   ```
4. Change `20` to your actual number of photos

### Method 2: Using images.json (More Flexible)

1. Create `images.json` with your image paths:
   ```json
   [
       "images/family-photo.jpg",
       "images/christmas-2023.png",
       "images/holiday-dinner.jpg"
   ]
   ```

2. Edit `index.html`, change:
   ```javascript
   const USE_EXTERNAL_JSON = true;  // Change false to true
   ```

### Method 3: External Image URLs

You can also use URLs from other sites:
```json
[
    "https://example.com/photo1.jpg",
    "https://i.imgur.com/abc123.jpg"
]
```

---

## ⚙️ Configuration

Edit these values in `index.html`:

```javascript
// Number of images (if using numbered method)
const IMAGE_LIST = Array.from({length: 50}, (_, i) => `images/${i + 1}.jpg`);
//                                    ↑ Change this number

// Or use external JSON
const USE_EXTERNAL_JSON = true;  // Set to true to use images.json

// Performance settings
imageLoading: {
    batchSize: 2,              // Images loaded at once
    delayBetweenBatches: 150,  // Delay in ms
    maxImages: 200,            // Maximum images
}
```

---

## ❓ Troubleshooting

### Images not loading?

1. **Check file names**: Must match exactly (case-sensitive)
2. **Check paths**: Should be `images/photo.jpg` not `/images/photo.jpg`
3. **Check file format**: Use `.jpg`, `.jpeg`, `.png`, `.webp`
4. **Check file size**: Very large images (>5MB) may fail

### Site not updating?

1. GitHub Pages can take 1-5 minutes to update
2. Try hard refresh: `Ctrl+Shift+R` (Windows) or `Cmd+Shift+R` (Mac)
3. Check Actions tab for deployment status

### CORS errors?

If using external URLs, they must allow cross-origin requests.
Use your own images in the `images/` folder to avoid this.

---

## 🎨 Customization

### Change Title
Find and edit:
```html
<h1 class="landing-title">🎄 Christmas Magic 🎄</h1>
```

### Change Colors
Find `CONFIG.colors`:
```javascript
colors: {
    bg: 0x000000,           // Background (black)
    champagneGold: 0xffd966, // Gold accents
    deepGreen: 0x03180a,     // Green ornaments
    accentRed: 0x990000,     // Red ornaments
}
```

### Change Music
Find and replace the audio URL:
```html
<audio id="bgMusic" loop>
    <source src="YOUR_MUSIC_URL.mp3" type="audio/mpeg">
</audio>
```

---

## 🔧 Local Development

To test locally before uploading:

```bash
# Option 1: Python
python -m http.server 8000
# Open http://localhost:8000

# Option 2: Node.js
npx serve .
# Open http://localhost:3000

# Option 3: VS Code
# Install "Live Server" extension
# Right-click index.html → "Open with Live Server"
```

---

## 📱 Browser Support

| Browser | Status |
|---------|--------|
| Chrome | ✅ Best |
| Edge | ✅ Best |
| Firefox | ✅ Good |
| Safari | ✅ Good |
| Mobile Chrome | ✅ Good |
| Mobile Safari | ⚠️ May be slow |

---

## 🎄 Credits

Made with ❄️ for the holidays!

---

## 📄 License

Free to use for personal projects. Have a Merry Christmas! 🎅
