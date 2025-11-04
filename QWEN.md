# Nature's Vigil - QWEN.md

## Project Overview

Nature's Vigil is a real-time AI-powered computer vision system designed to detect littering behavior in Bangladesh. The project is presented as a single-page HTML website that details the problem of waste management in Bangladesh and proposes an AI-powered solution using computer vision technologies.

### Purpose
- To address Bangladesh's waste management crisis through intelligent surveillance
- To support the National Action Plan targets of reducing plastic waste generation by 30% and virgin plastic use by 50% by 2030
- To create a system that detects, alerts, and prevents littering in real-time

### Core Technology Stack
- **Languages**: Python 3.9+
- **Deep Learning Framework**: PyTorch
- **Object Detection**: YOLO v8
- **Pose Estimation**: MediaPipe
- **Action Recognition**: Temporal CNN
- **Deployment**: NVIDIA Jetson Xavier NX for edge processing
- **Tools**: OpenCV, Label Studio/Roboflow for annotation

### System Architecture
The solution employs a two-stage approach:
1. **Object Detection**: YOLO v8 detects humans and waste objects with 30-60 FPS performance
2. **Action Recognition**: MediaPipe extracts 33 body landmarks per frame, analyzing arm trajectory and temporal patterns to classify sequences as littering vs. normal activity with 150ms latency

The system processes video streams from IP cameras in real-time and provides automated enforcement alerts including audio warnings, visual overlays, incident logging, and municipal notifications.

## Project Structure

```
natures-vigil.github.io/
├── index.html          # Main single-page application with embedded CSS
├── Logo.png            # Project logo
├── Team Member/        # Directory containing team member photos
│   ├── Fahmid Hasan (CTO).jpg
│   └── Swikrity Barman (CEO).jpg
└── QWEN.md             # This file
```

## Building and Running

This project is a static single-page website that can be run directly in any modern web browser by opening the `index.html` file.

To serve locally for development:
```bash
# Using Python 3
python -m http.server 8000

# Or using Node.js
npx http-server

# Then navigate to http://localhost:8000 in your browser
```

## Key Features

- Real-time littering behavior detection
- Automated alerts (audio, visual, notifications)
- 90%+ precision rate
- Edge processing on NVIDIA Jetson
- 24/7 monitoring and evidence logging
- Scalable deployment across multiple cities

## Business Model

The project includes plans for multiple revenue streams:
1. **System Licensing**: One-time fees for city-wide deployment (USD 15,000-50,000 per city)
2. **SaaS Monitoring**: Recurring monthly service (USD 500-2,000/month per camera)
3. **Data Analytics**: Behavioral analytics dashboards (USD 1,000-5,000/month per city)

## Market Opportunity

- Bangladesh's waste management market: USD 3.7 billion by 2026 (8.3% CAGR)
- Immediate addressable market: 50 cities × 5-10 cameras = USD 3.75-15 million (Year 1-2)
- Bangladesh generates 25,000-30,000 tonnes of waste daily
- Only 31% of plastic waste currently recycled
- Targets 50% plastic recycling by 2025

## Team

- **CEO**: Swikrity Barman
- **CTO**: Fahmid Hasan
- Team from Bangladesh Agricultural University, Mymensingh

## Development Conventions

The website implements:
- Modern, minimalistic design with a green/eco-friendly color scheme
- Responsive design supporting multiple screen sizes
- CSS variables for consistent styling
- Semantic HTML structure
- Accessibility considerations in navigation and content structure

## Target Deployment

The project is participating in the Cleantech Accelerator & Commercialization Program to solve plastic waste challenges in Bangladesh, with a focus on deployment across Bangladesh's urban centers.