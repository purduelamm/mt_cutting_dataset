# CNC Machine Tool Cutting Sound Dataset

## Introduction
Welcome to the CNC milling cutting sound dataset repository. This dataset has been collected as part of the research conducted for the papers[^1], [^2] . The dataset encompasses cutting sound in CNC milling process in both lab and industry settings, which have been meticulously collected and processed to facilitate reproducibility and further research.

There are two datasets, `IMI` and `KRPM`. 

**IMI** refers to the CNC milling sound dataset collected in a laboratory setting within the Intelligent Manufacturing Testbed (IMT) of the Indiana Next Generation Manufacturing Competitiveness Center (IN-MaC)[^3], located in the Indiana Manufacturing Institute at Purdue University, West Lafayette, Indiana, USA. The target machine is a 3-axis vertical CNC mill (VM20i, Hurco). The **IMI** data was originally collected for chatter sound detection during the end-milling process, featuring a wide range of cutting parameters and conditions, such as workpiece materials, tools, wear conditions, and so on, but is limited to end-milling. For more details about the experimental setup and related research, please refer to [^2].

**KRPM** refers to the CNC milling sound dataset collected in an industry setting at Kirby Risk Precision Machining (KRPM)[^4], Lafayette, Indiana, USA. **KRPM** is a Global Tier 1 supplier to Original Equipment Manufacturers (OEMs). The target machine is a 4-axis horizontal CNC mill (HCN-6000, Mazak) used for manufacturing machinery parts for the heavy-duty industry. Due to the high cost and time-consuming nature of data collection and labeling in an industry setting, the **KRPM** data was utilized to leverage abundant lab data for scarce industry data in domain adaptation (DA) research as described in [^2].

### Purpose
The primary aim of sharing this dataset is to promote transparency and repdoducibility in research. By making this dataset publicly available, we hope to:

* Enable other researchers to validate and build upon our findings.
* Foster collaboration and data sharing within the research community.
* Contribute to the body of knowledge in the field of machine sound recognition of metal cutting industry.

### Dataset Description

The tree of the datasets for the datasets is shown below.

<pre>
project
│   README.md
├───IMI
│   ├───Exp*
│   │   ├───*_sensor0.wav
│   │   ├───*_sensor1.wav
│   │   ├───*_sensor2.wav
│   │   ├───cutting.csv
│   │   └───*_video.mp4
│   ├───Exp*
│   │   ├───...
│   │   ...
│   └───labeling_all_details.xlsx
└───KRPM
    ├───*_sensor0.wav
    ├───*_sensor1.wav
    ├───*_sensor2.wav
    ├───cutting.csv
    └───Video1.mp4
</pre>

In the `IMI` dataset, there are 18 subdirectories. Each subdirectory contains three sound files in WAV format, one cutting label file in CSV format, and one video footage file (if available) in MP4 format. The `KRPM` dataset consists of one directory with the same data formats and notations as `IMI`.

All sound files in each subdirectory are synchronized and have the same length. The integer number between `*_sensor` and `.wav` indicates the sensor number.

The CSV file corresponds to the WAV files in each subdirectory. The CSV file is structured as follows: the first column (`start`) indicates the start time of the cutting path in seconds, and the second column (`end`) indicates the end time of the cutting path in seconds. For example, in the CSV file, the first cutting path starts at 10.816 seconds and ends at 12.864 seconds. The second cutting path starts at 13.42 seconds and ends at 15.38 seconds, and so on. This format allows easy loading of sound data with corresponding labels.

|  start |   end  |
|:------:|:------:|
| 10.816 | 12.864 |
|  13.42 |  15.38 |
|   ...  |   ...  |

If available, the video footage for the corresponding milling operation is included in the (sub)directory, providing a visual understanding of the dataset.

In the `IMI` dataset, `labeling_all_details.xlsx` includes details of cutting conditions, parameters, setups, and chatter labeling[^1].

### Data Collection






[^1]: E. Kim, T. Bui, J. Yuan, S. C. Mouli, B. Ribeiro, R. A. Yeh, M. P. Fassnacht, and M. B. Jun, “Online real-time machining chatter sound detection using convolutional neural network by adopting expert knowl- edge,” Manufacturing Letters, 2024, (forthcoming).
[^2]: M. Mostafiz, E. Kim, A. Li, E. Bertino, M. B. Jun, and A. Shakouri, "Adversarial Domain Adaptation for Metal Cutting Sound Detection: Leveraging Abundant Lab Data for Scarce Industry Data," 2024 IEEE 22nd International Conference on Industrial Informatics (INDIN), (submitted).
[^3]: https://www.purdue.edu/in-mac/ (accessible on May 30, 2024).
[^4]: https://www.kirbyrisk.com/precision-machining (accessible on May 30, 2024).