# Prerequisite 

- Docker
- Docker-compose

# How to convert mp3 to hls

```bash
ffmpeg -y -i "genda-phool.mp3" -c:a aac -b:a 128k -muxdelay 0 -f segment -sc_threshold 0 -segment_time 7 -segment_list "playlist-2.m3u8" -segment_format mpegts "filemp4%d.m4a"
```

# How to convert mp4 to hls

```bash
ffmpeg -i dildiya.mp4 -codec: copy -start_number 0 -hls_time 10 -hls_list_size 0 -f hls playlist-1.m3u8
```

# Build image and start container.

```bash
docker compose up -d --build
docker compose logs -f
```
