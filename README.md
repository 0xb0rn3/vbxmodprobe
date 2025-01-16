# VBXModProbe 🔐

[![GitHub](https://img.shields.io/badge/GitHub-0xb0rn3-blue?style=flat&logo=github)](https://github.com/0xb0rn3)

VBXModProbe is a powerful bash script designed to streamline the process of signing VirtualBox kernel modules on systems with Secure Boot enabled. By automating the complex steps of key generation, module signing, and secure boot management, this tool makes it easier for users to get VirtualBox running properly on their secure systems.

## 🌟 Features

When you run VBXModProbe, it takes care of the entire process automatically, including:

- Key generation and secure storage
- Module detection and signing
- Secure Boot environment management
- System verification and health checks
- Detailed logging with user-friendly color coding
- Comprehensive error handling and recovery

## 🚀 Prerequisites

Before using VBXModProbe, you'll need:

- A Linux system with Secure Boot enabled
- VirtualBox installed on your system
- Root/sudo privileges
- Essential system packages (automatically installed if missing):
  - openssl
  - mokutil
  - dkms
  - build-essential
  - linux-headers

## 💻 Installation

1. Clone the repository:
```bash
git clone https://github.com/0xb0rn3/vbxmodprobe.git
cd vbxmodprobe
```

2. Make the script executable:
```bash
chmod +x vbx
```

## 🔧 Usage

### Basic Usage
To run the full automation process:
```bash
sudo ./vbx
```

### Additional Options
VBXModProbe comes with several useful command-line options:

```bash
# Display help information
./vbx --help

# Show the complete manual command reference
./vbx --manual

# Perform a status check of your system
sudo ./vbx --check-only

# Rebuild modules without regenerating keys
sudo ./vbx --rebuild-only
```

## 🔄 Process Flow

When you run VBXModProbe, it follows these steps:

1. **System Preparation**
   - Validates root privileges
   - Checks for required dependencies
   - Installs any missing prerequisites
   - Verifies Secure Boot status

2. **Key Management**
   - Creates or reuses signing keys
   - Handles MOK (Machine Owner Key) enrollment
   - Sets up proper security permissions

3. **Module Processing**
   - Identifies installed VirtualBox modules
   - Applies digital signatures
   - Rebuilds modules when needed
   - Loads the signed modules into kernel

4. **System Verification**
   - Tests module loading status
   - Checks VirtualBox service health
   - Reviews kernel messages
   - Validates the complete setup

## 🚨 Important Notes

1. **First-Time Setup**
   After running VBXModProbe for the first time:
   - Your system will need to restart
   - You'll see the MOK management screen during boot
   - Follow the on-screen instructions to enroll your key
   - The system will restart one more time
   - VirtualBox should then work properly

2. **After Kernel Updates**
   When your system gets a kernel update:
   - Run VBXModProbe again
   - Your existing keys will be reused
   - Modules will be automatically re-signed

3. **Troubleshooting**
   If you encounter issues:
   - Look for color-coded messages in the output
   - Use the `--check-only` option to assess your system
   - Check kernel messages using `dmesg | grep -i vbox`

## 🛠️ Manual Commands

To understand the underlying process or perform manual steps:
```bash
./vbx --manual
```

This displays all commands that VBXModProbe uses internally.

## 🐛 Common Issues

1. **Module Not Found**
   This usually happens when:
   - VirtualBox installation is incomplete
   - Modules need rebuilding
   - System packages are outdated

2. **Signing Failures**
   Check these points:
   - Secure Boot status
   - Key generation success
   - Directory permissions

3. **Loading Problems**
   Verify:
   - Module signatures
   - Kernel version compatibility
   - Required dependencies

## 🤝 Contributing

We welcome contributions! Here's how you can help:

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙋‍♂️ Author

**0xb0rn3**
- GitHub: [@0xb0rn3](https://github.com/0xb0rn3)

## 🙏 Acknowledgments

Special thanks to:
- VirtualBox development team
- Linux kernel documentation
- UEFI Secure Boot documentation
- All contributors and testers

---

*VBXModProbe is maintained by 0xb0rn3. For issues, suggestions, or contributions, please visit the GitHub repository.*
