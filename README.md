# My Remote Desktop Application
This is a Prototype

# Remote Desktop Client

A secure Python-based remote desktop application that allows authorized users to connect to and control Windows computers remotely.

## 🌟 Features

### 🔒 Security-First Design
- **Authorization Required**: Host must explicitly approve each connection attempt
- **User Identification**: Shows the username of the person trying to connect
- **Virus Scanning**: Automatically scans transferred files for malware
- **Permission Prompts**: Ask before accepting potentially infected files

### 🖥️ Remote Control
- **Full Desktop Control**: Complete mouse and keyboard control
- **Real-time Screen Sharing**: Live desktop viewing with auto-refresh
- **High Performance**: Optimized for basic functionality and performance

### 📁 File Transfer
- **Secure File Sharing**: Transfer files, images, videos, and folders
- **Virus Protection**: Integrated antivirus scanning using Windows Defender
- **User Confirmation**: Host can approve/deny file transfers
- **Multiple File Types**: Support for all file formats

## 📋 Requirements

- Windows Operating System
- Python 3.7 or higher
- Network connectivity between host and client computers

## 🚀 Installation

### Method 1: Automatic Setup (Recommended)
1. Download or clone this repository
2. Open PowerShell or Command Prompt
3. Navigate to the `RemoteDesktopApp` folder
4. Run: `python setup.py`
5. Follow the on-screen instructions

### Method 2: Manual Installation
1. Install Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```
   
   Or install packages individually:
   ```bash
   pip install Pillow pyautogui pynput pywin32
   ```

## 📖 Usage

### 🖥️ Host Computer (Being Controlled)

1. **Start the Host Application**
   ```bash
   python host_app.py
   ```

2. **Configure Settings**
   - The application will automatically detect your IP address
   - Click **"Start Host"** to begin listening for connections

3. **Share Connection Details**
   - Share your IP address with the person who wants to connect

4. **Approve Connections**
   - When someone tries to connect, you'll see a dialog asking:
     **"Would You Like To Let '[Username]' Connect?"**
   - Click **"Yes"** to allow the connection or **"No"** to deny it

### 💻 Client Computer (Controlling)

1. **Start the Client Application**
   ```bash
   python client_app.py
   ```

2. **Enter Connection Details**
   - **Host IP Address**: Enter the host computer's IP address
   - **Your Username**: This will be shown to the host for identification

3. **Connect**
   - Click **"Connect"**
   - Wait for the host to approve your connection request

4. **Control the Remote Desktop**
   - Use the **"Remote Desktop"** tab to view and control the host screen
   - Click **"Refresh Screen"** for manual updates
   - Enable **"Auto Refresh"** for continuous screen updates
   - Click, double-click, right-click, and type normally to control the remote computer

5. **Transfer Files**
   - Use the **"File Transfer"** tab
   - **Send files**: Click "Select and Send File" to send files to the host
   - **Receive files**: Click "Request File from Host" and the host can choose a file to send you

## 🔐 Security Features

### Connection Authorization
- Every connection requires explicit approval from the host
- The host sees the connecting user's username before approving
- No automatic connections are allowed

### File Transfer Security
- All transferred files are scanned for viruses using Windows Defender
- If a virus is detected, the host is asked:
  **"This File/Folder '[filename]' has a virus. Would You Still Like To Receive It?"**
- Host can choose to accept or reject infected files

### Network Security
- Uses standard TCP socket communication
- Data is transmitted securely within your local network
- No external servers or cloud services involved

## 🌐 Network Setup

### Same Network (Recommended)
- Both computers should be on the same WiFi network or LAN
- The application will work automatically without additional configuration

### Internet Connection (Advanced)
If you want to connect over the internet:
1. **Port Forwarding**: Configure your router to forward port 9999 to the host computer
2. **Firewall**: Ensure Windows Firewall allows the application
3. **Public IP**: Use the host's public IP address instead of local IP

**⚠️ Warning**: Internet connections require additional security considerations

## 🎛️ Configuration Options

### Host Settings
- **Auto-accept**: Allow automatic connections (NOT recommended for security)

### Client Settings
- **Connection timeout**: 10 seconds by default
- **Screen refresh rate**: 1 second when auto-refresh is enabled
- **Screen resolution**: Automatically scaled to 800x600 for performance

## 🐛 Troubleshooting

### Connection Issues
- **"Connection refused"**: Make sure the host application is running and "Start Host" is clicked
- **"Connection timed out"**: Check network connectivity and firewall settings
- **"Host denied connection"**: The host user clicked "No" when asked to approve your connection

### Performance Issues
- **Slow screen updates**: Use manual refresh instead of auto-refresh
- **Lagging mouse/keyboard**: Check network speed and reduce screen refresh frequency

### File Transfer Issues
- **Virus detected**: The host's antivirus is working - decide whether to accept the file
- **File transfer failed**: Check network connectivity and file permissions

### Installation Issues
- **Missing modules**: Run `python setup.py` or install packages manually
- **Permission errors**: Run PowerShell/Command Prompt as Administrator

## 🔧 Advanced Configuration

### Firewall Configuration
If you're having connection issues, you may need to allow the application through Windows Firewall:
1. Go to Windows Security > Firewall & network protection
2. Click "Allow an app through firewall"
3. Add `python.exe` or the specific application


## 📝 File Structure

```
RemoteDesktopApp/
├── host_app.py          # Host/Server application
├── client_app.py        # Client application
├── setup.py             # Installation and setup script
├── requirements.txt     # Python dependencies
└── README.md           # This documentation file
```

## ⚖️ Legal Disclaimer

This software is intended for legitimate remote access purposes such as:
- Accessing your own computers remotely
- Providing technical support with permission
- Educational and learning purposes

**Important**: Only use this software on computers you own or have explicit permission to access. Unauthorized remote access is illegal and unethical.

## 🤝 Support

If you encounter issues:
1. Check this README for troubleshooting steps
2. Ensure all requirements are installed correctly
3. Verify network connectivity between computers
4. Check firewall and antivirus settings

## 🔄 Version History

### v1.0.0 (Initial Release)
- Basic remote desktop functionality
- File transfer with virus scanning
- Authorization-based connections
- Windows-only support
- GUI interface for both host and client

---

**Made with ❤️ for secure remote desktop access**
