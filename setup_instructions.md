# 1. Install required Termux package
pkg install termux-api

# 2. Enable access to the Downloads folder
termux-setup-storage

# 3. Copy the downloaded package into Termux
cp ~/storage/downloads/usbipdcpp-*-android-arm64.tar.gz ~/

# 4. Extract it into Termux private storage
tar xf usbipdcpp-*-android-arm64.tar.gz

# 5. Make the server executable
chmod +x usbipdcpp-termux/bin/termux_libusb_server

# 6. List connected USB devices
termux-usb -l

# 7. Use the listed device path to start the server

termux-usb -r -e ./usbipdcpp-*-android-arm64.tar.gz /dev/bus/usb/xxx/xxx

# 8. Approve the USB permission prompt. The command remains open with no output while the server runs. Use Ctrl+C to stop it.