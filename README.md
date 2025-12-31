# Prototype Preview

Password-protected demo site for sharing prototypes with stakeholders.

## Features

- **Password Protection**: SHA-256 client-side hashing keeps your prototypes private
- **Smart Mobile Preview**: Shows phone frame on desktop, redirects to native view on mobile
- **Zero Build Process**: Pure HTML/CSS/JS - no dependencies, no bundlers
- **Easy Hosting**: Works with GitHub Pages, Netlify, or any static hosting

## Quick Start

1. **Clone this repository**
   ```bash
   git clone https://github.com/yourusername/prototype-preview.git
   ```

2. **Set your password hash**

   Generate a SHA-256 hash of your password:
   ```javascript
   // In browser console:
   crypto.subtle.digest('SHA-256', new TextEncoder().encode('your-password'))
     .then(hash => console.log(Array.from(new Uint8Array(hash))
       .map(b => b.toString(16).padStart(2, '0')).join('')))
   ```

   Replace the `PASSWORD_HASH` value in `index.html` with your hash.

3. **Add your prototypes**

   Edit the `demos` array in `index.html`:
   ```javascript
   const demos = [
     { name: "My Desktop App", url: "prototypes/my-app.html" },
     { name: "Mobile Version", url: "prototypes/mobile-preview.html?src=my-mobile.html" }
   ];
   ```

4. **Deploy**

   Push to GitHub and enable GitHub Pages, or upload to any static hosting.

## File Structure

```
prototype-preview/
├── LICENSE
├── README.md
├── index.html                    # Password-protected landing page
└── prototypes/
    ├── example-desktop.html      # Sample desktop prototype
    ├── example-mobile.html       # Sample mobile prototype
    └── mobile-preview.html       # Phone frame wrapper template
```

## Mobile Preview

The `mobile-preview.html` wrapper provides:
- Phone frame display on desktop (430x960 viewport, scaled to 0.86)
- Automatic redirect to native view on mobile devices
- iPhone-style frame with notch

Usage:
```
prototypes/mobile-preview.html?src=your-mobile-prototype.html
```

## Configuration

### Password Hash

In `index.html`, update the `PASSWORD_HASH` constant:
```javascript
const PASSWORD_HASH = 'your-sha256-hash-here';
```

Default password for demo: `demo123`

### Demo List

Customize the demos array to list your prototypes:
```javascript
const demos = [
  { name: "Display Name", url: "path/to/prototype.html" },
  // Add more demos...
];
```

## Security Notes

- Password hashing is client-side only - this provides basic access control, not true security
- Anyone with the hash can access the content
- For sensitive prototypes, consider server-side authentication

## License

MIT License - See [LICENSE](LICENSE) for details.
