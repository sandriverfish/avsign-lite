# avSign.lite Quick Start Guide

**Get your first display running in 5 minutes!**

Version: 1.0.0-beta (Phase 0)

---

## What You'll Learn

In this quick start, you'll:
- ✅ Upload your first image
- ✅ Create a simple layout
- ✅ Build a basic program
- ✅ Display content on your screen

**Time Required**: 5-10 minutes

---

## Prerequisites

- ✅ avSign.lite installed ([Installation Guide](Installation_Guide.md))
- ✅ Application running
- ✅ Admin interface accessible at http://localhost:8080
- ✅ At least one image or video file ready

---

## Step 1: Upload an Image (1 minute)

1. **Open admin interface** in your browser: `http://localhost:8080`

2. **Login**:
   - Username: `admin`
   - Password: `admin`

3. **Navigate to Resources**:
   - Click **"Resources"** in the navigation menu

4. **Upload your image**:
   - Click **"Upload"** or **"Add Resource"** button
   - Click **"Choose File"** or drag and drop
   - Select an image from your computer (JPG, PNG, etc.)
   - Click **"Upload"**
   - Wait for upload to complete

5. **Verify**:
   - Your image appears in the resource list
   - Thumbnail is visible

✅ **Done!** You have your first resource uploaded.

---

## Step 2: Create a Layout (2 minutes)

You can either use a template or create a custom layout. We'll use a template for speed.

### Option A: Use a Template (Recommended for First Time)

1. **Navigate to Templates**:
   - Click **"Templates"** in the navigation menu

2. **Select "Full Screen" template**:
   - Find the "Full Screen" template
   - Click **"Use Template"** or **"Select"**

3. **Name your layout**:
   - Enter name: "My First Layout"
   - Click **"Save"** or **"Create"**

4. **Verify**:
   - Layout appears in your layouts list
   - Shows one zone covering full screen

### Option B: Create Custom Layout (For Advanced Users)

1. **Navigate to Layouts**:
   - Click **"Layouts"** in navigation menu

2. **Create new layout**:
   - Click **"New Layout"** or **"Create Layout"**
   - **Name**: "My First Layout"
   - **Width**: 1920 (or your screen width)
   - **Height**: 1080 (or your screen height)
   - Click **"Create"**

3. **Add a zone**:
   - Click **"Add Zone"**
   - **Name**: "Main"
   - **X**: 0
   - **Y**: 0
   - **Width**: 1920 (full width)
   - **Height**: 1080 (full height)
   - Click **"Save Zone"**

4. **Save layout**:
   - Click **"Save Layout"**

✅ **Done!** You have a layout ready to use.

---

## Step 3: Create a Program (2 minutes)

A program defines what content displays in each zone.

1. **Navigate to Programs**:
   - Click **"Programs"** in navigation menu

2. **Create new program**:
   - Click **"New Program"** or **"Create Program"**
   - **Name**: "My First Program"
   - **Description**: "Test display" (optional)
   - **Layout**: Select "My First Layout"
   - Click **"Create"**

3. **Add content to the zone**:
   - You'll see your layout with zones
   - Click on the **"Main"** zone (or your zone name)
   - Click **"Add Content"** or **"+"**

4. **Select your image**:
   - **Content Type**: Image
   - **Resource**: Select the image you uploaded
   - **Duration**: 10 seconds (or any duration)
   - Click **"Add"** or **"Save"**

5. **Save program**:
   - Click **"Save Program"**

✅ **Done!** Your program is ready to publish.

---

## Step 4: Add a Terminal (1 minute)

A terminal represents your display device.

1. **Navigate to Terminals**:
   - Click **"Terminals"** in navigation menu

2. **Add terminal**:
   - Click **"Add Terminal"** or **"New Terminal"**
   - **Name**: "Main Display"
   - **Location**: "Office" (optional)
   - **Resolution**: 1920x1080 (or your screen resolution)
   - Click **"Save"**

