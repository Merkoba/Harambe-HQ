# Harambe

Harambe is a self-hosted file-uploading platform designed for sharing media, links, and gathering reactions. Beneath its casual, approachable interface lies a capable and feature-rich system built on a lightweight Python, vanilla JavaScript, SQLite, and Redis stack.

By design, Harambe enforces a strict single-file policy: every post contains either one file or none. When multiple files are uploaded at once, they are automatically bundled into a single `.zip` archive (unless a multi-file media conversion is chosen).

---

## Key Features

### Supported Embeds & Post Types

Harambe supports native, in-browser embeds for a wide range of media and post formats:

- **Image Files**
- **Video Files**
- **Audio Files**
- **Text & Code Files** — with full syntax highlighting and a built-in multi-file Pastebin
- **PDF Documents**
- **Markdown Text**
- **Discussions** — text-only talk posts with titles and descriptions
- **URL Previews & YouTube Embeds** — automatic title, description, and thumbnail fetching, with native YouTube playback
- **Flash Files** — playable directly in modern browsers via Ruffle
- **Archives** — browsable file listings for `.zip`, `.tar`, `.7z`, `.rar`, and more

### Browsing, Discovery & Instant Previews

Exploring hosted content goes well beyond static directories. Harambe provides searchable, sortable, and filterable catalogs for both posts and reactions, alongside quick **Fresh**, **Random**, and **Next** navigation (all filterable by media type) and randomized overview rolls.

To make browsing effortless, Harambe automatically generates lightweight **samples** for every post—resized thumbnails for images and GIFs, frame captures for videos, 10-second audio clips, text excerpts, and archive file listings. Clicking any sample opens a floating preview you can step through with your keyboard before opening the full post.

### Reactions & Live Updates

Users can react to posts using either a large collection of classic reaction icons or full text messages. Post pages periodically refresh in the background so new reactions appear automatically without reloading, and both authors and administrators can edit or delete reactions at any time.

### Magic Conversions & Media Commands

For authorized users, Harambe includes built-in server-side media conversions (**Magic**) powered by `ffmpeg`. Directly during upload, users can:

- Convert images to `.jpg`, audio to `.mp3`, or video to `.mp4`
- Merge multiple audio tracks into a single album `.mp3`
- Combine an image and audio tracks into an `.mp4` video
- Assemble multiple images into an animated `.gif`

Once published, embedded media includes interactive in-browser controls. Visitors can adjust playback speed, pitch, reverb, bass, treble, and fade effects, jump to random timestamps, or rotate and resize images—all without leaving the page.

### Themes & Personalization

Harambe ships with 16 built-in light and dark themes. New users are greeted with an interactive theme gallery where they can filter by tone, preview themes live across the interface, and save their preferred theme—along with custom font family and font size settings—per device.

### Privacy, Accounts & Administration

An account is required to upload files and view the full catalog of hosted content, though administrators can customize visibility to fit their site's needs—including keeping posts public or unlisted, opening or restricting self-registration, and gating sign-ups behind invite codes and built-in CAPTCHAs.

User accounts support granular permissions for uploading, browsing, public listing, reacting, and using Magic conversions, along with per-user file size and upload rate limits. Administrators have access to a dedicated management interface to:

- Review, edit, or delete posts and reactions
- Add, edit, or remove user accounts and adjust permissions
- Read and manage user feedback and reports through a built-in admin inbox

Behind the scenes, Harambe protects your instance with automatic EXIF metadata stripping (while preserving image orientation), SHA-256 duplicate prevention, optional hotlink protection, and automatic storage cleanup when post count or disk quota limits are reached.

---

## Self-Hosting & Configuration

Harambe is easy to tailor through its TOML configuration system. Customizing your instance—including its default theme, banners, favicon, navigation links, and custom static pages (such as Terms of Service and Privacy Policy)—takes only a few adjustments. Most configuration changes are **hot-reloaded automatically at runtime**, so you can update limits, permissions, or branding without restarting the server.

For power users and desktop workflows, Harambe also provides a configurable API upload endpoint and a ready-to-use CLI upload script supporting prompt dialogs, pastebins, Magic conversions, and automatic clipboard copying.

Once configured, deployment is a matter of setting up your web server stack (Apache, Nginx, and Gunicorn), as detailed in the documentation.

---

## Licensing

Harambe is proprietary software, and licenses are available for self-hosting. If you are interested in running your own Harambe instance, please get in touch to discuss licensing arrangements.

**Email:** contact@merkoba.com

---

## Issues

Please use this repository to report any bugs you encounter.