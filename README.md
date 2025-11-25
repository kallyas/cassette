# 🎵 3D Cassette Player - Professional Edition

A stunning, fully interactive 3D cassette player built with Three.js and the Web Audio API. Experience the nostalgia of cassette tapes with modern web technology, featuring real-time audio visualization, playlist support, and a fully rotatable 3D model you can explore from every angle.

![3D Cassette Player](https://img.shields.io/badge/3D-WebGL-brightgreen) ![Audio](https://img.shields.io/badge/Audio-Web%20Audio%20API-blue) ![License](https://img.shields.io/badge/license-MIT-orange)

## ✨ Features

### 🎨 **Fully Interactive 3D Model**
- **360° Rotation**: Drag with your mouse to rotate the cassette player and view it from any angle
- **Realistic Details**:
  - Front panel with cassette window, animated reels, and control buttons
  - Back panel with headphone jack, AUX input, power jack, and control knobs
  - Side-mounted speaker grills with detailed holes
  - Animated magnetic tape between reels
  - Brand label on top
- **Professional Materials**: Enhanced metallic finishes, glass effects, and realistic lighting
- **Dynamic Shadows**: Real-time shadow casting for depth and realism
- **Auto-Rotation Mode**: Optional automatic rotation to showcase the 3D model

### 🎧 **Advanced Audio Features**
- **Multi-File Playlist**: Load multiple audio files and switch between tracks
- **Progress Bar Scrubber**: Click anywhere on the progress bar to jump to that position
- **VU Meters**: Stereo left/right audio level meters with classic green-yellow-red gradient
- **Volume Control**: Smooth volume slider with visual feedback
- **Keyboard Shortcuts**: Full keyboard control for hands-free operation
- **LocalStorage Persistence**: Remembers your volume, theme, and visualization preferences

### 📊 **Real-Time Visualizations**
- **Waveform Display**: Shows the actual audio waveform in real-time
- **Frequency Bars**: 3D frequency spectrum analyzer with 64 bars
- **Toggle Modes**: Switch between waveform, frequency, or no visualization

### 🎨 **Multiple Themes**
- **Night** (Default): Deep blue gradient
- **Sunset**: Purple and pink gradient
- **Ocean**: Blue-teal gradient
- **Forest**: Green gradient

### 🖱️ **Intuitive Controls**
- **Drag & Drop**: Simply drag audio files onto the page to load them
- **Mouse Controls**:
  - Left-click drag: Rotate camera
  - Right-click drag: Pan camera
  - Scroll wheel: Zoom in/out
- **Transport Controls**: Play, Pause, Stop, Previous, Next
- **Playlist Management**: Click tracks to play them directly

## 🚀 Quick Start

### Installation

No installation required! Just open the `index.html` file in any modern web browser.

```bash
# Clone the repository
git clone <repository-url>

# Navigate to the directory
cd cassette

# Open in your browser
open index.html
```

Or simply double-click `index.html` to open it in your default browser.

### Requirements

- **Modern Web Browser** with WebGL support:
  - Chrome 90+ (recommended)
  - Firefox 88+
  - Safari 14+
  - Edge 90+
- **Audio Files**: MP3, WAV, OGG, or any format supported by HTML5 audio

## 📖 Usage Guide

### Loading Audio Files

**Method 1: File Picker**
1. Click the "📁 LOAD AUDIO FILE(S)" button
2. Select one or more audio files from your computer
3. Files will appear in the playlist

**Method 2: Drag & Drop**
1. Drag audio files from your file explorer
2. Drop them anywhere on the page
3. Files will automatically load into the playlist

### Playback Controls

**Using Mouse:**
- Click the ▶ Play button to start playback
- Click ⏸ Pause to pause
- Click ⏹ Stop to stop and reset
- Click ⏮ Previous or ⏭ Next to navigate tracks
- Click on the progress bar to seek
- Adjust the volume slider

**Using Keyboard:**
| Key | Action |
|-----|--------|
| `SPACE` | Play/Pause |
| `S` | Stop |
| `←` | Previous track |
| `→` | Next track |
| `↑` | Volume up (+5%) |
| `↓` | Volume down (-5%) |

### 3D Camera Controls

| Control | Action |
|---------|--------|
| Left-click drag | Rotate around cassette |
| Right-click drag | Pan camera position |
| Scroll wheel | Zoom in/out |
| Auto-Rotate checkbox | Enable automatic rotation |

### Customization

**Visualization Modes:**
- **Waveform**: Shows the audio wave shape
- **Frequency**: Shows frequency spectrum as 3D bars
- **Off**: No visualization (better performance)

**Themes:**
Choose from 4 beautiful background gradients to match your mood:
- Night (default)
- Sunset
- Ocean
- Forest

**Settings Persistence:**
Your preferences are automatically saved and restored:
- Volume level
- Visualization mode
- Theme selection
- Auto-rotation state

## 🎯 Technical Details

### Technologies Used

- **Three.js** (r128): 3D rendering and WebGL graphics
- **OrbitControls**: Smooth camera manipulation
- **Web Audio API**: Audio processing and analysis
- **HTML5 Audio**: Audio playback
- **localStorage API**: Settings persistence
- **Drag & Drop API**: File loading

### Architecture

```
├── 3D Scene (Three.js)
│   ├── Camera (Perspective)
│   ├── Lights (Ambient, Directional, Point)
│   ├── Cassette Model
│   │   ├── Body & Panels
│   │   ├── Reels & Tape
│   │   ├── Buttons & Display
│   │   ├── Back Connectors
│   │   └── Speaker Grills
│   └── Visualization
│       ├── Waveform Line
│       └── Frequency Bars
│
├── Audio Pipeline
│   ├── MediaElementSource
│   ├── ChannelSplitter (Stereo)
│   ├── Analysers (Left/Right/Main)
│   └── Destination (Output)
│
└── UI Components
    ├── Control Panel
    ├── Playlist
    ├── VU Meters
    └── Info Panel
```

### Performance Optimizations

- **Efficient Rendering**: 60 FPS target with optimized geometry
- **Texture-less Materials**: Using procedural colors for smaller file size
- **Single HTML File**: No external dependencies (except CDN libraries)
- **Conditional Rendering**: Visualizations only update when playing
- **Optimized Shadows**: Soft shadows with appropriate resolution

## 🎨 Customization Guide

### Changing Colors

To customize the theme colors, modify the CSS gradients in the `<style>` section:

```css
body.theme-custom {
    background: linear-gradient(135deg, #yourcolor1 0%, #yourcolor2 100%);
}
```

### Adjusting 3D Model

To modify the cassette dimensions, edit the geometry parameters in `createCassettePlayer()`:

```javascript
const bodyGeometry = new THREE.BoxGeometry(width, height, depth);
```

### Adding New Visualizations

Extend the visualization modes in `createVisualization()` and `updateVisualization()`:

```javascript
// Add your custom visualization logic
if (vizMode === 'custom') {
    // Your code here
}
```

## 🐛 Troubleshooting

### Audio Not Playing
- **Issue**: Browser auto-play restrictions
- **Solution**: Click the play button manually after loading the file

### Visualization Not Working
- **Issue**: Audio context suspended
- **Solution**: Browser requires user interaction before audio processing starts

### 3D Model Not Rotating
- **Issue**: Auto-rotate enabled but not working
- **Solution**: Ensure the checkbox is checked and refresh the page

### Poor Performance
- **Issue**: Low FPS or lag
- **Solutions**:
  - Turn off visualization (select "Off" mode)
  - Close other browser tabs
  - Update your graphics drivers
  - Use a desktop browser instead of mobile

## 📱 Browser Compatibility

| Browser | Version | Status |
|---------|---------|--------|
| Chrome | 90+ | ✅ Full support |
| Firefox | 88+ | ✅ Full support |
| Safari | 14+ | ✅ Full support |
| Edge | 90+ | ✅ Full support |
| Opera | 76+ | ✅ Full support |
| Mobile Safari | 14+ | ⚠️ Limited (no WebGL2) |
| Mobile Chrome | 90+ | ⚠️ Limited (performance) |

## 🤝 Contributing

Contributions are welcome! Here are some ideas for improvements:

- [ ] Add equalizer controls (bass, treble, mid)
- [ ] Implement shuffle and repeat modes
- [ ] Add recording functionality
- [ ] Support for streaming audio URLs
- [ ] More visualization types (circular, particle effects)
- [ ] Custom cassette skins/themes
- [ ] Export visualization as video
- [ ] MIDI controller support
- [ ] Bluetooth audio output

### Development Setup

1. Fork the repository
2. Make your changes to `index.html`
3. Test in multiple browsers
4. Submit a pull request with a description of your changes

## 📄 License

This project is licensed under the MIT License - feel free to use it for personal or commercial projects.

```
MIT License

Copyright (c) 2025

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 🙏 Acknowledgments

- **Three.js**: Amazing 3D library that powers the visuals
- **Web Audio API**: For real-time audio processing capabilities
- **OrbitControls**: For intuitive camera manipulation
- **Retro Audio Equipment**: Inspiration for the design

## 📞 Support

If you encounter any issues or have questions:

1. Check the [Troubleshooting](#-troubleshooting) section
2. Review [Browser Compatibility](#-browser-compatibility)
3. Open an issue on GitHub with:
   - Browser name and version
   - Operating system
   - Description of the problem
   - Steps to reproduce

## 🎉 Features Roadmap

### Version 2.0 (Planned)
- [ ] Mobile-optimized touch controls
- [ ] Fullscreen mode
- [ ] Screenshot/share functionality
- [ ] Audio effects (reverb, echo, distortion)
- [ ] Cassette label customization
- [ ] Multiple cassette player models

### Version 3.0 (Future)
- [ ] Multiplayer DJ mode
- [ ] Cloud playlist storage
- [ ] Social sharing features
- [ ] VR support
- [ ] AI-powered music recommendations

---

<div align="center">

**Made with ❤️ and JavaScript**

[⭐ Star this project](https://github.com/yourusername/cassette-player) if you find it useful!

</div>
