# Anuran Calls (MFCCs) Dataset

## Overview

The **Anuran Calls (MFCCs)** dataset contains acoustic features extracted from syllables of frog calls, along with taxonomic labels for family, genus, and species.

The dataset was developed for classification tasks related to automatic anuran species recognition using bioacoustic signals.

## Dataset Information

| Attribute | Description |
|---|---|
| Dataset Name | Anuran Calls (MFCCs) |
| Number of Instances | 7,195 |
| Number of Features | 22 |
| Feature Type | Mel-Frequency Cepstral Coefficients (MFCCs) |
| Classification Labels | Family, Genus, Species |
| Additional Column | RecordID |
| Number of Families | 4 |
| Number of Genera | 8 |
| Number of Species | 10 |

The dataset was created by segmenting **60 audio recordings** collected from individual frogs.

Each recording corresponds to one specimen, and the resulting syllables were extracted as individual observations for classification.

## Data Collection and Processing

The audio recordings were collected under real-world environmental conditions, including background noise.

Recording locations include:

- Federal University of Amazonas, Manaus, Brazil
- Atlantic Forest (Mata Atlântica), Brazil
- Córdoba, Argentina

The original recordings were stored in WAV format with the following specifications:

- **Sampling Frequency:** 44.1 kHz
- **Bit Depth:** 32 bits
- **Maximum Analyzable Frequency:** Approximately 22 kHz

### Segmentation

Audio segmentation was performed using:

- Spectral entropy
- Binary clustering

These methods were used to identify audio frames corresponding to individual frog-call syllables.

Segmentation and feature extraction were performed in MATLAB.

The segmentation process produced **7,195 syllables**, which became the observations used for classification.

### Feature Extraction

For each extracted syllable, **22 Mel-Frequency Cepstral Coefficients (MFCCs)** were calculated using 44 triangular filters.

Because syllables have different lengths, the MFCC values were normalized for each observation.

The normalization procedure was:

$begin:math:display$
\\text\{MFCC\}\_\{i\,\\text\{normalized\}\}
\=
\\frac\{\\text\{MFCC\}\_i\}
\{\\max\(\|\\text\{MFCC\}\_i\|\)\}
$end:math:display$

The normalized coefficients fall within the range:

$begin:math:display$
\-1 \\leq \\text\{MFCC\} \\leq 1
$end:math:display$

## Class Distribution

The dataset contains three hierarchical classification labels:

- Family
- Genus
- Species

### Family Distribution

| Family | Instances |
|---|---:|
| Bufonidae | 68 |
| Dendrobatidae | 542 |
| Hylidae | 2,165 |
| Leptodactylidae | 4,420 |
| **Total** | **7,195** |

### Genus Distribution

| Genus | Instances |
|---|---:|
| Adenomera | 4,150 |
| Ameerega | 542 |
| Dendropsophus | 310 |
| Hypsiboas | 1,593 |
| Leptodactylus | 270 |
| Osteocephalus | 114 |
| Rhinella | 68 |
| Scinax | 148 |
| **Total** | **7,195** |

### Species Distribution

| Species | Instances |
|---|---:|
| AdenomeraAndre | 672 |
| AdenomeraHylaedactylus | 3,478 |
| Ameeregatrivittata | 542 |
| HylaMinuta | 310 |
| HypsiboasCinerascens | 472 |
| HypsiboasCordobae | 1,121 |
| LeptodactylusFuscus | 270 |
| OsteocephalusOophagus | 114 |
| Rhinellagranulosa | 68 |
| ScinaxRuber | 148 |
| **Total** | **7,195** |

## Dataset Structure

The dataset contains:

- **22 numerical features:** MFCC coefficients
- **3 categorical labels:** Family, Genus, Species
- **1 identifier:** RecordID

The MFCC coefficients serve as predictor variables, while the taxonomic labels serve as classification targets.

The RecordID identifies the original audio recording associated with each observation.

## Applications

The dataset has been used in research involving:

- Automatic frog species recognition
- Bioacoustic signal classification
- Hierarchical classification
- Feature subset selection
- Acoustic signal segmentation
- Wireless sensor networks
- Machine learning for biodiversity monitoring

## Contributors

The dataset was developed by researchers affiliated with the **Universidade Federal do Amazonas**, Brazil.

- **Juan Gabriel Colonna** — Engineering and Research
- **Eduardo Freire Nakamura** — Professor
- **Marco A. P. Cristo** — Professor
- **Marcelo Gordo** — Biologist and Collaborator

**Institution:**

Universidade Federal do Amazonas  
Av. General Rodrigo Octavio Jordão Ramos, 1200  
Coroado I, Manaus - AM, 69067-005, Brazil

## Relevant Publications

1. Colonna, J. G., Cristo, M., Salvatierra, M., & Nakamura, E. F. (2015). An incremental technique for real-time bioacoustic signal segmentation. *Expert Systems with Applications, 42*, 7367–7374.

2. Colonna, J. G., Gama, J., & Nakamura, E. F. (2016). How to correctly evaluate an automatic bioacoustics classification method. In *17th Conference of the Spanish Association for Artificial Intelligence (CAEPIA)* (pp. 37–47). Springer International Publishing.

3. Colonna, J. G., Gama, J., & Nakamura, E. F. (2016). Recognizing family, genus, and species of anuran using a hierarchical classification approach. *Lecture Notes in Computer Science, 9956*, 198–212.

4. Colonna, J. G., Ribas, A. D., Santos, E. M., & Nakamura, E. F. (2012). Feature subset selection for automatically classifying anuran calls using sensor networks. In *Proceedings of the International Joint Conference on Neural Networks (IJCNN 2012)* (pp. 1–8). IEEE.

5. Colonna, J. G., Peet, T., Ferreira, C. A., Jorge, A. M., Gomes, E. F., & Gama, J. (2016). Automatic classification of anuran sounds using convolutional neural networks. In *Proceedings of the Ninth International C* Conference on Computer Science & Software Engineering* (pp. 73–78). ACM.

6. Colonna, J. G., Cristo, M., & Nakamura, E. F. (2014). A distributed approach for classifying anuran species based on their calls. In *Proceedings of the 22nd International Conference on Pattern Recognition (ICPR)* (pp. 1242–1247). IEEE.

7. Ribas, A. D., Colonna, J. G., Figueiredo, C. M. S., & Nakamura, E. F. (2012). Similarity clustering for data fusion in wireless sensor networks using k-means. In *Proceedings of the International Joint Conference on Neural Networks (IJCNN 2012)* (pp. 1–7). IEEE.

8. Diaz, J. M., Colonna, J. G., Soares, R. B., Figueiredo, C. M. S., & Nakamura, E. F. (2012). Compressive sensing for efficiently collecting wildlife sounds with wireless sensor networks. In *Proceedings of the 21st International Conference on Computer Communications and Networks (ICCCN 2012)* (pp. 1–7). IEEE.

## Citation and Acknowledgements

The dataset contributors request that users cite relevant publications when using the dataset in academic or research projects.

For classification tasks involving family, genus, and species labels, the following publication is particularly relevant:

> Colonna, J. G., Gama, J., & Nakamura, E. F. (2016). Recognizing family, genus, and species of anuran using a hierarchical classification approach. *Lecture Notes in Computer Science, 9956*, 198–212.
