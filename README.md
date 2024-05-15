# GStreamerLearnings

#### Here are some important gstreamer pipelines

### Video playback pipeline:
```bash
gst-launch-1.0 filesrc location=<video_file> ! decodebin ! videoconvert ! autovideosink
```
This pipeline reads a video file at the location specified by <video_file> using the filesrc element. The video is then decoded using decodebin and converted to a format that can be displayed on the screen using videoconvert. Finally, the video is displayed automatically using autovideosink.

### Audio playback pipeline:
```bash
gst-launch-1.0 filesrc location=<audio_file> ! decodebin ! audioconvert ! autoaudiosink
```
This pipeline reads an audio file at the location specified by <audio_file> using the filesrc element. The audio is then decoded using decodebin and converted to a format that can be played through the speakers using audioconvert. Finally, the audio is played automatically using autoaudiosink.

### Video capture pipeline:
```bash
gst-launch-1.0 v4l2src device=/dev/video0 ! decodebin ! videoconvert ! autovideosink
```
This pipeline captures video from a camera or other input device specified by device=/dev/video0 using the v4l2src element. The video is then decoded using decodebin and converted to a format that can be displayed on the screen using videoconvert. Finally, the video is displayed automatically using autovideosink.

### Audio capture pipeline:
```bash
gst-launch-1.0 alsasrc device=default ! decodebin ! audioconvert ! autoaudiosink
```
This pipeline captures audio from a microphone or other input device specified by device=default using the alsasrc element. The audio is then decoded using decodebin and converted to a format that can be played through the speakers using audioconvert. Finally, the audio is played automatically using autoaudiosink.

### Video streaming pipeline:
```bash
gst-launch-1.0 v4l2src device=/dev/video0 ! videoconvert ! x264enc ! rtph264pay ! udpsink host=<destination_ip> port=<destination_port>
```
This pipeline captures video from a camera or other input device specified by device=/dev/video0 using the v4l2src element. The video is then converted to a format suitable for streaming using videoconvert. x264enc is used to encode the video using the H.264 codec, rtph264pay is used to packetize the encoded video data into RTP packets, and udpsink is used to send the packets over UDP to the destination IP address and port specified by <destination_ip> and <destination_port>, respectively. 

### Video recording pipeline:
```bash
gst-launch-1.0 v4l2src device=/dev/video0 ! videoconvert ! x264enc ! mp4mux ! filesink location=<output_file>
```
This pipeline captures video from a camera or other input device specified by device=/dev/video0 using the v4l2src element. The video is then converted to a format suitable for recording using videoconvert. x264enc is used to encode the video using the H.264 codec, mp4mux is used to multiplex the encoded video and audio data into a MP4 container format, and filesink is used to save the output file to the location specified by <output_file>.


