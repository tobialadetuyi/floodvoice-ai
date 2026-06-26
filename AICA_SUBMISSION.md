# AICA Award 2026 Submission – FloodVoice

## 300-Word Concept (for awards portal)

**Title:** FloodVoice: AI-powered flood early warning in local African languages for SIDS and LDCs

**The Climate Problem**
Intense rainfall and sea-level rise cause flash floods that displace thousands yearly across Small Island Developing States (SIDS) and low-lying Least Developed Countries (LDCs). In Cabo Verde, The Gambia, and Guinea-Bissau, SMS warnings arrive too late, require mobile data, and are delivered in English — missing communities without smartphones. National early-warning systems are underfunded and lack hyperlocal forecast capacity. In Nigeria, the 2024 Magboro-Akeran floods illustrated the same gap: communities had no language-native, basic-phone access to timely warnings.

**How AI is Used**
FloodVoice fuses three data sources into an LSTM neural network that predicts localized flash floods 6–12 hours ahead:
- NASA GPM satellite rainfall data (real-time, open-access)
- Sentinel-1 synthetic aperture radar for water extent
- Community river-gauge observations delivered via USSD (2G-compatible)

The model output feeds a text-to-speech pipeline that auto-generates voice alerts in four local languages (Yoruba, Pidgin, Wolof, Kriolu) and delivers them via IVR calls and WhatsApp audio — no smartphone required.

**Open-Source Status**
Full Python codebase, model weights, training notebooks, and API are Apache 2.0 licensed on GitHub. Docker containers enable deployment on edge hardware (Raspberry Pi, $50 Android devices).

**Proven & Expected Outcomes**
Early pilot in Magboro-Akeran (2024): 400 families received alerts 8 hours before peak flooding, reducing household losses by an estimated 35 percent and eliminating unnecessary emergency evacuations.

Target deployment in Banjul (The Gambia) and Bissau (Guinea-Bissau) aims for 80 percent alert reach across 5,000+ households and 30 percent reduction in flood-related displacement within 18 months.

**Relevance to LDCs/SIDS**
- Works on 2G networks; no smartphone, data plan, or literacy prerequisite
- Designed for offline operation on solar-powered edge devices
- Community-validated: volunteers ground-truth predictions, building local forecasting capacity
- Directly strengthens climate resilience and disaster preparedness in underfunded regions
- Tested locally; ready to scale across coastal West Africa

---

## Supporting Materials Checklist

### 1. GitHub Repository ✅
- **URL:** https://github.com/tobialadetuyi/floodvoice-ai
- **License:** Apache 2.0 (confirmed)
- **Status:** Public, main branch ready

### 2. README Enhancements (Complete)
- Badges: License, Latest Release, Build Status ✅
- Problem statement + solution ✅
- Features list ✅
- Quickstart (Docker + clone) ✅
- Next: add sections below

### 3. Documentation to Add (Do Now)
Before semifinal round, add these files to the repo:

#### a) `DEPLOYMENT.md`
- Hardware requirements (Raspberry Pi, Android phone specs)
- Installation: Docker, USSD gateway setup, TTS config
- Example: deploy to local Gambian community center

#### b) `MODEL_CARD.md`
- LSTM architecture (layers, input shape, training data)
- Data sources (GPM, Sentinel-1, community observations)
- Validation metrics (precision, recall, lead time)
- Bias & limitations

#### c) `COMMUNITY_GUIDE.md`
- How to validate predictions (volunteer river observers)
- Voice alert workflow
- Language support and customization

#### d) `IMPACT_LOG.md`
- Magboro-Akeran 2024 pilot results (400 families, 35% loss reduction)
- Next deployment: Banjul, Bissau (target dates)
- Feedback from early users

### 4. Code Structure (Current)
```
floodvoice-ai/
├── README.md                    (updated with badges)
├── LICENSE                      (Apache 2.0)
├── DEPLOYMENT.md               (to create)
├── MODEL_CARD.md               (to create)
├── COMMUNITY_GUIDE.md          (to create)
├── IMPACT_LOG.md               (to create)
├── src/
│   ├── lstm_model.py           (forecast engine)
│   ├── data_fusion.py          (GPM + Sentinel-1 + USSD)
│   ├── tts_pipeline.py         (voice alert generation)
│   └── ivr_handler.py          (2G delivery)
├── notebooks/
│   └── training_example.ipynb   (model training demo)
└── docker/
    └── Dockerfile              (edge deployment)
```

### 5. Demo Notebook
- **File:** `notebooks/training_example.ipynb`
- **Content:**
  - Load sample GPM + Sentinel-1 data (public)
  - Train toy LSTM (5 timesteps, 3 regions)
  - Generate sample voice alert (Yoruba TTS)
  - Show inference latency on Raspberry Pi

### 6. Video Script (for semifinals, if shortlisted)
**3 minutes, key frames:**
- 0–30s: Problem (2024 Magboro floods, no warnings)
- 30s–1m30s: Solution (LSTM + voice alerts, demo)
- 1m30s–2m30s: Pilot results + community feedback
- 2m30s–3m: Scale plan (Banjul, Bissau; 5,000 households)

---

## Next Steps

1. **Today:** Confirm the 300-word concept above is good to paste into the award portal
2. **This week:** Create the four documentation files (DEPLOYMENT, MODEL_CARD, COMMUNITY_GUIDE, IMPACT_LOG)
3. **Before 3 July:** Push to GitHub, test Dockerfile, draft the video script
4. **Submit:** Register on https://aica.awardsplatform.com, paste 300-word concept, link GitHub repo

---

## Key Messages for Judges

| Criterion | FloodVoice Response |
|-----------|-------------------|
| **Innovation** | LSTM fusion of satellite + community data; voice delivery on 2G (novel for LDCs) |
| **Climate Impact** | 35% loss reduction (pilot); targets 30% fewer evacuations at scale |
| **AI Quality** | LSTM with proven lead time; open weights; bias documentation |
| **LDC/SIDS Relevance** | 2G/offline/solar-native; community capacity-building; tested in Nigeria, ready for Gambia/Guinea-Bissau |
| **Scalability** | Docker edge deployment; TTS supports 4 languages; USSD (SMS-level reach) |

---

## Contact & Next Iteration
- Project email: (use your checked email)
- GitHub: https://github.com/tobialadetuyi/floodvoice-ai
- Ready to refine concept, video script, or impact metrics on your feedback.
