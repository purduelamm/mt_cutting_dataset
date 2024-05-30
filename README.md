# CNC Machine Tool Cutting Sound Dataset

## Introduction
Welcome to the CNC milling cutting sound dataset repository. This dataset has been collected as part of the research conducted for the papers[^1], [^2] . The dataset encompasses cutting sound in CNC milling process in both lab and industry settings, which have been meticulously collected and processed to facilitate reproducibility and further research.

There are two datasets, `IMI` and `KRPM`.

**IMI** refers to the CNC milling sound dataset collected in a laboratory setting within the Intelligent Manufacturing Testbed (IMT) of the Indiana Next Generation Manufacturing Competitiveness Center (IN-MaC)[^3], located in the Indiana Manufacturing Institute at Purdue University, West Lafayette, Indiana, USA. The machine is a 3-axis vertical CNC mill (VM20i, Hurco). The **IMI** data was originally collected for chatter sound detection during the end-milling process, featuring a wide range of cutting parameters and conditions, such as workpiece materials, tools, wear conditions, and so on, but is limited to end-milling. For more details about the experimental setup and related research, please refer to [^2].

**KRPM** refers to the CNC milling sound dataset collected in an industry setting at Kirby Risk Precision Machining (KRPM)[^4], Lafayette, Indiana, USA. **KRPM** is a Global Tier 1 supplier to Original Equipment Manufacturers (OEMs). The machine is a 4-axis horizontal CNC mill (HCN-6000, Mazak) used for manufacturing machinery parts for the heavy-duty industry. Due to the high cost and time-consuming nature of data collection and labeling in an industry setting, the **KRPM** data was utilized to leverage abundant lab data for scarce industry data in domain adaptation (DA) research as described in [^2].

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

