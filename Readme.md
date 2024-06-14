## Overview

The Gen-Parallel-Workloads repository contains generated and training data for job traces from various high-performance computing clusters, including `BW`, `Theta`, `Philly`, `Helios`, `SDSC - 95`, designed to facilitate the development and comparison of machine learning models for synthetic job trace generation.

## Structure

- **BW, Theta, Philly, Helios**: Directories for each cluster, containing:
  - **generated_data**: Synthetic traces generated by different ML models.
  - **training_data**: Original traces used to train the models.
- **SDSC-95**: Additional data including traces generated by statistical methods.
- **Readme.md**: Documentation of the repository.

## Models

Five machine learning models, listed below, are utilized to generate synthetic traces for each original workload or job trace. Please refer to the `Example` section below for more details on how these models are applied.

- **GAN (Generative Adversarial Network)**
- **CTGAN (Conditional GAN)**
- **TVAE (Tabular Variational Autoencoder)**
- **Gaussian Copula**
- **Copula GAN**

### Example

Original job traces from the Blue Waters dataset were used to train five models, producing five synthetic traces for each original trace (as shown in image below). This process was replicated for all listed datasets, providing a broad basis for analysis and comparison across different machine learning techniques.

![Example Image](example_image.png)

## Data Format

Each trace includes several key columns such as:
| Column Name | Description |
| ----------- | ----------- |
| **u id**        | A unique identifier assigned to each job |
| **user**        | User ID, an identifier assigned to distinct users |
| **gpu num**     | Number of GPUs a job uses |
| **cpu num**     | Number of CPUs a job uses |
| **node num**    | Number of Nodes a job uses |
| **interval**    | Time taken for a job to arrive after the previous job was submitted |
| **run time**    | Total time a job was running |
| **wall time**   | Total time a job spent in the system from submit to completion |
| **new status**  | Status of the job, when it was completed (Pass, Failed, Killed) |

## Citation

Please cite the following paper if you use this dataset or repository in your research:

```bibtex
@article{SoundarRaj2024Empirical,
  title={An Empirical Study of Machine Learning-based Synthetic Job Trace Generation Methods},
  author={Monish Soundar Raj and Thomas MacDougall and Di Zhang and Dong Dai},
  year={2024}
}
```