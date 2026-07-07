# Adding videos

This site has no upload feature and no backend — it is a fully static site. Visitors
can only browse; there is no button, form, or API endpoint anywhere that accepts a
file from the browser. The only way to add a video is to edit this repository locally
and deploy the change.

## Steps

1. Copy the video file into this `videos/` folder (e.g. `videos/my-clip.mp4`).
2. Open `videos/manifest.json` and reference it:

   ```json
   {
     "about": "videos/about.mp4",
     "works": [
       "videos/my-clip.mp4",
       "videos/another-clip.mp4"
     ]
   }
   ```

   - `about` is the single video shown in the "About" section. Set it to `null` to show
     the empty placeholder instead.
   - `works` is the ordered list of videos shown in the "Pieces" filmstrip. The first
     entry auto-plays in the main player.

3. Commit and push. Vercel / Cloudflare Pages (or any static host) redeploys the new
   files automatically, and every visitor sees the update — no per-browser storage,
   no re-uploading.

Removing a video is the same in reverse: delete its entry from `manifest.json` (and the
file, if no longer needed) and redeploy.