All sound files in each subdirectory are synchronized and have the same length. The sampling rate is 48 kHz and in-depth resolution is 16-bit. The integer number between `*_sensor` and `.wav` indicates the sensor number. Regarding the sensor numbers and data collection details, please see [Data Collection](#data-collection).

The CSV file corresponds to the WAV files in each subdirectory. The CSV file is structured as follows: the first column (`start`) indicates the start time of the cutting path in seconds, and the second column (`end`) indicates the end time of the cutting path in seconds. For example, in the CSV file, the first cutting path starts at 10.816 seconds and ends at 12.864 seconds. The second cutting path starts at 13.42 seconds and ends at 15.38 seconds, and so on. This format allows easy loading of sound data with corresponding labels.

|  start |   end  |
|:------:|:------:|
| 10.816 | 12.864 |
|  13.42 |  15.38 |
|   ...  |   ...  |

If available, the video footage for the corresponding milling operation is included in the (sub)directory, providing a visual understanding of the dataset.

In the `IMI` dataset, `labeling_all_details.xlsx` includes details of cutting conditions, parameters, setups, and chatter labeling[^1].

### Data Collection

[Table 1](#table1) summarizes a comparison of the datasets. At **IMI**, the cutting process involved end-milling with simple zig-zag tool paths, encompassing a variety of cutting conditions, such as different end mills, materials, tool wear conditions, and tool setups. In contrast, the **KRPM** dataset includes additional cutting processes like facing and drilling. To accurately label the cutting sounds, an expert meticulously reviewed the recorded video footage while simultaneously listening to the audio from each sensor. Given that the workpiece was made of cast iron, which resulted in irregular shapes, determining the exact start and end times of the cutting process was challenging.

<table id="table1" class="tg"><thead>
  <caption>Table 1: Comparisons of datasets</caption>
  <tr>
    <th class="tg-c3ow" colspan="2">Category</th>
    <th class="tg-c3ow">Lab (<b>IMI</b>)</th>
    <th class="tg-c3ow">Industry (<b>KRPM</b>)</th>
  </tr></thead>
<tbody>
  <tr>
    <td class="tg-c3ow" colspan="2"><br>Machine (Model, Manufacturer)</td>
    <td class="tg-c3ow">3-axis Vertical Mill<br>(VM20i, Hurco)</td>
    <td class="tg-c3ow">4-axis Horizontal Mill<br>(HCN-6000, Mazak)</td>
  </tr>
  <tr>
    <td class="tg-c3ow" colspan="2">Working travel in x&times;y&times;z in inches</td>
    <td class="tg-c3ow">40&times;20&times;20</td>
    <td class="tg-c3ow">31.5&times;31.5&times;31.5</td>
  </tr>
  <tr>
    <td class="tg-c3ow" rowspan="2"><br>Maximum spindle specification</td>
    <td class="tg-c3ow">Torque</td>
    <td class="tg-c3ow">82.3 ft-lbs</td>
    <td class="tg-c3ow">442 ft-lbs</td>
  </tr>
  <tr>
    <td class="tg-c3ow">Speed</td>
    <td class="tg-c3ow">12,000 rpm</td>
    <td class="tg-c3ow">10,000 rpm</td>
  </tr>
  <tr>
    <td class="tg-c3ow" rowspan="3"><br><br>Sensor (Location)</td>
    <td class="tg-c3ow">0</td>
    <td class="tg-c3ow">Microphone (Working area)</td>
    <td class="tg-c3ow">Microphone (Working area)</td>
  </tr>
  <tr>
    <td class="tg-c3ow">1</td>
    <td class="tg-c3ow">ISS (Near spindle)</td>
    <td class="tg-c3ow">ISS (Spindle)</td>
  </tr>
  <tr>
    <td class="tg-c3ow">2</td>
    <td class="tg-c3ow">ISS (Base)</td>
    <td class="tg-c3ow">ISS (Base)</td>
  </tr>
  <tr>
    <td class="tg-c3ow" colspan="2">Process</td>
    <td class="tg-c3ow">End-milling</td>
    <td class="tg-c3ow">End-milling, facing, drilling</td>
  </tr>
  <tr>
    <td class="tg-c3ow" colspan="2">Material</td>
    <td class="tg-c3ow">AL 6061, AISI 4140, AISI 1018</td>
    <td class="tg-c3ow">Cast iron</td>
  </tr>
  <tr>
    <td class="tg-c3ow" colspan="2">Total data length in second (Cutting time)</td>
    <td class="tg-c3ow">2789.97 (1032.97)</td>
    <td class="tg-c3ow">315.38 (119.908)</td>
  </tr>
  <tr>
    <td class="tg-c3ow" colspan="2">Cutting condition (Remark)</td>
    <td class="tg-c3ow">527 (limited to end-milling)</td>
    <td class="tg-c3ow">a few (inclduing end-milling, facing, and drilling)</td>
  </tr>
</tbody></table>

The CNC milling machine, schematic, and sensor deployment in each case are shown in [Figure 1](#figure1) and [Figure 1](#figure2). Both datasets utilized three sound sensors: one USB microphone to capture ambient noise and two Internal Sound Sensors (ISS) to capture sound directly from the target surface on the equipment. For more information about the ISS, please refer to [^5]. The ISS comprises a stethoscope and a USB microphone. All microphones used were the same model (K053, Fifine), and all stethoscopes were the same model (Littmann Classic III, 3M). 

Regarding sound data collection for each dataset, to collect sound data and stream sound signals from the sensors, an MTConnect adapter was developed which adheres to the MTConnect standard [^6]. This adapter was specifically designed for the sound sensors and was implemented on a Raspberry Pi. It was written in Python, utilizing the Advanced Linux Sound Architecture (ALSA) and the PyAudio module. Each data stream, represented by the *Displacement* type and *TimeSeries* in MTConnect, contains sound data sampled at 48 kHz, with a chunk size of 2<sup>11</sup> and a 16-bit depth resolution in mono-channel. Therefore, A single sample data stream in MTConnect includes 2048 sound sensor data points, covering approximately 42.67 milliseconds. Each data point within a sample data stream is separated by a space and evenly distributed over time. The timestamp of each sample data stream in MTConnect indicates the exact time of the last observation. Consequently, all data points within each sample data stream can be traced back to this timestamp.


<a id="figure1"></a>
![Figure 1](./figure/IMI_configuration.png)(#figure1)
*Figure 1: **IMI** sound data collection: (A) Schematic of hardware, (B) 3-axis mill (VM20i, Hurco), (C) Working area and Sensor 0, (D), Spindle and Sensor 1, and (E) Sensor 2*

<a id="figure2"></a>
![Figure 2](./figure/KRPM_configuration.png)
*Figure 1: **KRPM** sound data collection: (A) Schematic of sensor deployment, (B) 4-axis mill (HCN6000, Mazak), (C) Working area and Sensor 0, (D), Spindle and Sensor 1, and (E) Sensor 2*


[^1]: E. Kim, T. Bui, J. Yuan, S. C. Mouli, B. Ribeiro, R. A. Yeh, M. P. Fassnacht, and M. B. Jun, “Online real-time machining chatter sound detection using convolutional neural network by adopting expert knowl- edge,” Manufacturing Letters, 2024, (forthcoming).
[^2]: M. Mostafiz, E. Kim, A. Li, E. Bertino, M. B. Jun, and A. Shakouri, "Adversarial Domain Adaptation for Metal Cutting Sound Detection: Leveraging Abundant Lab Data for Scarce Industry Data," 2024 IEEE 22nd International Conference on Industrial Informatics (INDIN), (submitted).
[^3]: https://www.purdue.edu/in-mac/ (accessible on May 30, 2024).
[^4]: https://www.kirbyrisk.com/precision-machining (accessible on May 30, 2024).
[^5]: H. Yun, H. Kim, E. Kim, M. B., Jun, "Development of internal sound sensor using stethoscope and its applications for machine monitoring," Procedia Manufacturing, 2020, Jan 1;48:1072-8. https://doi.org/10.1016/j.promfg.2020.05.147.
[^6]: E. Kim, H. Yun, O. C. Araujo, M.B. Jun, "Sound recognition based on convolutional neural network for real-time cutting state monitoring of tube cutting machine," International Journal of Precision Engineering and Manufacturing-Smart Technology. 2023;1(1):1-8. https://doi.org/10.57062/ijpem-st.2022.0038.
