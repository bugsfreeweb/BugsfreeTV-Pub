# 📺 Bugsfree IPTV Pro-Web Player (SmartTV)

A feature-rich, responsive web-based IPTV player with support for modern streaming protocols, TV/Smart TV remote control navigation, and cross-device compatibility.

## ✨ Features

### Core Playback
- **Multi-Protocol Support**: HLS (m3u8) and DASH (mpd) streaming with automatic format detection
- **Dual Player Engines**: HLS. js and DASH.js with auto-fallback capability
- **Flexible Input**: Load M3U/M3U8 playlists from URLs or local files

### TV & Smart TV Support
- **Automatic TV Detection**: Detects Samsung TV, Android TV, Google TV, LG WebOS, Tizen, and more
- **Remote Control Navigation**: Full remote control support with arrow keys, OK/Enter, and volume controls
- **TV Mode UI**: Optimized interface for large screens with TV-focused navigation
- **Home Screen Grid Navigation**: Card-based navigation system for remote control

### Playlist Management
- **Multiple Playlists**: Add, manage, and switch between multiple playlists
- **Live Playlist Updates**: Refresh playlists from URLs on-demand
- **Persistent Storage**: Auto-save playlists and playback preferences using browser localStorage

### Channel Features
- **Favorites System**: Mark channels as favorites for quick access
- **Smart Search**: Filter channels by name across all playlists
- **Channel Info Display**: View current channel name and position in playlist
- **Logo Support**: Display channel logos from M3U metadata (with fallback SVG placeholder)

### User Interface
- **Responsive Design**: Optimized for desktop, tablet, and mobile devices
- **Auto-Fullscreen**: Automatic fullscreen mode for desktop and landscape mobile
- **Auto-Hiding Controls**: Mini dock control panel auto-hides with activity detection
- **Dark/Light Theme Toggle**: User-customizable theme preference
- **Orientation Detection**: Handles device orientation changes seamlessly

### Playback Controls
- **Auto-Resume**: Remembers last played channel and resumes on app reload
- **Quick Navigation**: Arrow keys to switch between channels
- **Volume Control**: Adjustable volume with visual indicator
- **Mute Toggle**: Quick mute/unmute functionality
- **Full Keyboard Support**: Spacebar to play/pause, F for fullscreen, M for mute

### TV Remote Controls
| Button | Action |
|--------|--------|
| Arrow Keys | Navigate menu / Change channels |
| OK/Enter | Select / Play channel |
| CH+/CH- | Next/Previous channel |
| VOL+/VOL- | Increase/Decrease volume |
| Mute | Toggle audio mute |
| Play/Pause | Control playback |
| Stop | Return to home |
| Back/Return | Go back / Exit fullscreen |
| Info | Show channel information |

## 🚀 Getting Started

### Installation

1. Clone the repository:
```bash
git clone https://github.com/bugsfreeweb/bugsfreetv.git
cd bugsfreetv
```

2. Open in a web server:
```bash
# Using Python 3
python -m http.server 8000

# Using Node.js http-server
npx http-server

# Using PHP
php -S localhost:8000
```

3. Open in your browser:
```
http://localhost:8000
```

### Adding Playlists

#### Method 1: From URL
1. Click "Add Playlist" (Remote button)
2. Enter playlist name
3.  Paste M3U/M3U8 URL
4. Wait for parsing to complete

#### Method 2: Local File
1. Use file upload interface
2. Select M3U/M3U8 file from device
3. File is automatically parsed and imported

#### Method 3: Refresh Existing
- Click the sync icon on any URL-based playlist to refresh channels

## 📋 M3U Format Support

The player supports standard M3U8 format with the following metadata:

```
#EXTINF:-1,tvg-logo="http://example.com/logo.png",Channel Name
http://streaming-url.example.com/stream.m3u8

#EXTINF:-1,tvg-logo="http://example. com/logo2.png",Another Channel
http://dash-url.example.com/manifest.mpd
```

