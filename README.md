# AIDP Video Forge

**GPU-Accelerated Video Processing on Decentralized Compute Networks**

[![Research Paper](https://img.shields.io/badge/📄_Research_Paper-Hugging_Face-orange)](https://huggingface.co/purplesquirrelnetworks/aidp-video-forge-paper)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 🎯 Key Results

| Metric | AIDP Video Forge | AWS MediaConvert | Improvement |
|--------|------------------|------------------|-------------|
| **Speed (4K)** | 2.8 min | 3.2 min | ⚡ **16x faster than CPU** |
| **Cost/Hour** | $0.25 | $0.60 | 💰 **58% cheaper** |
| **Quality (VMAF)** | 95.8 | 96.0 | 📊 Near-identical |

## 📄 Research Paper

Read our full research paper: [AIDP Video Forge: GPU-Accelerated Video Processing](https://huggingface.co/purplesquirrelnetworks/aidp-video-forge-paper)

## 🚀 Quick Start

```bash
# Install
pip install aidp-video-forge

# Configure
export AIDP_API_KEY="your-api-key"
export AIDP_WALLET="your-solana-wallet"

# Process video
python -m aidp_video_forge process \
  --input video.mp4 \
  --preset cinematic \
  --output processed.mp4
```

## 📊 GPU Acceleration

### NVENC vs CPU Encoding

| Operation | CPU | GPU (NVENC) | Speedup |
|-----------|-----|-------------|---------|
| H.264 Encoding | libx264 | h264_nvenc | **15-20x** |
| HEVC Encoding | libx265 | hevc_nvenc | **20-30x** |
| Scaling | scale | scale_cuda | 5-8x |
| HDR Tone Map | zscale | tonemap_cuda | 15x |
| LUT Application | lut3d | CUDA texture | 10x |

### Processing Speed

| Method | Time (10-min 4K) | Real-time | Speedup |
|--------|------------------|-----------|---------|
| CPU (libx264) | 45 min | 0.22x | 1x |
| AWS MediaConvert | 3.2 min | 3.1x | 14x |
| **AIDP (RTX 3090)** | **2.8 min** | **3.6x** | **16x** |
| **Distributed (5 GPUs)** | **1.2 min** | **8.3x** | **37x** |

## 💰 Cost Savings

### Hourly Processing Costs

| Provider | GPU | Cost/Hour | Cost/Min |
|----------|-----|-----------|----------|
| AWS MediaConvert | T4 | $0.60 | $0.030 |
| GCP Transcoder | T4 | $0.55 | $0.031 |
| **AIDP Video Forge** | **RTX 3090** | **$0.25** | **$0.011** |

### Annual Savings

| Scenario | Volume | AIDP Cost | AWS Cost | Savings |
|----------|--------|-----------|----------|---------|
| YouTuber | 100 hrs/mo | $66 | $180 | **$1,368/yr** |
| Studio | 500 hrs/mo | $330 | $900 | **$6,840/yr** |
| Platform | 2000 hrs/mo | $1,320 | $3,600 | **$27,360/yr** |

## 🎨 Processing Presets

### 1. Cinematic
- Teal-orange LUT (CUDA)
- Film grain overlay
- Letterbox aspect
- **12-15x real-time (4K)**

### 2. Broadcast
- Rec709 compliance
- Loudness normalization
- H.264 Level 4.1
- **18-22x real-time (1080p)**

### 3. Social Media
- Vertical crop (9:16)
- AI-generated captions
- Auto thumbnail
- **25-30x real-time (1080p)**

### 4. HDR
- SDR → HDR10 conversion
- Rec.2020 color space
- PQ transfer function
- **8-12x real-time (4K HDR)**

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│  Client (Web UI / CLI)                                  │
│  └── Upload → Process → Download                       │
├─────────────────────────────────────────────────────────┤
│  Job Orchestrator                                       │
│  └── Queue → Assign → Aggregate                        │
├─────────────────────────────────────────────────────────┤
│  AIDP GPU Workers                                       │
│  └── FFmpeg + NVENC + CUDA filters                     │
└─────────────────────────────────────────────────────────┘
```

## 🌍 Supported Formats

**Input:** MP4, MOV, MKV, AVI, ProRes, DNxHD, up to 8K
**Output:** H.264, HEVC, ProRes, AAC/MP3/PCM audio

## 🔗 Links

- **Research Paper**: https://huggingface.co/purplesquirrelnetworks/aidp-video-forge-paper
- **Live Demo**: https://video-forge.aidp.store
- **AIDP Marketplace**: https://aidp.store/marketplace/video-forge

## 📚 Citation

```bibtex
@article{karsten2026videoforge,
  title={AIDP Video Forge: GPU-Accelerated Video Processing on Decentralized Compute Networks},
  author={Karsten, Matthew},
  journal={Purple Squirrel Networks Technical Report},
  year={2026},
  url={https://huggingface.co/purplesquirrelnetworks/aidp-video-forge-paper}
}
```

## 📄 License

MIT License

---

Built by [Purple Squirrel Networks](https://purplesquirrelnetworks.com)
