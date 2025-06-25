# Multimodal-Driver-Safety-System-Using-EEG-and-Facial-Data

Multimodal Driver Safety Emotion Recognition Using EEG and Facial Features

This research presents an effective multimodal deep learning model for driver safety based on EEG signals and facial emotion features. It aims to monitor and analyze the cognitive state of a driver through the detection of patterns related to fatigue, distraction, and cognitive load. The integration of LSTM and Transformer models for EEG data and CNN-based facial emotion detection enables precise real-time emotion detection. The developed model identifies unsafe driver conditions for alerting.

Overview
Cognitive monitoring is essential in sophisticated driver safety systems. Camera stream or facial expression-based conventional approaches may be susceptible to degradation under low-light or occluded conditions. In the proposed project, EEG signals and facial expressions are combined together to provide a complete picture of the driver's mental state.

The project uses a multimodal pipeline that:

uses LSTM and Transformer networks to learn temporal and global features from EEG signals.

Utilizes a pre-trained CNN-based facial emotion model from actual-world data.

Blends EEG and facial embeddings for final emotion classification and threat detection.

Distinguishes emotional states into safe or risky driving states (alert, drowsy, distracted, cognitively overloaded).

Issues alerts when security thresholds are breached.

The EEG data (SEED-IV dataset) is made up of:

Multiples subjects' records

Four emotion classes' stimuli (happy, sad, fear, neutral)

EEG signals recorded at 1000Hz

Preprocessed as time-series FFT-based features across multiple channels

Facial Emotion Dataset:

Use the dima806/facial_emotions_image_detection model

Collects emotion probabilities (happy, sad, angry, etc.)

Reduces emotions to distraction/fatigue indicators

Model Architecture

EEG Branch (LSTM + Transformer)

LSTM Layers
Extract short-term temporal patterns in brain signals

Transformer Block
Employs multi-head self-attention to catch global context
Includes:

Attention masking

Layer normalization

Feed-forward neural net

Residual connections

Facial Emotion Branch (CNN)

Pre-trained model to predict facial emotion categories

Outputs are projected onto fatigue/distraction scores

Fusion Layer

Concatenates EEG and facial feature vectors

Dense layer learns cross-modal representations

Classification Head

Last softmax layer generates driving state classification

Labels: Alert, Fatigued, Distracted, Overloaded


Metric	EEG Only	Facial Only	Fused Model
Accuracy	92.10%	89.67%	96.28%
Precision	91.92%	89.34%	96.10%
Recall	91.88%	89.10%	96.22%
F1-Score	91.86%	89.02%	96.13%
Cohen’s Kappa	90.25%	86.88%	94.80%
