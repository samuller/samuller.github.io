---
layout: post
title:  "RTSP to WebRTC"
categories: video software webrtc
---

<!-- # Example of converting RTSP video stream to WebRTC -->

If you have some type of RTSP video source and you want to view the stream in a browser, then you can follow this example.

To do this we run a [MediaMTX](https://github.com/bluenviron/mediamtx) server by using their docker container as follows:
```bash
# Set your own source's URL.
RTSP_URL="rtsp://user:pass@127.0.0.1/your_stream_url"
# We specifically set each of the address ports so that they're easy to change
# in case your system currently has those ports in use.
docker run --rm -it --network=host \
    -e MTX_RTMPDISABLE="yes" \
    -e MTX_RTSPADDRESS=":8554" \
    -e MTX_RTPADDRESS=":8000" \
    -e MTX_RTCPADDRESS=":8001" \
    -e MTX_HLSADDRESS=":8899" \
    -e MTX_WEBRTCADDRESS=":8889" \
    -e MTX_PATHS_TESTRTSP_SOURCE="$RTSP_URL" \
    bluenviron/mediamtx:0.23.7
```
After running that command, and checking that the output is successfully pulling from the stream, you can then go to this URL in a browser to view the stream via WebRTC: <http://localhost:8889/testrtsp/>.

As you might've noticed from the above command options or its output logs, MediaMTX will by default already also create an [HLS](https://en.wikipedia.org/wiki/HTTP_Live_Streaming) stream which you can access in any browser with something like [HLS.js](https://github.com/video-dev/hls.js/).

## Further configurations

Config options for MediaMTX can either be:

* Put in a YAML config file that has to be mapped in: `-v $PWD/mediamtx.yml:/mediamtx.yml`,
* or they can be passed as environment variables starting with `MTX_` (with further underscores used for configs that are nested dictionary keys).

See the [full config file](https://github.com/bluenviron/mediamtx/blob/main/mediamtx.yml) for all the options and their default values.

<!-- It includes many extra features that can help to transform or record the video streams (mostly via using[ffmpeg](https://ffmpeg.org/)). -->