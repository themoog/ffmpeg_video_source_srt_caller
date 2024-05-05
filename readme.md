
# FFMPEG SRT Streaming Docker Setup

This Docker container is designed to facilitate SRT streaming using FFMPEG. It loops through one of three predefined videos (video1, video2, video3) for test purposes and includes configuration options through environment variables.

## Base Image

The Dockerfile uses `Ubuntu 22.04` as the base image.

## Environment Variables

Several environment variables are set to control the behavior of the streaming setup:

- `VIDEO_NAME`: Specifies the video file to be streamed. Default is `video1.mp4`.
- `SRT_IP`: The IP address where the SRT stream will be sent. Default is `0.0.0.0`.
- `SRT_PORT`: The port number for the SRT stream. Default is `4900`.
- `OVERLAY_TEXT`: Custom text overlay to be added to the video. Default is "Default Text".
- `LOGO_ENABLED`: Boolean flag to toggle logo overlay on the video. Default is `true`.


## Video and Audio Streaming

The container streams video using the H.264 video codec and AAC audio codec. The streaming happens over SRT (Secure Reliable Transport) protocol as a caller

## Usage

1. **Build the Docker Image:**
   ```bash
   docker build -t ffmpeg-srt-streamer .
   ```

2. **Run the Docker Container:**
   ```bash
   docker run -e VIDEO_NAME=video2.mp4 -e SRT_IP=192.168.1.100 -e SRT_PORT=4900 ffmpeg-srt-streamer
   ```

   Adjust the `VIDEO_NAME`, `SRT_IP`, and `SRT_PORT` environment variables as needed.
