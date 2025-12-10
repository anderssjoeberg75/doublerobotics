#doublerobotics

#update
sudo apt update && sudo apt upgrade -y

# required packages
sudo apt install -y ffmpeg v4l-utils

# if you want libcamera support (Pi Camera module)

on modern Raspberry Pi OS, libcamera-apps are usually installed; if not:
sudo apt install -y libcamera-apps

# Install node (example Node 20 LTS)
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt install -y nodejs build-essential

# Create project dir
mkdir -p ~/pi-stream && cd ~/pi-stream

# Copy the files server.js, package.json, public/index.html as above.
npm install

# Export credentials (recommended)
export STREAM_USER=pi
export STREAM_PASS=strongpasswordhere
# Or add to systemd service file (below)

# Start
node server.js
# Check logs; open http://<pi-ip>:3000/ in browser. Browser will prompt for HTTP basic auth.
