# Jetson: 
> Once powered ON, it should automatically start and run a script that essentially waits for GND station to connect and control.
1) Post power initialization script 
2) Vehicle Detection Algorithm 
- Starts automatically when powered ON 
- Runs start up script that initializes basic services
- Waits for commands from the remote computer
- Capture video from PTZ Optics 
- Process the video w/ Vehicle Tracking Algorithm 
- Control the camera based on Processing result 
- Sends the processed video to remote computer 
- Receieves commands from the remote computer 

# Ground Station (Remote Computer): 
- Connects to Jetson 
- Send initialization commands 
- Display video receieved from Jetson 
- Provides UI to send command
- Send commands to Jetson 