# Large Language Model Framework for Log Sequence Anomaly Detection

This repository contains the implementation of a model-agnostic framework for log sequence anomaly detection using large language models (LLMs), as described in the paper "Large Language Model Framework for Log Sequence Anomaly Detection." The framework leverages the Unsloth library to enable seamless integration and experimentation with various LLMs, such as Llama, Gemma, and Qwen, for detecting anomalies in log sequences.

## Overview

The proposed framework is designed to be flexible and modular, allowing users to easily switch between different LLMs without modifying the core codebase. It consists of three main components:
1. **Log Parsing**: Uses the Drain parser to extract log templates and generate log keys from raw log messages.
2. **Model Training**: Fine-tunes LLMs on normal log sequences to learn typical system behavior.
3. **Inference**: Employs Top-K prediction to flag anomalies when the actual log key does not appear among the K most probable next tokens.

The framework was evaluated on three benchmark datasets,HDFS, BGL, and Thunderbird, demonstrating competitive performance against state-of-the-art methods like LogGPT and LogLLaMA. It achieves high F1 scores, particularly with Gemma 3 and Llama 3.2, highlighting its effectiveness and adaptability.

## Datasets

All datasets used in this project (HDFS, BGL, and Thunderbird) were obtained and parsed using the code provided by the [LogGPT solution](https://github.com/nokia/LogGPT). These datasets are widely used benchmarks for log sequence anomaly detection.


## Usage

To use this framework, follow these steps:

1. **Training the Model**:
   - Run the `train.ipynb` Jupyter notebook to fine-tune the selected LLM on normal log sequences.

2. **Determining the Value of K**:
   - Run the `get_k.ipynb` Jupyter notebook to compute the optimal value of K for Top-K prediction.

3. **Testing the Model**:
   - Run the `test.ipynb` Jupyter notebook to evaluate the trained model on the test dataset (do not forget to change the K to the one obtained in the get_k.ipynb).