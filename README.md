# CCminer Installer for Verus Mining on Android

Automated mining setup for Verus coin on Android using Termux. This script will configure and run CCminer automatically when you open Termux.

## How to Install
1. Update the system:
   ```
   pkg update && pkg upgrade -y
   ```
2. Install wget:
   ```
   pkg install wget -y
   ```
3. Download the installer and uninstaller scripts:
   ```
   wget https://raw.githubusercontent.com/DWBVUNH/cc/master/installer.sh
   wget https://raw.githubusercontent.com/DWBVUNH/cc/master/uninstaller.sh
   ```
4. Grant execute permission:
   ```
   chmod +x installer.sh
   chmod +x uninstaller.sh
   ```
5. Run the installer:
   ```
   ./installer.sh
   ```

## Uninstalling CCminer
To remove CCminer and its configuration:
```
./uninstaller.sh
```

## Configuration
During installation, you will be prompted to enter the following details:
- Wallet Address: Your Verus wallet address (default: `RULZ69W1YmQzCcxFW1miCxUrkkkgYeA3aK`)
- Worker Name: Custom name for your mining device (default: `worker`)
- Threads: Number of CPU threads to use (default: `8`)
- Pool URL: URL of the mining pool (default: `stratum+tcp://sg.vipor.net:5040`)
- Pool Name: Name of the mining pool (default: `SG-VIPOR`)

If you leave any field blank, the default value will be used.

## How to Start Mining
After successful installation, mining will start automatically. If Termux is restarted, mining will resume automatically as well.

To start mining manually:
```
$HOME/ccminer/ccminer -c $HOME/ccminer/config.json
```
To stop mining, close the Termux application or terminate the process.

## Log and Configuration
The mining configuration is saved in:
```
$HOME/ccminer/config.json
```
To modify the configuration, use:
```
nano $HOME/ccminer/config.json
```
After editing, restart Termux to apply changes.

## Troubleshooting
1. Miner does not start automatically:
   - Check the auto-run command in `.bashrc`:
     ```
     grep "ccminer" ~/.bashrc
     ```
   - If not found, manually add it:
     ```
     echo "$HOME/ccminer/ccminer -c $HOME/ccminer/config.json" >> ~/.bashrc
     ```

2. Mining stops unexpectedly:
   - Check for errors in the output or configuration file.
   - Ensure your device has enough resources (CPU/RAM).

3. Update CCminer:
   - To update CCminer, delete the existing folder:
     ```
     ./uninstaller.sh
     ```
   - And Reinstall:
     ```
     ./installer.sh
     ```

## Contact
For more information or support, Takumi Tesla's Email : [takumitesla@gmail.com](mailto:takumitesla@gmail.com).
