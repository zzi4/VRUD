# VRUD: A Drone Dataset for Complex Vehicle-VRU Interactions within Mixed Traffic

[![Access](https://img.shields.io/badge/Dataset-Access%20by%20application-blue)](https://zzi4.github.io/VRUD/)

**Vehicle–Vulnerable Road User Interaction Dataset** — Three urban mixed-traffic sites, including residential settings in Shenzhen and a mixed-use street.

## Research Inventory — 29 October 2026

The following figures describe the three-site manuscript analysis. The version and included resources supplied for an access request are confirmed separately; this repository does not distribute raw trajectories.

| Quantity | Value | Counting rule |
|---|---:|---|
| Recording exposure | 8.11 h / 135 recordings | Three sites; rounded hours |
| Retained trajectories | 18,491 | Recording-local instances; rounded recorded distance ≥2.00 m |
| VRU trajectories | 14,308 (77.38%) | Pedestrians, bicycles, tricycles, motorcycles |
| Motor-vehicle trajectories | 4,183 | Cars, trucks, buses |
| Primary behavior/SSM intervals | 16,944 | Separate sustained-motion cohort; intervals may overlap |
| Within-recording pairs | 9,662 | Motor-vehicle ego and VRU counterpart |

Site A (residential intersection): 41 recordings / 2.41 h. Site B (residential street): 23 / 1.30 h. Site C (mixed-use street): 71 / 4.40 h. Registered OpenDRIVE maps cover all three sites. See [the inventory description](dataset_inventory_20261029.json) for machine-readable scope and counting rules.

## Research Components

- **Seven-category trajectories:** observed frames, local metric positions, heading, oriented-box dimensions and recorded motion; missing observations remain explicit.
- **Behavior organization:** scenario.center/CRUISE-based adaptation with one fixed car/truck/bus ego, multiple associated participants and concurrent relations. Detector and map support are stated explicitly.
- **Conditional SSM profiles:** clearance, body-contact TTC, exposure, conflict-area timing and applicable longitudinal measures. Reference cutoffs are not calibrated accident-risk boundaries.
- **Prediction evaluation:** map-free Trajectron++ comparisons with SinD and INTERACTION; an additional 3,214-window car evaluation associates motorcycle/tricycle counterparts within one held-out acquisition.

The inventory, behavior/SSM cohort and prediction windows have distinct eligibility rules and counting units. A raw count of overlapping behavior intervals is not a count of independent physical encounters. Public access uses the existing application process below. Specify the three-site inventory date and the requested trajectory, map, behavior/SSM or evaluation components; package availability is confirmed in the response.

## Data Access Application

**Application form: <https://lab.autozyx.com/vrud.zh.html>**

> ⚠️ **Please apply through the form above. Do not open a GitHub issue.**
> GitHub issues are no longer used as a data-request channel — applications opened
> there may not be processed. After your application is reviewed, we will email you
> the download link, extraction code, and a pointer to the
> [vrud-viewer](https://github.com/zzi4/vrud-viewer) toolkit for inspecting and
> validating the data.


The application page describes the distributed release. For the three-site manuscript analysis, specify the research inventory date and requested components; the response confirms the corresponding version and availability.

## Free Data Processing Service

If you have already collected, or are planning to collect, drone-view traffic flow videos in urban or mixed-traffic environments, we are happy to help with data processing.

**We offer free small-batch data processing**, including:
- Object detection and tracking
- Trajectory extraction and coordinate transformation
- HD map generation (OpenDRIVE format)
- Behavior-based scenario organization and safety-surrogate analysis

Processed results will be delivered back to you by email. **Please note:** by using this service, the processed data will also be incorporated into our own research database, and we reserve the right to use it for both academic research and commercial applications.

For large-scale processing needs or commercial collaboration inquiries, please contact us directly:

- [ziyu25@mails.jlu.edu.cn](mailto:ziyu25@mails.jlu.edu.cn)

## Authors

Ziyu Wang, Hongrui Kou · Cheng Wang · Ruochen Li, Hubert P. H. Shum, Amir Atapour-Abarghouei · **Yuxin Zhang*** (Corresponding)

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
