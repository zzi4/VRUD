# VRUD: A Drone Dataset for Complex Vehicle-VRU Interactions within Mixed Traffic

[![GitHub](https://img.shields.io/badge/Dataset-Open%20Source-blue)](https://github.com/zzi4/VRUD)

**Vehicle-Vulnerable Road User Interaction Dataset** — Collected from urban villages in Shenzhen, China.

## Overview

VRUD addresses the critical gap in open-source datasets for **chaotic, unstructured urban mixed-traffic** environments. Unlike datasets focused on highways or regulated intersections, VRUD captures the "long-tail" scenarios where VRUs constitute the majority of traffic participants and interactions are driven by negotiation rather than rigid rules.

| Metric | Value |
|--------|-------|
| **Recording** | 4 hours @ 4K/30Hz |
| **VRU Trajectories** | 11,479 |
| **Vehicle Trajectories** | 1,939 |
| **Interaction Scenarios** | 4,002 |
| **VRU Proportion** | ~87% |

## Key Features

- **Extreme VRU density** — Pedestrians, motorcycles, tricycles, bicycles
- **OpenDRIVE HD maps** — Standard format for map-based research
- **VTTC-based scenario extraction** — 4,002 multi-agent interaction samples
- **7 categories** — Cars, buses, trucks, bicycles, motorcycles, tricycles, pedestrians

## Data Access Application

To request access to VRUD, choose either of the following methods:

**Option 1 — GitHub Issue (recommended):** [Submit a Data Access Request](https://github.com/zzi4/VRUD/issues/new/choose) directly on GitHub. No email required.

**Option 2 — Email:** Download the form, fill it in, and send to [ziyu25@mails.jlu.edu.cn](mailto:ziyu25@mails.jlu.edu.cn).
[Download Application Form (Word)](./VRUD_Access_Application_Form.docx)

Both options require: **Full Name**, **Institution / Company**, **Detailed Description of Intended Use**, and **Acknowledgement**.

## Free Data Processing Service

If you have already collected, or are planning to collect, drone-view traffic flow videos in urban or mixed-traffic environments, we are happy to help with data processing.

**We offer free small-batch data processing**, including:
- Object detection and tracking
- Trajectory extraction and coordinate transformation
- HD map generation (OpenDRIVE format)
- VTTC-based interaction scenario extraction

Processed results will be delivered back to you by email. **Please note:** by using this service, the processed data will also be incorporated into our own research database, and we reserve the right to use it for both academic research and commercial applications.

For large-scale processing needs or commercial collaboration inquiries, please contact us directly:

- [ziyu25@mails.jlu.edu.cn](mailto:ziyu25@mails.jlu.edu.cn)

## Authors

Ziyu Wang, Hongrui Kou · Cheng Wang · Ruochen Li, Hubert P. H. Shum · **Yuxin Zhang*** (Corresponding)

*Jilin University · Heriot-Watt University · Durham University*

## Citation

If you use VRUD in your research, please cite our paper:

```bibtex
@misc{wang2026vruddronedatasetcomplex,
      title={VRUD: A Drone Dataset for Complex Vehicle-VRU Interactions within Mixed Traffic}, 
      author={Ziyu Wang and Hongrui Kou and Cheng Wang and Ruochen Li and Hubert P. H. Shum and Amir Atapour-Abarghouei and Yuxin Zhang},
      year={2026},
      eprint={2604.01134},
      archivePrefix={arXiv},
      primaryClass={cs.RO},
      url={https://arxiv.org/abs/2604.01134}, 
}
```

## License

For research use in autonomous driving and VRU interaction studies.
