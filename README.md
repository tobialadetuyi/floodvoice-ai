FloodVoice
FloodVoice is an open-source early warning platform that combines satellite data and community observations with artificial intelligence to protect climate-vulnerable communities in Least Developed Countries and Small Island Developing States. Developed by Oluwatobi Jeremiah in Ogun State, Nigeria, FloodVoice uses an LSTM neural network to forecast ward-level flood risk from open NASA and Copernicus data, then generates automated voice alerts in local languages delivered through IVR calls and WhatsApp audio. Designed for offline operation, low power, and 2G networks, the system is published under Apache 2.0 to enable Red Cross chapters and civil protection agencies in The Gambia, Guinea-Bissau, and Cabo Verde to adapt and deploy it without proprietary barriers.

Problem
Increasing flash floods displace thousands yearly in low-lying LDCs and SIDS
National alerts arrive in English, need mobile data, and reach communities too late
2024 floods in Magboro-Akeran showed the gap for local-language, basic-phone warnings
Solution
AI forecast (6–12h): LSTM model fusing NASA GPM rainfall, Sentinel-1 flood extent, and community river gauges via USSD
Local voice alerts: auto-generated TTS in Wolof, Kriolu, Mandinka, and Yoruba
2G delivery: IVR calls and WhatsApp audio, works offline on Raspberry Pi
Open Source
License: Apache 2.0
Copyright 2026 Oluwatobi Jeremiah
Code, model weights, and Docker containers will be published here
Quickstart
bash
# coming soon
git clone https://github.com/YOUR-USERNAME/floodvoice-ai
cd floodvoice-ai
