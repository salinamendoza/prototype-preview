# Prototype Preview

**Share your prototypes privately with a simple password-protected demo site.**

Perfect for designers and developers who want to share work-in-progress with clients or stakeholders without making it public.

**[Live Demo](https://salinamendoza.github.io/prototype-preview/)** · Password: `demo123`

## What You Get

- **Password protection** — Keep your prototypes private until you're ready to share
- **Beautiful mobile previews** — Desktop visitors see your mobile designs in a realistic phone frame
- **No build tools** — Just HTML files. Drop in your prototypes and go
- **Free hosting** — Works perfectly with GitHub Pages

## Quick Start with Claude Code

The easiest way to set this up is with [Claude Code](https://claude.ai/code). Just tell it what you want:

> "Use the prototype-preview template. Set the password to 'clientdemo2025' and add my prototype files from the /designs folder"

> "Change the password to 'newpassword' and add a new demo called 'Mobile App v2'"

> "Set up GitHub Pages for this repo"

Claude handles all the technical details — generating password hashes, updating config, organizing files.

## Manual Setup

1. **Fork or clone this repo**

2. **Set your password** — Open `index.html` and find the `PASSWORD_HASH` line. Replace it with a hash of your password. (Or just ask Claude Code to do it!)

3. **Add your prototypes** — Drop your HTML files in the `prototypes/` folder

4. **Update the demo list** — Edit the `demos` array in `index.html` to list your prototypes

5. **Deploy** — Enable GitHub Pages in your repo settings, or upload to any web host

## File Structure

```
prototype-preview/
├── index.html              # Password gate + demo list
└── prototypes/
    ├── your-desktop.html   # Your desktop prototype
    ├── your-mobile.html    # Your mobile prototype
    └── mobile-preview.html # Phone frame wrapper (included)
```

## Mobile Preview Magic

For mobile prototypes, use the included phone frame wrapper:

```
prototypes/mobile-preview.html?src=your-mobile.html
```

- **On desktop**: Shows your prototype in a realistic iPhone frame
- **On mobile**: Redirects to the full native experience

## Default Demo Password

The template comes with password `demo123` — change this before sharing!

## License

MIT — Use it however you like.
