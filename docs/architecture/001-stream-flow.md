# ARCH001: Stream Flow

대략적인 구성은 아래와 같다.

```text
OBS
 ↓
RTMP
 ↓
Ingest
 ↓
Transcode
 ↓
MinIO
 ↓
HLS
 ↓
Player
 ↓
Viewer
```