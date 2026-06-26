# Deployment and Usage

This page contains short deployment examples for running FloodVoice in cloud or on edge hardware (Raspberry Pi).

Docker (recommended for quick testing)

1) Build the image (repository contains a Dockerfile)

```bash
# build the image
docker build -t floodvoice:latest .

# run with a mounted model directory and environment variables
docker run --rm -v $(pwd)/models:/app/models \
  -e MODEL_PATH=/app/models/floodvoice-lstm-v1.pt \
  -e TELEPHONY_API_KEY="your-telephony-api-key" \
  -e IVR_PROVIDER_URL="https://api.example-ivr.com" \
  -p 8080:8080 \
  floodvoice:latest
```

2) Example docker-compose.yml

```yaml
version: '3.8'
services:
  floodvoice:
    image: floodvoice:latest
    build: .
    ports:
      - "8080:8080"
    volumes:
      - ./models:/app/models
    environment:
      - MODEL_PATH=/app/models/floodvoice-lstm-v1.pt
      - TELEPHONY_API_KEY=${TELEPHONY_API_KEY}
      - IVR_PROVIDER_URL=${IVR_PROVIDER_URL}
```

Raspberry Pi / Edge notes

- Use multi-arch images or build for arm/v7 or arm64 using buildx:

```bash
docker buildx build --platform linux/arm/v7,linux/arm64,linux/amd64 -t floodvoice:latest --push .
```

- If your model is large, store it on an external USB drive and mount it into the container.
- Keep inference lightweight: use quantized weights or convert to TorchScript if using PyTorch.

Environment variables (used by the runtime)

- MODEL_PATH — path to the model file inside the container
- TELEPHONY_API_KEY — API key for IVR/telephony provider (e.g., Twilio, Plivo, local provider)
- IVR_PROVIDER_URL — URL endpoint for IVR API
- USSD_GATEWAY_CREDENTIALS — connection info for USSD/shortcodes

Logging & monitoring

- Route logs to stdout/stderr for container logging
- Expose a /health endpoint and monitor it with a simple readiness/readiness probe

