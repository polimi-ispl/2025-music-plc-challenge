# IEEE-IS² 2025 Music Packet Loss Concealment Challenge
Welcome to the official repository for the for the [IEEE-IS² 2025 Music Packet Loss Concealment Challenge](https://internetofsounds2025.ieee-is2.org/workshops/3rd-ieee-international-workshop-networked-immersive-audio/music-packet-loss-concealment)!

## Introduction
After the success of last year’s inaugural edition, we are glad to announce that the IEEE-IS² Music Packet Loss Concealment Challenge is coming back in 2025!

The **IEEE-IS² Music Packet Loss Concealment Challenge** aims to promote research on Packet Loss Concealment (PLC) for Networked Music Performance (NMP) applications.

Packet loss, either by missing packets or high packet jitter, is one of the main problems and, in turn, engineering challenges in real-life NMP. While PLC for Voice over IP has recently attracted a great deal of attention, PLC for NMP applications has been considerably less studied. 

This year’s challenge follows the same format as the 2024 edition, with a few important updates to reflect the importance of real-time performance in practical applications (see **Evaluation Rules**).

We invite researchers and practitioners in signal processing, machine learning, and audio technologies at large to take part in the second edition of the challenge.

The **IEEE-IS² 2025 Music Packet Loss Concealment Challenge** is a satellite event of the 6th IEEE International Symposium on the Internet of Sounds ([IEEE IS² 2025](https://internetofsounds2025.ieee-is2.org)), which will take place in L'Aquila, Italy, October 29–31, 2025.

## Challenge Prizes 🏆
We are thrilled to announce that the three top-ranked teams will be awarded prizes for a total of **800€**, thanks to the generous sponsorship of **Sennheiser Electronic SE & Co. KG.**   
 
The awards for the highest-ranked submissions are:

🥇 **1st place:** 500€ 

🥈 **2nd place:** 200€

🥉 **3rd place:** 100€

We look forward to receiving your contributions—best of luck to all participants!

## Important Dates
- [x] **February 10, 2025** – Challenge start
- [ ] **May 25, 2025** – Release of blind test set
- [ ] **June 2, 2025** – Challenge submissions due (11:59 PM CET)
- [ ] **September 29, 2025** – (tentative) Notification of evaluation results
- [ ] **October 29–31, 2025** – Symposium dates
  
## Problem Formulation

Packet-switched networks often rely on best-effort protocols that prioritize speed over reliability. This means there are no guarantees that audio data packets will be correctly transmitted. In fact, excessive delays due to high packet jitter or missing packet may cause gaps in the audio stream at the receiver end.

In NMP applications, the packet size is typically determined by the buffer of the soundcard from which audio data is read. Whereas small buffer sizes are sometimes preferred, the Challenge addresses the more challenging scenario of the packet size being **512 samples**, corresponding to approximately 11.6 ms at a sampling rate of 44.1 kHz. 

All PLC methods submitted to the IEEE-IS² 2025 Music Packet Loss Concealment Challenge are expected to be able to process real-world music signals in a 16bit-44.1kHz WAV format.

Moreover, this year’s Challenge will focus on **causal systems only**. Namely, at any given time, only previously received packets or prediction thereof may be used to predict the next audio frame. In other words, **systems are not allowed any look-ahead**. Please note that this is different from other audio deep PLC challenges. 

Therefore, **non-causal approaches will not be considered eligible for the Challenge** and will be thus excluded from the final ranking. Other than that, there are no limitations on the proposed PLC methods, which may comprise one or more deep-learning models, traditional signal processing algorithms, or a hybrid approach.

## Registration Procedure

To enter the Challenge, please register on the [**IEEE IS² 2025 EasyChair portal**](https://easychair.org/conferences/?conf=ieeeis22025) by the Challenge registration deadline (see **Important Dates**).

On EasyChair, 
*	Select "make a new submission" in the Author Console.
*	Select "2nd Music Packet Loss Concealment Challenge" as Track.
*	Enter title, abstract, and register all team members as "Authors."
*	Upload (temporary) placeholder files and complete the submission.

The final files (see **Submission Rules**) can be uploaded by updating an existing submission at any time before the Challenge submission deadline (see **Important Dates**).

**Every team is allowed to submit only one (1) PLC system for evaluation.**

**Note that registration to the 6th IEEE International Symposium on the Internet of Sounds is <ins>not</ins> mandatory to participate in the Challenge.**

## Submission Rules

Once the blind test set is released, every team is required to:
*	Download the blind test set.
*	Process each and every degraded audio clip using the proposed PLC method.
*	Save the enhanced audio clips as 16bit-44.1kHz single-channel wav files making sure to use the same filenames of the corresponding degraded audio clips. 
*	Compress the enhanced audio files into a single zip file.
*	Upload the resulting zip file on a cloud storage service.
*	Make sure that the zip file can be downloaded without access restrictions.

Then, each team should submit the following files through [EasyChair](https://easychair.org/conferences/?conf=ieeeis22025):
-	A technical report in PDF format detailing the approach `[Upload as: Paper]`
-	A txt file containing: `[Upload as: Supplemental material]`
	- a permanent link to a public repository (e.g., GitHub) hosting the project code.
    - a permanent link to a cloud storage service (e.g., Dropbox) hosting the enhanced audio clips processed with the proposed PLC system. Please make sure that download is enabled without access restrictions.

**The cloud storage folder must host a single zip file containing the enhanced audio files. Make sure that you zip as many audio clips as there are in the blind test set. Every enhanced clip should have the same filename as the corresponding degraded clip. Do not upload the degraded audio clips from the blind test set or any other file to the cloud storage folder.**

Only teams that upload all the required material will be considered eligible for participating in the evaluation process. **<ins>Important</ins>: please make sure that the Supplemental material contains both the link to the enhanced audio clips and the link to the project repo.**

### Technical Reports

Technical reports should not exceed four (4) pages of scientific content (including tables and figures) + one (1) optional page for references only. 

Technical reports should describe the proposed approach and provide all the details to ensure reproducibility. Authors may choose to report additional objective/subjective metrics in their paper. At the end of the Challenge, technical reports will be made available on the [Internet of Sounds Research Network website](https://internetofsounds.net/).

Please note that **technical reports will <ins>not</ins> be included in the Symposium Proceedings**. 

Nevertheless, authors are warmly encouraged to submit regular papers outlining their PLC method to the main conference track. Regular papers will undergo the normal peer-review process, whereas technical reports will not. 

**Paper acceptance and registration to the conference are <ins>not</ins> required for taking part in the 2025 Music Packet Loss Concealment Challenge.**

### Official Templates

For drafting the technical report, please use the same LaTeX and Word template as of regular IEEE IS² papers. **Official templates can be found here:** [IEEE conference templates](https://www.ieee.org/conferences/publishing/templates.html)

## Evaluation Rules
Please note that the evaluation rules have changed from the 2024 edition.

### Blind Test Set
The blind test set consists of several single-channel audio clips in a 16bit-44.1kHz wav format. Every file consists of a short clip of a solo-instrument performance.

The audio clips are artificially degraded by dropping packets according to predetermined “packet traces,” i.e., text files containing a string of binary digits: 0 if a packet was correctly received and 1 if the packet was lost. Every digit in a packet trace corresponds to 512 samples. Traces do not contain explicit temporal information, and the packet rate is implicitly determined by the audio sampling rate.

The packet traces used to create the blind test set were repurposed from the INTERSPEECH 2022 Audio Deep Packet Loss Concealment Challenge ([Microsoft GitHub](https://github.com/microsoft/PLC-Challenge)). 

Said traces are divided into three subsets according to the maximum burst loss length:

*	**Subset 1.** Bursts of up to 6 consecutive packets 
*	**Subset 2.** Bursts of 6 to 16 consecutive packets
*	**Subset 3.** Bursts of 16 to 50 consecutive packets
  
We sample packet traces from subset 1 (with high probability) and subset 2 (with low probability). We do not sample traces from subset 3.

The resulting packet traces will be made available in txt format along with the corresponding degraded audio clips. In practice, such a degradation consists of filling the missing packets with zeros in the waveform domain. 

The blind test set will be released shortly before the Challenge submission deadline.

Participants are forbidden from using the blind test set to retrain or tune their models. They should not submit results using other PLC methods other than the one they have developed. **Failing to adhere to these rules will lead to disqualification from the Challenge.**

### Evaluation Procedure

Once the blind test set is made available, participants should process every track using their own PLC system, create a single zip file containing all the resulting audio clips, upload the zip file on a cloud storage service, and submit a permanent link through EasyChair.

Please do not upload audio files or model weights on EasyChair.

**Participants must save each enhanced clip using the same filename of the corresponding degraded audio file. Failing to do so would make it impossible to automate the evaluation process and may result in the exclusion of the team’s submission from the final ranking.**

**Note that any ex-post manual intervention on the audio files or any ad-hoc post-processing is forbidden. Every clip in the blind test set should be processed using the proposed PLC method only.**

**<ins>Main evaluation</ins>:** The final ranking will be determined through a listening test involving a curated subset of the audio clips included in the blind test set. As last year, the evaluation will involve a modified **MUSHRA test** (ITU-R Recommendation BS.1534-3). 

**<ins>Pre-screening</ins>:** If we receive a high volume of submissions, conducting a large-scale MUSHRA test may not be feasible. In that case, we may implement a pre-screening round based on objective metrics to narrow down the number of entries that will take part in the main evaluation phase.

In the MUSHRA test, the enhanced clips from each team will be assigned a score on a scale of 0 to 100. For each clip, assessors will be tasked to identify the “Hidden Reference,” i.e., the clean untampered signal, and assign it the highest possible score. At the same time, assessors will be presented with an “Anchor,” i.e., the lower bound of the perceptual scale. Here, zero-filled lossy signals from the blind test set will be used as Anchors.

If needed, the submitted audio clips will be converted to mono via channel average and saved as 16bit-44.1kHz wav files before the evaluation. Please consider that this procedure is automated and might affect the audio quality of your submission. Please upload audio in the right format in the first place.

### Real-Time Performance

Practical PLC systems should take less than a stride length (in ms) to process the next frame. This means that, overall, submitted methods should take less than 11.6 ms to estimate the next 512-sample packet.

**<ins>All participants are required to self-assess the real-time performance of their PLC systems</ins>** by reporting the total number of model parameters and the average time needed to process a single packet on an Intel Core i5 quad-core machine clocked at 2.4 GHz or equivalent processors.

**<ins>Top-ranked teams are required to satisfy real-time constraints in order to be eligible for a prize.</ins> The organizers will reach out to prospect winners to coordinate practical evaluation.**

## Training Data

We do not provide training data, nor do we indicate a list of eligible training datasets. 

However, we prescribe that all training data is exclusively taken from publicly-available freely-accessible audio datasets, i.e., proprietary and commercial datasets should not be used for training the proposed PLC systems. This rule applies to any type of training, including pretextual pre-training and fine-tuning.

Every team should disclose the datasets used to train the final model, provide links or references in the technical report, and specify the amount/duration of audio taken from each and every dataset.

Data can be augmented in any way that improves the performance of the models. However, metadata and other auxiliary information other than packet loss traces, if present, should be disregarded and should not be passed to the model in any way. 

Participants are strictly prohibited from employing the blind test set for any training or fine-tuning purposes.

## Validation Data

To help development, we are making the test set from last year’s IEEE-IS² 2024 Music Packet Loss Concealment Challenge publicly available. Participants can use this dataset to benchmark their methods. However, please note that this dataset and the 2025 blind test set may differ significantly.

* **Download the dataset [here](https://polimi365-my.sharepoint.com/:f:/g/personal/10391311_polimi_it/EsXcdjz3YZFKgdDVfQBwtOwBB7tXLAPuVVlcvZmKlIkt4A?e=eLnSfX)** 📂

## Baseline System

The IEEE-IS² 2025 Music Packet Loss Concealment Challenge will make use of the same baseline model as the 2024 edition.

The baseline system, named **PARCnet-IS²**, comprises a linear predictor (LP) and a lightweight feedforward CNN. The LP is fitted in real-time within a sliding context window using the autocorrelation method with white noise compensation, whereas the CNN is trained to estimate the LP residual. More information can be found in last year’s Challenge report 📝 [arXiv preprint](https://arxiv.org/abs/2409.18564).

* **The pre-trained PARCnet-IS² model and inference code are available [here](https://github.com/polimi-ispl/2024-music-plc-challenge/tree/main/parcnet-is2)** 📌

If you use PARCnet-IS² in your research, please cite:
```
@article{mezza2024hybrid,
  author={Mezza, Alessandro Ilic and Amerena, Matteo and Bernardini, Alberto and Sarti, Augusto},
  journal={IEEE Open Journal of Signal Processing}, 
  title={Hybrid Packet Loss Concealment for Real-Time Networked Music Applications}, 
  year={2024},
  volume={5},
  number={},
  pages={266-273},
  doi={10.1109/OJSP.2023.3343318}}
```

## Video Presentations

The winning teams are invited to record a brief video presentation showcasing their method, which will be featured in the final Challenge presentation at the 6th IEEE International Symposium on the Internet of Sounds ([IEEE IS² 2025](https://internetofsounds2025.ieee-is2.org)) in L’Aquila, Italy, October 29–31, 2025.

The organizers will reach out to the top-ranking teams to coordinate the video recordings. While this is optional and not mandatory, we highly encourage teams to take advantage of this opportunity to share their insights with the community.

## Contacts

For questions, please contact [music.plc.challenge@gmail.com](mailto:music.plc.challenge@gmail.com)

## Organizers
*	**Alessandro Ilic Mezza** (Politecnico di Milano)
*	**Alberto Bernardini** (Politecnico di Milano)

-------------------

<p align="center">
<img src="/resources/Sennheiser-logo-new.png" width="250" />
<img src="/resources/RESTART-logo.png" width="250" />
<img src="/resources/ispl1.png" width="250" />
</p>
