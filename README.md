# SOC-AI-Agents-for-Attack-Validation-and-Response-Automation

This project is a multi-agent AI system designed to reduce the gap between **attack detection and actual impact validation** in Security Operations Centers (SOC).

## Overview

SOCs frequently detect events such as SQL injection, command injection, path traversal, and abnormal authentication attempts. However, detection alone does not show whether the attack was blocked, failed, caused an error, or actually succeeded.

This system connects **detection → validation → response** to help analysts determine real impact and prioritize action faster.

## Architecture

### 1. Triage Agent
Analyzes suspicious events collected from SIEM and determines attack type, initial severity, and whether replay validation is needed.

### 2. Replay and Validation Agent
Reconstructs the original HTTP request and replays it in a controlled environment to determine whether the attack was blocked, failed, triggered an error, or likely succeeded.

### 3. Response and Orchestration Agent
Uses the outputs of the first two agents to generate incident priority, recommend actions, and connect results to SOC workflows such as ticketing, alerting, and response coordination.

## Key Features

- Collects suspicious attack logs from Splunk
- Classifies attack type and initial severity
- Reconstructs and replays HTTP requests
- Validates actual attack outcome based on server responses
- Distinguishes blocked, failed, error-inducing, and likely successful attacks
- Supports automated triage, escalation, and response workflows

## Why It Matters

Traditional SOC systems usually stop at detection.  
This project goes further by validating **what actually happened** after the detected request, helping improve triage quality, reduce manual investigation time, and prioritize incidents based on real impact.

## Tech Stack

- Splunk
- Python
- Flask / FastAPI
- HTTP replay module
- Rule-based logic + LLM
- SOAR / ticketing / Slack integration
