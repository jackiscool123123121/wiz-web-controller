# WiZ Web Controller

A web-based control interface for WiZ smart lights with an animated aurora effect background.

# NOTE
this code is ai writen 

## Features

- Beautiful aurora animation effect with smooth color transitions
- Control WiZ lights via simple web interface
- Color presets (Red, Green, Blue, White)
- Power on/off controls
- Real-time color synchronization
- Built with FastAPI and modern web technologies

## Requirements

- Python 3.11+
- WiZ smart light device on your local network

## Installation

### Step 1: Install Dependencies

Run the installation script:

```bash
install_dependencies.bat
```

This will install all required packages:
- `fastapi` - Web framework
- `pywizlight` - WiZ light library
- `uvicorn` - ASGI server

### Step 2: Configure Your Light

Edit `wiz_web.py` and replace the `BULB_IP` with your WiZ light's IP address:

```python
BULB_IP = "192.168.1.100"  # replace with your light's IP
```

## Running

Simply run the startup script:

```bash
run.bat
```

The web interface will be available at `http://localhost:8000`

## Usage

### Web Interface

1. **Power Controls**: Toggle the light on/off with the ON/OFF buttons
2. **Color Presets**: Click Red, Green, Blue, or White buttons to change colors
3. **Live Updates**: The interface automatically syncs with the light's current state every 4 seconds

### API Endpoints

- `GET /` - Main web interface
- `GET /set?r=255&g=0&b=0` - Set RGB color (values 0-255)
- `GET /white` - Set to warm white (4000K)
- `GET /on` - Turn light on
- `GET /off` - Turn light off
- `GET /status` - Get current status (JSON: power and RGB values)

## Project Structure

```
wiz_web.py              - Main application
wiz_web.py              - Web UI and API endpoints
install_dependencies.bat - Dependency installer
run.bat                 - Server launcher
```

## Troubleshooting

### Connection refused
Make sure your WiZ light is on the same network and the IP address is correct.

### Module not found
Run `install_dependencies.bat` to ensure all packages are installed.

### Port already in use
Change the port in `run.bat` by modifying the uvicorn command:
```bash
py -3.11 -m uvicorn wiz_web:app --reload --port 8001
```

## License

MIT