✅ **Done!** Terminal is registered.

---

## Step 5: Publish and Display (1 minute)

Now, let's display your content!

1. **Navigate to Programs**:
   - Click **"Programs"** in navigation menu

2. **Select your program**:
   - Find "My First Program"
   - Click **"Publish"** or **"Deploy"**

3. **Choose terminal**:
   - Select **"Main Display"**
   - Click **"Publish"** or **"Confirm"**

4. **View your display**:
   - Your image should appear on screen
   - If using same device, open a new browser window
   - Navigate to the display URL (usually shown after publishing)
   - Or press F11 for fullscreen in browser

✅ **Congratulations!** 🎉 Your first digital signage display is live!

---

## What's Next?

### Add More Content

**Create a slideshow**:
1. Upload 3-5 more images
2. Edit your program
3. Click on the zone → Add more content items
4. Each image will display for its set duration, then loop

**Add a video**:
1. Upload a video file (MP4 recommended)
2. Add to your program like an image
3. Video will play and loop automatically

### Try Multi-Zone Layouts

**Use the "Side-by-Side" template**:
1. Go to Templates → Select "Side-by-Side"
2. Create new program with this layout
3. Add different content to left and right zones
4. Publish to see split-screen display

### Explore Templates

Try these pre-built templates:
- **Picture-in-Picture (PIP)**: Main content + logo overlay
- **Quad Dashboard**: Four zones for information displays
- **Video Wall**: Multi-screen configurations

---

## Common Next Steps

### Change Display Duration

1. Go to Programs → Select your program
2. Click on content item
3. Change duration (in seconds)
4. Save and republish

### Update Content

1. Edit your program
2. Add, remove, or reorder content
3. Save
4. Republish to terminal
5. Display updates automatically

### Schedule Content (Coming in Phase 2)

Scheduling features are planned for Phase 2. Currently, all content loops continuously.

---

## Quick Troubleshooting

**Image not displaying:**
- ✅ Check that program is published
- ✅ Verify terminal is active
- ✅ Confirm image uploaded successfully
- ✅ Refresh display page (F5)

**Upload failed:**
- ✅ Check file size (keep under 10MB for images)
- ✅ Verify file format (JPG, PNG supported)
- ✅ Check available storage space

**Layout looks wrong:**
- ✅ Verify layout dimensions match your display
- ✅ Check zone positions and sizes
- ✅ Ensure no overlapping zones

---

## Need More Help?

### Documentation

- **Full User Guide**: [User Guide](User_Guide.md)
- **Installation Help**: [Installation Guide](Installation_Guide.md)
- **Troubleshooting**: [Troubleshooting Guide](Troubleshooting.md)
- **FAQ**: [Frequently Asked Questions](FAQ.md)

### Support

- **GitHub Issues**: [Report bugs](https://github.com/sandriverfish/avsign-lite/issues)
- **Email**: sandriverfish@gmail.com
- **Discussions**: [Ask questions](https://github.com/sandriverfish/avsign-lite/discussions)

---

## Keyboard Shortcuts

Speed up your workflow with these shortcuts:

| Action | Shortcut | Description |
|--------|----------|-------------|
| Save | Ctrl+S | Save current changes |
| Fullscreen | F11 | Toggle fullscreen display |
| Refresh | F5 | Refresh display content |

---

## Tips for Success

**💡 File Organization**
- Use descriptive file names
- Keep files under 10MB for best performance
- Match content resolution to display

**💡 Content Design**
- Use high-contrast colors for readability
- Keep text large (24pt+)
- Test on actual display before deploying

**💡 Performance**
- Start with 3-5 images in playlist
- Use MP4 format for videos
- Optimize image sizes before uploading

---

**You're all set!** 🚀

You've created your first digital signage display. Explore the [User Guide](User_Guide.md) to learn about advanced features.

---

**Happy Signage!**

Visit us: https://github.com/sandriverfish/avsign-lite
