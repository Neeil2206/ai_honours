# Experiment No. 2

## Title

Structured JSON Extraction from Unstructured Engineering Fault Logs using Large Language Models.

---

## Objective

To extract important information from unstructured engineering fault logs and convert it into a structured JSON format using a Large Language Model (LLM).

---

## Problem Statement

Engineering fault logs contain important information such as incident ID, equipment name, failure type, severity, affected subsystems, and recommended actions. However, this information is often present in an unstructured textual format.

This experiment uses a Large Language Model to extract the required information from the unstructured fault log and organize it into a predefined JSON structure.

---

## Software Requirements

- Python 3.x
- VS Code
- Groq API
- OpenAI Python SDK
- python-dotenv
- Internet Connection

---

## Model Used

```text
Llama 3.3 70B Versatile
```

---

## Input Log

```text
URGENT LOG ENTRY - 02-AUG-2026 14:22 UTC
System alert raised on High-Pressure Boiler Unit #4. Thermal sensors detected 
overheating in the primary coolant intake loop and pressure relief valve B. 
Operator logged issue under INC-88201. Severity classified as CRITICAL. 
Immediate shutdown initiated and technician dispatch required to replace intake seals.
```

---

## JSON Structure

```json
{
  "incident_id": "string or null",
  "equipment_name": "string",
  "failure_type": "string",
  "severity": "string (CRITICAL, MAJOR, MINOR)",
  "affected_subsystems": ["list of strings"],
  "recommended_action": "string"
}
```

---

## Expected Output

```json
{
  "incident_id": "INC-88201",
  "equipment_name": "High-Pressure Boiler Unit #4",
  "failure_type": "Overheating in the primary coolant intake loop and pressure relief valve B",
  "severity": "CRITICAL",
  "affected_subsystems": [
    "Primary coolant intake loop",
    "Thermal sensors",
    "Pressure relief valve B"
  ],
  "recommended_action": "Immediate shutdown and technician dispatch to replace intake seals"
}
```

---

## Key Features

- Converts unstructured engineering fault logs into structured JSON.
- Uses an LLM for automated information extraction.
- Uses a constrained system prompt to control the output format.
- Requests JSON output using the API response format.
- Validates the generated output using Python's `json.loads()`.
- Handles fields that cannot be determined using `null`.

---

## Result

The unstructured engineering fault log was successfully processed and converted into a structured JSON object containing the incident ID, equipment name, failure type, severity, affected subsystems, and recommended action.
