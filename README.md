# VRUD: A Drone Dataset for Complex Vehicle-VRU Interactions within Mixed Traffic

[![Access](https://img.shields.io/badge/Dataset-Access%20by%20application-blue)](https://zzi4.github.io/VRUD/)

**Vehicle–Vulnerable Road User Interaction Dataset** — Three urban mixed-traffic sites in Shenzhen, Guangdong, China (Sites A and B) and Changchun, Jilin, China (Site C).

## Research Inventory — 10 November 2026

The figures below describe the updated three-site manuscript inventory. Dataset access is by application; the supplied version and included resources are confirmed in the response. This repository does not host raw trajectories.

| Quantity | Value | Counting rule |
|---|---:|---|
| Recording exposure | 8.50 h / 151 recordings | Three sites; rounded hours |
| Retained trajectories | 30,554 | Recording-local tracks; rounded recorded travel distance ≥2.00 m |
| VRU trajectories | 22,733 (74.40%) | Pedestrians, bicycles, tricycles, motorcycles |
| Motor-vehicle trajectories | 7,821 | Cars, trucks, buses |
| Primary behavior/SSM intervals | 14,105 | Sustained-motion directed-pair–behavior intervals; types may overlap |
| Within-recording ego–VRU pairs | 10,264 | Distinct motor-vehicle ego and VRU counterpart identities |
| Selected-ego scenes | 5,513 | One selected ego and multiple successive or concurrent targets |
| Scenes with simultaneous targets | 3,032 | At least two distinct targets interacting concurrently |

All three sites use **4K resolution, an 80 m flight altitude, and a nominal frame rate of 30 fps**.

| Site | Setting | Location | Recordings | Exposure |
|---|---|---|---:|---:|
| A | Residential intersection | Shenzhen, Guangdong, China | 41 | 2.41 h |
| B | Residential street | Shenzhen, Guangdong, China | 23 | 1.30 h |
| C | Mixed-use junction and adjoining streets | Changchun, Jilin, China | 87 | 4.78 h |

Site C contains all 87 available recordings from October 13, 14, 16, and 17, 2026. Registered OpenDRIVE maps cover all three sites. See [the machine-readable inventory](dataset_inventory_20261110.json?v=83a09e44da50) and [the combined category inventory and composition figure](img/manuscript_20261110/dataset_profile.png).

## Manuscript Overview

Automated driving in dense mixed traffic requires anticipating interactions between motor vehicles and heterogeneous vulnerable road users (VRUs) sharing limited road space. Uneven trajectory-data coverage of narrow streets and roadside activity restricts the development and evaluation of models for these environments. We present VRUD, a drone-based dataset collected at three urban mixed-traffic sites, comprising 8.50 hours, 30,554 retained trajectories, and seven road-user categories. VRUs constitute 74.40% of its retained trajectory inventory. Encounters are organized around a selected motor vehicle, preserving surrounding participants and their successive or concurrent behavior relations. Complementary spatial and temporal safety-surrogate measures characterize behavior- and participant-dependent interaction conditions. Forecasting experiments highlight the value of representative mixed-traffic training data and surrounding trajectories, while behavior-conditioned evaluation exposes differences hidden by aggregate errors. Together, the trajectory resource, interaction profiles, and forecasting benchmark support the study of heterogeneous mixed traffic and the selection of test conditions through behavioral coverage and safety criticality. VRUD can support research on interaction-aware prediction, cross-domain generalization, and scenario mining and generation for automated-driving evaluation. Dataset access requests: https://zzi4.github.io/VRUD/.

## Research Components

- **Seven-category trajectories:** observed frames, local metric positions, heading, oriented-box dimensions, native motion attributes, and recording-local identities.
- **Multi-participant scene organization:** relative motion, oriented-box spatial relations, and registered map semantics define successive or concurrent behaviors around a selected car/truck/bus ego. Multiple VRUs and other motor vehicles can participate in one scene.
- **Shared behavior vocabulary:** 13 behavior types separate the motion relation from road-user category. Crossing uses one definition across pedestrians, bicycles, tricycles, and motorcycles.
- **Conditional interaction profiles:** clearance, body-contact TTC, exposure, conflict-region PET, braking, and applicable longitudinal measures. [Seven supported behavior types](img/manuscript_20261110/interaction_profiles.png) cover 97.25% of primary intervals; distributions require ≥30 valid observations from ≥5 recordings in each behavior–VRU–metric cell.
- **Crossing evidence:** 3,090 intervals include 2,801 occupancy-supported and 289 path-only crossings. PET is evaluated for occupancy-supported crossings.
- **Prediction evaluation:** map-free Trajectron++ comparisons use VRUD, SinD, and INTERACTION, with seven training conditions and three seeds (21 fitted models; 45 main cross-dataset evaluations). Conditions examine source transfer, neighboring trajectories, and held-out-location generalization. Updated plots are [cross-dataset prediction](img/manuscript_20261110/prediction_overview.png), [context and generalization evidence](img/manuscript_20261110/prediction_evidence.png), and [behavior-stratified prediction](img/manuscript_20261110/prediction_strata.png?v=f45e21eed6f3).

A common map-free Trajectron++ protocol assigns 13,312 class-balanced training targets per condition and predicts 3 s from 1 s of observations. On the held-out Site C date, VRUD training achieves class-macro minADE@6 of 0.367 ± 0.011 m, compared with 0.486 ± 0.002 m for SinD training and 0.721 ± 0.012 m for INTERACTION training. CAR and pooled pedestrian/bicycle targets receive equal macro weight. Sites A+B-only training gives 0.463 ± 0.008 m on the same test windows. Full context reduces CAR minADE@6 from 0.566 to 0.525 m. Linking the complete behavior library identifies 2,023 CAR windows; 1,940 have at least one quality-eligible detailed relation, and 1,862 satisfy the stricter pooled safety-surrogate checks. Pedestrian crossing contributes 679 clean windows across 25 recordings; side-neighbor and completed opposing-passage relations contribute 318/24 and 68/19 windows/recordings. These relation groups may overlap. Results describe one predictor and one held-out VRUD date. All ± values denote sample standard deviation across three training seeds.

The inventory, behavior intervals, selected-ego scenes, and forecast windows have different eligibility rules and counting units. A behavior interval requires each actor to have at least one continuous second at native speed ≥0.5 m/s somewhere in its track; temporary stops are retained. One scenario can contain multiple directed-pair behavior intervals. Specify the inventory date and requested trajectory, map, behavior/SSM, or evaluation components in an access request.

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
