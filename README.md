# Linux Desktop on GitHub Actions

A disposable Linux GUI environment for visual browser testing and debugging via Chrome Remote Desktop.

## Setup Instructions

### 1. Get Your Chrome Remote Desktop Authorization Code

1. Visit: **https://remotedesktop.google.com/headless**
2. Click **"Begin"** → **"Next"** → **"Authorize"**
3. Copy the authorization code from the displayed command
   - It looks like: `--code="4/xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"`
   - Copy only the code part (without quotes)

### 2. Run the Workflow

1. Go to your GitHub repository → **Actions** tab
2. Select **"Linux Desktop with Chrome Remote Desktop"**
3. Click **"Run workflow"**
4. Paste your authorization code in the `CRP_CODE` field
5. Click **"Run workflow"**

### 3. Connect to Your Desktop

1. Visit: **https://remotedesktop.google.com/access**
2. Find **"GitHub Actions Linux Desktop"** in the list
3. Click on it
4. Enter PIN: `123456`
5. You're now connected to the remote desktop!

## Features

- **OS**: Ubuntu Latest (22.04/24.04)
- **Desktop**: XFCE4 (lightweight and stable)
- **Terminal**: xfce4-terminal included
- **Runtime**: 6 hours maximum (GitHub Actions limit)
- **Access**: High-performance via Chrome Remote Desktop

## Use Cases

- Visual browser testing
- GUI application debugging
- Remote development environment
- Running GUI-based automation tools

## Security Notes

- The PIN is set to `123456` (static)
- The authorization code expires after use
- The runner automatically terminates after 6 hours
- Each run generates a new, isolated environment

## File Structure

```
.github/workflows/linux-desktop.yml    # Main workflow file
```

## Requirements

- GitHub repository with Actions enabled
- Google account for Chrome Remote Desktop
- Chrome browser or Chrome Remote Desktop app
