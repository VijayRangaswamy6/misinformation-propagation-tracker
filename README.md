# Social Media Misinformation Propagation Tracker

A system for detecting misinformation on social media and predicting its potential spread using semantic analysis, network diffusion modeling, and agentic AI reasoning.

This project goes beyond traditional fake news detection by estimating **how far misinformation can propagate** and assigning an **explainable risk score** for real-world intervention.

## Overview

Misinformation spreads rapidly on social media, often faster than manual verification methods can respond. Most existing solutions focus only on content classification and fail to consider network effects.

This system answers two critical questions:

* Is the content misinformation?
* If yes, how dangerous can it become?

## Features

* BERT-based semantic misinformation detection
* MongoDB-based graph modeling (no dedicated graph database)
* Information diffusion simulation using Independent Cascade Model
* Multi-step agentic reasoning for explainable risk assessment
* Low-latency, real-time processing pipeline
* Scalable and production-ready architecture

## System Architecture

Social Media Data
↓
MongoDB Storage (posts, edges, chains)
↓
BERT Classifier (FAKE / REAL + confidence)
↓
Cascade Simulator (Independent Cascade Model)
↓
Agentic Reasoning Engine
↓
Risk Score & Final Analysis

## Tech Stack

* Python — Core implementation
* BERT (Transformers) — Semantic text classification
* MongoDB — Data storage and graph modeling
* Independent Cascade Model — Propagation prediction
* NetworkX — Graph construction
* NumPy — Statistical computation

## Project Structure

├── database/
│   └── misinformation_database.py
├── models/
│   └── misinformation_classifier.py
├── simulation/
│   └── cascade_simulator.py
├── reasoning/
│   └── misinformation_reasoning_agent.py
├── integration/
│   └── misinformation_tracker.py
├── main.py
├── requirements.txt
└── README.md

## Database Schema

| Collection  | Purpose                                              |
| ----------- | ---------------------------------------------------- |
| posts       | Stores social media posts                            |
| edges       | Stores propagation relationships (retweets, replies) |
| post_chains | Groups related posts into cascades                   |
| analysis    | Stores final risk assessments                        |

MongoDB is used to represent graph-like structures efficiently without requiring a specialized graph database.

## Risk Scoring

The final risk score combines content reliability and spread potential:

Risk Score = 0.6 × Spread Risk + 0.4 × Content Risk

Risk Levels: LOW / MEDIUM / HIGH

## Performance

| Metric             | Result                     |
| ------------------ | -------------------------- |
| Accuracy           | 95.3%                      |
| F1 Score           | 0.953                      |
| Spread Correlation | 0.71                       |
| Latency            | 1.355 seconds              |
| Scalability        | Tested up to 10,000+ posts |


## Sample Output

Classification: FAKE (Confidence: 92%)
Predicted Reach: 3.2 posts
Risk Score: 0.67
Risk Level: HIGH

## Limitations

* No time-based decay in propagation probability
* Uniform user influence assumptions (no influencer/bot modeling)
* Paraphrased claims not semantically clustered
* Designed primarily for Twitter-like platforms

## Future Work

* Time-aware diffusion modeling
* Influencer and bot-aware propagation
* Semantic claim clustering for paraphrased misinformation
* Cross-platform generalization

## Academic Context

* Course: DSC302A – Big Data
* Institution: Ramaiah University of Applied Sciences
* Author: Vijay Rangaswamy

## License

For academic and educational use only.

Detecting misinformation is not enough — predicting its impact is what matters.
