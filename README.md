# Linux Desktop on GitHub Actions

A disposable Linux GUI environment for visual browser testing and debugging via VNC/noVNC with ngrok tunnel.

## Overview

This workflow creates a remote Linux desktop (XFCE) accessible through:
- **Web Browser** (noVNC) - no client needed!
- **VNC Client** - using any VNC viewer

## Quick Start

### 1. Run the Workflow

1. Go to **https://github.com/Chadabaz-Cdi/linux/actions**
2. Select **"Linux Desktop with VNC and noVNC"**
3. Click **"Run workflow"**
4. Configure:
   - **VNC_PASSWORD**: Set your password (min 6 characters)
   - **SCREEN_RESOLUTION**: Choose resolution (default: 1920x1080)
5. Click **"Run workflow"**

### 2. Access Your Desktop

After ~30 seconds, the workflow logs will display:

```
🖥️  LINUX DESKTOP READY!
========================================

🔗 Web Browser Access (noVNC):
   https://xxxx.trycloudflare.com/vnc.html

📋 Connection Details:
   Password: your_password
   Resolution: 1920x1080
```

**Click the Cloudflare URL** to open the desktop in your browser!

✅ **No signup required!** Uses free Cloudflare Tunnel (no account needed).

### 3. Connect

**Via Web Browser (Recommended):**
- Click the ngrok URL from the logs
- Click **"Connect"** button
- Enter your password
- Enjoy your Linux desktop!

**Via VNC Client:**
- Host: `localhost` (with SSH tunnel) or use ngrok TCP tunnel
- Port: `5901`
- Password: your configured password

## Features

- **OS**: Ubuntu Latest (22.04/24.04 LTS)
- **Desktop**: XFCE4 (lightweight, fast, stable)
- **Terminal**: xfce4-terminal included
- **Remote Access**: 
  - **noVNC** - Browser-based (no installation needed)
  - **TigerVNC** - Standard VNC protocol
- **Tunnel**: Cloudflare Tunnel (free, no account needed)
- **Runtime**: 6 hours maximum (GitHub Actions limit)

## Included Software

- XFCE4 Desktop Environment
- TigerVNC Server
- noVNC (HTML5 VNC client)
- curl, wget, net-tools
- Web browsers (can install Chrome/Firefox)

## Use Cases

- Visual browser testing
- GUI application debugging
- Remote development environment
- Running GUI-based automation tools
- Testing desktop applications
- Education and tutorials

## Security Notes

- Password is set by you (workflow input)
- ngrok creates a temporary, random public URL
- Connection is SSL encrypted (HTTPS)
- Runner automatically terminates after 6 hours
- Each run creates a fresh, isolated environment

## Troubleshooting

**Can't access the URL?**
- Wait 30-60 seconds after workflow starts
- Check the workflow logs for the ngrok URL
- Refresh the page if it times out

**Connection refused?**
- The desktop takes ~20 seconds to fully start
- Wait a bit and try again

**Slow performance?**
- Try lowering the screen resolution
- Use a VNC client instead of browser for better performance

## Alternative: Direct VNC Connection

If you prefer using a VNC client instead of browser:

1. The workflow exposes VNC on port 5901
2. You can create an SSH tunnel or use ngrok's TCP tunneling
3. Connect with any VNC viewer (RealVNC, TigerVNC, TightVNC, etc.)

## File Structure

```
.github/workflows/linux-desktop.yml    # Main workflow file
README.md                              # This file
```

## Why Not Chrome Remote Desktop?

Chrome Remote Desktop requires OAuth authentication that doesn't work in headless/server environments. This solution uses TigerVNC + ngrok which is the industry standard for remote desktop access on cloud servers.

## License

MIT - Feel free to fork and modify for your needs!
