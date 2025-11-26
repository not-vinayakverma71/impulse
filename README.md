# Impulse - AI-Powered Code Editor for Linux

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Linux-orange.svg)]()

**Impulse** is a powerful, self-contained AI-powered code editor with built-in Language Server Protocol (LSP) support and integrated Linux automation tools.

## 🚀 Quick Start (3 Commands)

```bash
# 1. Extract the package
tar -xzf impulse-standalone-20251126.tar.gz

# 2. Enter the directory
cd impulse-standalone-20251126

# 3. Run Impulse
./impulse
```



## 🖥️ Desktop Integration (Optional)

To add Impulse to your application menu:

```bash
cd impulse-standalone-20251126
./register.sh
```

Now you can launch Impulse from your application menu!

## 📋 System Requirements

- **OS:** Linux (x86_64)
- **RAM:** 4GB minimum, 8GB recommended
- **Disk:** 300MB for installation
- **Libraries:** Standard glibc, GTK3 (pre-installed on most systems)


## 🛠️ Advanced Installation

### System-Wide Installation

```bash
# Extract
tar -xzf impulse-standalone-20251126.tar.gz
cd impulse-standalone-20251126

# Install to /usr/local (requires sudo)
sudo cp bin/* /usr/local/bin/
sudo chmod +x /usr/local/bin/impulse /usr/local/bin/language_server_impulse_x64

# Now run from anywhere
impulse
```

### User-Local Installation

```bash
# Extract
tar -xzf impulse-standalone-20251126.tar.gz
cd impulse-standalone-20251126

# Install to ~/.local
mkdir -p ~/.local/bin
cp bin/impulse bin/language_server_impulse_x64 ~/.local/bin/

# Add to PATH (add to ~/.bashrc for persistence)
export PATH="$HOME/.local/bin:$PATH"

# Run
impulse
```

## 🔑 API Keys

API keys are pre-configured and included in the package. The editor will work immediately with AI features enabled.

If you need to use your own API keys:
1. Edit the `.env` file in the package directory
2. Add your keys:
   ```
   GEMINI_API_KEY=your_key_here
   OPENAI_API_KEY=your_key_here
   ```

## 📝 Logs & Debugging

Logs are stored in:
- **Main logs:** `~/.local/share/lapce-debug/logs/lapce.*.log`
- **LSP logs:** `~/.local/share/lapce-debug/logs/lsp_server.log`
- **Startup log:** `/tmp/impulse_startup.log`
- **Backend log:** `/tmp/impulse_backend.log`

## 🔄 Updating

To update to a new version:
1. Download the new tarball
2. Extract to a new directory or overwrite the old one
3. Re-run `./register.sh` if using desktop integration

## 🗑️ Uninstallation

### If using portable version:
```bash
rm -rf impulse-standalone-20251126
rm ~/.local/share/applications/impulse-portable.desktop
update-desktop-database ~/.local/share/applications/
```

### If installed system-wide:
```bash
sudo rm /usr/local/bin/impulse /usr/local/bin/language_server_impulse_x64
```

### If installed to ~/.local:
```bash
rm ~/.local/bin/impulse ~/.local/bin/language_server_impulse_x64
```

## 🐛 Troubleshooting

### LSP not starting
```bash
# Check logs
tail -f /tmp/impulse_backend.log

# Manually start LSP to see errors
cd impulse-standalone-20251126
./bin/language_server_impulse_x64
```

### Application won't launch
```bash
# Check startup log
cat /tmp/impulse_startup.log

# Check for missing libraries
ldd impulse-standalone-20251126/bin/impulse
```

### API keys not working
```bash
# Verify .env file exists
ls -la impulse-standalone-20251126/.env

# Check if keys are loaded
grep GEMINI_API_KEY /tmp/impulse_startup.log
```

## 🤝 Support

For issues, questions, or feature requests:
- **GitHub:** [not-vinayakverma71/impulse](https://github.com/not-vinayakverma71/impulse)
- **Email:** Support available through GitHub issues
.


