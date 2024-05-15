# GStreamerLearnings

### Video playback pipeline:
```bash
gst-launch-1.0 filesrc location=<video_file> ! decodebin ! videoconvert ! autovideosink
```
This pipeline reads a video file at the location specified by <video_file> using the filesrc element. The video is then decoded using decodebin and converted to a format that can be displayed on the screen using videoconvert. Finally, the video is displayed automatically using autovideosink.
