# Experiment No. 2

# Title

Structured JSON Extraction from Unstructured Engineering Fault Logs using Large Language Models.

---

# Aim

To extract relevant information from unstructured engineering fault logs and convert it into a structured JSON object using a Large Language Model (LLM).

---

# Theory

Engineering systems generate fault logs containing important information about incidents, equipment failures, severity, affected components, and recommended actions. However, these logs are often written in an unstructured textual format.

Large Language Models can understand natural language and identify important information from such unstructured text. The extracted information can then be organized into a predefined JSON structure.

## Structured Data Extraction

Structured data extraction is the process of identifying specific information from unstructured or semi-structured text and representing it in a predefined format.

In this experiment, the LLM extracts the following information:

- **Incident ID** – Unique identifier of the reported incident.
- **Equipment Name** – Name or identification of the affected equipment.
- **Failure Type** – Description of the detected failure.
- **Severity** – Classification of the incident as CRITICAL, MAJOR, or MINOR.
- **Affected Subsystems** – Subsystems affected by the failure.
- **Recommended Action** – Action required to handle or resolve the incident.

## JSON

JSON (JavaScript Object Notation) is a lightweight data format used to store and exchange structured information.

In this experiment, JSON is used to represent the information extracted by the LLM in a consistent and machine-readable format.

## Constrained System Prompt

A system prompt is used to define the role and behavior of the LLM.

The prompt instructs the model to act as an automated **Data Extraction Engine** and return only valid JSON according to the required structure.

## JSON Validation

After receiving the model response, Python's `json.loads()` function is used to validate whether the generated output is a valid JSON object.

This provides a programmatic validation step before the extracted data is used further.

---

# Software Used

- Python 3.x
- Visual Studio Code
- Groq API
- OpenAI Python SDK
- python-dotenv
- JSON library

---

# Model Used

```text
llama-3.3-70b-versatile
```

---

# Sample Input

```text
URGENT LOG ENTRY - 02-AUG-2026 14:22 UTC
System alert raised on High-Pressure Boiler Unit #4. Thermal sensors detected 
overheating in the primary coolant intake loop and pressure relief valve B. 
Operator logged issue under INC-88201. Severity classified as CRITICAL. 
Immediate shutdown initiated and technician dispatch required to replace intake seals.
```

---

# Required JSON Structure

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

# Procedure

1. Install Python and the required libraries.
2. Create a `.env` file and configure the Groq API key.
3. Load the environment variables using `python-dotenv`.
4. Initialize the OpenAI-compatible Groq client.
5. Define a system prompt containing the data extraction instructions and required JSON structure.
6. Provide the unstructured engineering fault log as input.
7. Send the system prompt and input text to the LLM.
8. Request the response in JSON format using `response_format`.
9. Receive the generated structured JSON response.
10. Remove unnecessary Markdown code-block characters if present.
11. Validate the output using Python's `json.loads()` function.
12. Display the extracted equipment name, severity, and recommended action.
13. Record the result and capture screenshots of the program and output.

---

# Experimental Result

The unstructured engineering fault log was successfully converted into a structured JSON object.

### Extracted Information

| Field | Extracted Value |
|-------|-----------------|
| Incident ID | INC-88201 |
| Equipment Name | High-Pressure Boiler Unit #4 |
| Failure Type | Overheating in the primary coolant intake loop and pressure relief valve B |
| Severity | CRITICAL |
| Affected Subsystems | Primary coolant intake loop, Thermal sensors, Pressure relief valve B |
| Recommended Action | Immediate shutdown and technician dispatch to replace intake seals |

---

# Result Analysis

The experiment demonstrated that the LLM was able to identify important information from an unstructured engineering fault log and organize it according to the predefined JSON structure.

The incident ID was extracted from the log, while the equipment name was identified as **High-Pressure Boiler Unit #4**. The failure information described overheating in the primary coolant intake loop and pressure relief valve B.

The model also identified the severity as **CRITICAL** because the input explicitly classified the incident as critical. The recommended action was extracted from the instruction for immediate shutdown and technician dispatch.

The generated response was then passed through Python's JSON parser. Successful parsing confirmed that the returned output was a valid JSON object.

---

# Key Learning Outcomes

- Understood the concept of structured information extraction using LLMs.
- Learned how to convert unstructured engineering logs into JSON.
- Learned how to use a system prompt to control LLM output.
- Gained practical experience using the Groq API with Python.
- Learned how to request JSON responses from an LLM.
- Learned how to validate generated JSON programmatically using Python.
- Understood the importance of machine-readable output for further data processing.

---

# Advantages

- Reduces manual extraction of information from fault logs.
- Converts text into a consistent machine-readable format.
- Can be used for automated engineering monitoring systems.
- Makes extracted information easier to store and process.
- JSON output can be integrated with other software systems.

---

# Conclusion

The experiment successfully demonstrated the use of a Large Language Model for extracting structured information from an unstructured engineering fault log.

The LLM identified the incident ID, equipment name, failure type, severity, affected subsystems, and recommended action and organized them into a JSON object.

The generated JSON was programmatically validated using Python, confirming that the output could be processed as a valid JSON object.

Therefore, LLM-based structured extraction can be useful for converting unstructured engineering logs into machine-readable information for further analysis and automation.

---

# Screenshots

## Program Code

![Program Code](OUTPUT/exp%202%20code.png)

---

## Program Output

![Program Output](OUTPUT/output%20exp2.png)
