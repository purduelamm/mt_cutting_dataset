# CNC Machine Tool Cutting Sound Dataset

## Introduction
Welcome to the CNC milling cutting sound dataset repository. This dataset has been collected as part of the research conducted for the papers[^1], [^2] . The dataset encompasses cutting sound in CNC milling process in both lab and industry settings, which have been meticulously collected and processed to facilitate reproducibility and further research.

[^1]: E. Kim, T. Bui, J. Yuan, S. C. Mouli, B. Ribeiro, R. A. Yeh, M. P. Fassnacht, and M. B. Jun, “Online real-time machining chatter sound detection using convolutional neural network by adopting expert knowl- edge,” Manufacturing Letters, 2024, (forthcoming).
[^2]: M. Mostafiz, E. Kim, A. Li, E. Bertino, M. B. Jun, and A. Shakouri, "Adversarial Domain Adaptation for Metal Cutting Sound Detection: Leveraging Abundant Lab Data for Scarce Industry Data," 2024 IEEE 22nd International Conference on Industrial Informatics (INDIN), (submitted).

There are two datasets, `IMI` and `KRPM`. 

**IMI** refers to the CNC milling sound dataset collected in a laboratory setting within the Intelligent Manufacturing Testbed (IMT) of the Indiana Next Generation Manufacturing Competitiveness Center (IN-MaC)[^3], located in the Indiana Manufacturing Institute at Purdue University, West Lafayette, Indiana, USA. The target machine is a 3-axis vertical CNC mill (VM20i, Hurco). The **IMI** data was originally collected for chatter sound detection during the end-milling process, featuring a wide range of cutting parameters and conditions, such as workpiece materials, tools, wear conditions, and so on, but is limited to end-milling. For more details about the experimental setup and related research, please refer to [^2].

**KRPM** refers to the CNC milling sound dataset collected in an industry setting at Kirby Risk Precision Machining (KRPM)[^4], Lafayette, Indiana, USA. **KRPM** is a Global Tier 1 supplier to Original Equipment Manufacturers (OEMs). The target machine is a 4-axis horizontal CNC mill (HCN-6000, Mazak) used for manufacturing machinery parts for the heavy-duty industry. Due to the high cost and time-consuming nature of data collection and labeling in an industry setting, the **KRPM** data was utilized to leverage abundant lab data for scarce industry data in domain adaptation (DA) research as described in [^2].

[^3]: https://www.purdue.edu/in-mac/
[^4]: https://www.kirbyrisk.com/precision-machining


### Purpose
The primary aim of sharing this dataset is to promote transparency and repdoducibility in research. By making this dataset publicly available, we hope to:

* Enable other researchers to validate and build upon our findings.
* Foster collaboration and data sharing within the research community.
* Contribute to the body of knowledge in the field of machine sound recognition of metal cutting industry.

### Description

This repository tree for the datasets is shown below.

project
|   README.md
├───IMI
|   ├───Exp*
|   |   ├───*_sensor0.wav
|   |   ├───*_sensor1.wav
|   |   ├───*_sensor2.wav
|   |   ├───cutting.csv
|   |   └───*_video.mp4
|   ├───Exp*
|   |   ├───...
|   ├───labeling_all_details.xlsx
├───KRPM
    ├───*_sensor0.wav
    ├───*_sensor0.wav
    ├───*_sensor0.wav
    ├───cutting.csv
    ├───Video1.mp4




