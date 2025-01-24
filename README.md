# VBXModProbe 🔐

[![GitHub](https://img.shields.io/badge/GitHub-0xb0rn3-blue?style=flat&logo=github)](https://github.com/0xb0rn3)

## 🚀 Overview

VBXModProbe is a sophisticated Bash script designed to simplify and optimize VirtualBox installation and configuration on Linux systems. This comprehensive toolkit automates the complex process of setting up virtualization environments, handling dependencies, and ensuring optimal performance.

## ✨ Key Features

- **Automated Dependency Management**: Checks and installs required packages
- **Virtualization Capability Detection**: Verifies CPU virtualization support
- **System Optimization**: Configures GRUB and kernel modules
- **Security Enhancements**: Signs kernel modules and manages potential conflicts
- **Interactive User Experience**: Provides clear, colorful feedback and user confirmations
- **Diagnostic Tools**: Includes verification and diagnostic capabilities

## 🛠 Prerequisites

### System Requirements
- Linux distribution (Debian/Ubuntu recommended)
- Root/sudo access
- x86_64 processor with virtualization support (VMX/SVM)

### Supported Architectures
- Intel and AMD processors with virtualization extensions
- 64-bit Linux systems

## 📦 Dependencies

The script automatically checks and installs the following dependencies:
- VirtualBox
- DKMS (Dynamic Kernel Module Support)
- Linux Kernel Headers
- MOKUtil (Machine Owner Key Utility)
- OpenSSL
- Build Essential tools

## 🔧 Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/0xb0rn3/vbxmodprobe.git
   ```

2. Make the script executable:
   ```bash
   chmod +x vbxmodprobe/vbx
   ```

3. Run with root privileges:
   ```bash
   sudo ./vbx
   ```

## 💡 Usage Options

### Default Mode
```bash
sudo ./vbx
```
Performs a complete VirtualBox setup with interactive confirmation.

### Verification Mode
```bash
sudo ./vbx --verify
```
Checks current VirtualBox configuration and displays system diagnostics.

### Help
```bash
sudo ./vbx --help
```
Displays usage instructions and available options.

## 🔍 What the Script Does

### Detailed Setup Process
1. **Root Privilege Verification**
   - Ensures script runs with administrative rights

2. **Virtualization Capability Check**
   - Analyzes CPU for virtualization support
   - Verifies IOMMU capabilities

3. **Dependency Management**
   - Checks for required packages
   - Installs missing dependencies
   
4. **System Configuration**
   - Disables potential KVM conflicts
   - Optimizes GRUB settings
   - Signs kernel modules
   - Configures VirtualBox environment

5. **Final Verification**
   - Runs comprehensive system diagnostics
   - Confirms successful setup

## ⚠️ Important Considerations

- **Reboot Recommended**: After setup, reboot your system to apply all changes
- **Backup**: Always backup critical system configurations before running
- **Compatibility**: Tested primarily on Debian/Ubuntu-based systems

## 🛡️ Security Notes

- Uses OpenSSL for module signing
- Implements Machine Owner Key (MOK) management
- Disables potential virtualization conflicts

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

## 👥 Author

0xb0rn3 - [GitHub Profile](https://github.com/0xb0rn3)

## 🐞 Issues

Report issues and bugs on the [GitHub Issues Page](https://github.com/0xb0rn3/vbxmodprobe/issues)

---

**Disclaimer**: Use this script responsibly and understand its actions before execution. Always have system backups.