### Supported Metadata Tags
- `tvg-logo` - Channel logo URL (displayed in UI)
- Channel name (displayed in playlists and playback)

## 🎮 Navigation & Controls

### Desktop/Web Browser
- **Escape / Backspace** - Go to home
- **↑ / ↓** - Previous/next channel (while playing)
- **Space** - Play/Pause
- **F** - Toggle fullscreen
- **M** - Toggle mute
- **?** - Show keyboard help

### TV Remote Control
- **Arrow Keys** - Navigate menus / Switch channels
- **OK/Select** - Confirm / Play channel
- **Volume Up/Down** - Adjust volume
- **Mute** - Toggle audio
- **Play/Pause** - Control playback
- **Stop** - Return to home

## 💾 Data Persistence

All user data is stored locally in the browser:
- **Playlists**: Complete playlist data and metadata
- **Favorites**: Saved channel favorites
- **Last Played**: Resume point on app restart
- **Theme**: User's theme preference
- **Player Engine**: Selected playback engine

Data is stored in `localStorage` and persists across browser sessions.

## 🌐 Browser Compatibility

- ✅ Chrome/Chromium 60+
- ✅ Firefox 55+
- ✅ Safari 12+
- ✅ Edge 79+
- ✅ Smart TV Browsers (WebOS, Tizen, Android TV)

## 📦 Dependencies

### External Libraries
- **HLS.js** - HLS protocol streaming support
- **DASH.js** - DASH/MPEG-DASH protocol streaming support
- **Font Awesome** - Icon library for UI controls

### Browser APIs Used
- Fetch API - Playlist loading
- localStorage - Data persistence
- Fullscreen API - Fullscreen mode
- Media Element API - Video playback
- Keyboard Events - Control handling

## ⚙️ Configuration

### Player Engine Selection
The application automatically detects and uses the best available player:
- **Auto** (Default) - Automatic selection based on URL format
- **HLS.js** - Force HLS protocol handling
- **DASH.js** - Force DASH protocol handling
- **Native** - Use browser's native HTML5 video player

### Device Detection
The app automatically detects:
- Desktop vs mobile devices
- Portrait vs landscape orientation
- TV and Smart TV devices
- Available screen size and capabilities

## 🎨 Customization

### Theme Colors
Modify CSS variables to customize appearance:
```css
--primary: #color
--accent: #color
--danger: #color
--bg: #color
--text: #color
```

### Adding Custom Channels
Edit playlists directly through the UI or import pre-configured M3U files.

## 🐛 Troubleshooting

### Playlist Won't Load
- Verify the M3U/M3U8 URL is accessible and contains valid stream links
- Check browser console for CORS or network errors
- Ensure the file format is valid

### Streams Not Playing
- Verify the stream URL is active and accessible
- Check that your browser supports the streaming protocol (HLS or DASH)
- Try switching the player engine in settings
- Check for region blocking or DRM restrictions

### Remote Control Not Working
- Ensure TV mode is properly detected (check browser console)
- Verify your device/TV remote is sending keyboard events
- Try pressing arrow keys and Enter to test remote input

### Fullscreen Not Working
- Some browsers restrict fullscreen on insecure contexts (non-HTTPS)
- Check browser permissions for fullscreen requests
- Try using HTTPS to enable all features

## 📱 Device Support

### Tested Devices
- Desktop (Windows, macOS, Linux)
- Tablets (iPad, Android tablets)
- Mobile (iOS Safari, Android Chrome)
- Smart TVs:
  - Samsung Smart TV
  - LG WebOS
  - Android TV
  - Google TV
  - Tizen
  - Netcast

## 📄 License

[Your License Here]

## 🤝 Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📞 Support

For issues, feature requests, or questions:
- Open an GitHub issue
- Check existing issues for solutions
- Review the troubleshooting section

## 🙏 Acknowledgments

- HLS.js team for excellent streaming support
- DASH.js community for MPEG-DASH implementation
- Font Awesome for UI icons

---

**Last Updated**: 27-11-2025
**Version**: 1.0.0
