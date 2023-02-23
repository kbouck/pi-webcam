# pi-webcam
A Raspberry Pi Webcam using HDMI output with capture card

# Approach
The approach for this pi-webcam is to auto-login into pi OS desktop, to run camera preview at fullscreen, and to capture the HDMI output with a capture card. Other pi-webcam projects exist which configure the pi as a USB gadget and transfer the video over that USB connection. While this HDMI capture card approach simplifies the pi configuration, it does likely cost more than just buying a simple webcam with comparable capabilities, but we're just having fun here... 

# Install
- Install Raspberry Pi OS (with Desktop)
- Configure user auto-login
- Configure display preferences 
  - Navigate to Pi Menu -> Preferences -> Raspberry Pi Configuration -> Display
  - Disable screen blanking
  - Configure headless screen resolution
- Configure camera autostart 
  - create directory $HOME/.config/autostart if it doesn't already exist
  - create file $HOME/.config/autostart/pi-webcam.desktop with the following content:
    ```
    [Desktop Entry]
    Type=Application
    Name=Pi-Webcam
    Exec=/usr/bin/libcamera-vid -t 0 --fullscreen --awb indoor
    ```
- After next pi desktop startup, the camera will appear full screen over the HDMI connection

# Hardware
- Raspberry Pi 3 or 4
- Raspberry Pi Camera (v3 or HQ preferred)
- HDMI capture card (eg. Elgato Cam Link) 

# USB Gadget vs HDMI Capture
This is a placeholder for comparing the performance/bandwidth of the USB gadget approach versus the HDMI w/ capture card approach. 


# Other Pi-Webcam projects/resources
- https://github.com/geerlingguy/pi-webcam
