# Model weights

This repository does not include trained model weights in the v0.1.0 release. The core model is a short-range LSTM trained to fuse satellite and community observations. To run inference on real data you should attach model weight files to the v0.1.0 release (or a later release).

Suggested weight file conventions

- Filename: floodvoice-lstm-v1.pt (PyTorch) or floodvoice-lstm-v1.tar.gz
- Format: PyTorch state_dict (.pt / .pth) or a compressed tarball containing:
  - model/state_dict.pt
  - model/config.json (model hyperparameters)
  - tokenizer/ (if used)
- Provide a SHA256 checksum alongside the release asset:
  - sha256sum floodvoice-lstm-v1.pt > floodvoice-lstm-v1.pt.sha256

How to upload weights to release v0.1.0

1) Using the GitHub web UI
- Go to: https://github.com/tobialadetuyi/floodvoice-ai/releases/tag/v0.1.0
- Click "Edit" (or "Draft a new release" if creating a new one)
- Drag & drop the model file(s) into the "Attach binaries by dropping them here or selecting them" area
- Save / Publish the release

2) Using the GitHub CLI
- gh release upload v0.1.0 path/to/floodvoice-lstm-v1.pt
- Optional: gh release upload v0.1.0 path/to/floodvoice-lstm-v1.pt path/to/floodvoice-lstm-v1.pt.sha256

3) Using curl + API (automation)
- Create a personal access token with repo scope and set GITHUB_TOKEN
- Example:
  ```bash
  RELEASE_ID=$(gh release view v0.1.0 --json id -q .id)
  curl -XPOST -H "Authorization: token $GITHUB_TOKEN" -H "Content-Type: application/octet-stream" \
    --data-binary @floodvoice-lstm-v1.pt \
    "https://uploads.github.com/repos/tobialadetuyi/floodvoice-ai/releases/$RELEASE_ID/assets?name=floodvoice-lstm-v1.pt"
  ```

Recommend before uploading

- Include a small README or JSON manifest describing:
  - model framework and versions (PyTorch 2.0+ recommended)
  - input normalization and expected sensor cadence
  - expected performance metrics on validation set

If you want, I can:
- Prepare a sample (tiny) model file placeholder in the repo for testing, or
- Upload a provided model file to the release if you share it or give an upload URL/token.
