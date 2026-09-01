# HAPulse

A calm, modern Home Assistant dashboard — a fully client-side alternative to the default Lovelace UI.

## Features

- Live entity updates via WebSocket
- Auto-builds room layout from HA's area registry
- Music/media control, security panel, automations & scenes, energy monitoring
- Four themes, seven languages, drag-to-reorder edit mode
- Layout saved to HA's per-user storage (syncs across devices, survives browser clears)
- PWA-installable

## Usage

1. Install and start the add-on.
2. Click **Open Web UI** on the add-on page.
3. On first launch, enter your Home Assistant URL and a long-lived access token.
   - Generate a token in HA → Profile → Long-Lived Access Tokens.

## Updating to a New Upstream Version

This add-on uses the prebuilt Docker image published by the upstream HAPulse project. When upstream releases a new version (e.g. `1.5.0`), the add-on will not update automatically — you need to do two things:

### Step 1 — Update the fork

1. Go to your fork on GitHub: `https://github.com/<user>/HAPulse-HAOS`
2. Open `hapulse/config.yaml`
3. Click the pencil (edit) icon
4. Change the `version` line to the new tag:
   ```yaml
   version: "1.5.0"
   ```
5. Commit the change

To find the latest available version, check the upstream image tags at:
`https://github.com/jlnbln/HAPulse/pkgs/container/hapulse`

### Step 2 — Update in Home Assistant

1. Go to **Settings → Add-ons → HAPulse**
2. An **Update** button will appear — click it
3. Home Assistant will pull the new image and restart the add-on

That's it. No rebuilding, no reinstalling — the new upstream image is pulled directly.

## Notes

- All configuration is stored in your browser's `localStorage` or in HA's per-user storage — nothing is stored on the server.
- The add-on container is a static nginx server; it does not proxy or log any HA traffic.
- The upstream project publishes new versions at: `https://github.com/jlnbln/HAPulse`
