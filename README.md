# Task 2: Causal Explanation Generation from Structured Questionnaire Responses in Crowdsourced Chest X-ray Interpretation 

## Introduction
In Task 2, this alternative approach, without requiring the MIMIC data license, focuses solely on the structured questionnaire responses from radiologists. It allows participants to generate causal explanations based on radiologist-provided answers rather than directly on MIMIC reports or image data, potentially broadening accessibility for participants while keeping the focus on interpretative radiology analysis.

![Diagram for Task 2](./images/task2_diagram.png "Task 2 Overview")

## Task 2 Description

This task involves generating a causal explanation report for chest X-ray findings based on structured input derived from radiologists’ responses to a questionnaire. Unlike Task 1, Task 2 does not require the MIMIC license, as it relies solely on the answers to a specific set of questions provided by radiologists through crowdsourcing. This approach aims to enable participants without MIMIC data access to engage with the shared task while still emphasizing the clinical interpretative process.

### Input

The input data for Task 2 consists of radiologists’ responses to a structured questionnaire related to the assessment of chest X-ray images. This questionnaire includes a series of ordered questions designed to capture essential diagnostic information, structured as follows:
1.  First Impressions: Initial observations based on the X-ray, identifying general findings.
2.  Anatomical Location Identification: The anatomical region(s) of interest within the chest X-ray image where abnormalities may be present.
3.  Thoracic Spine Level Localization: Specification of the location in relation to the thoracic spine, aiding in precise abnormality localization.
4.  Final Impression: A revised conclusion based on the first impressions and location information, confirming or revising initial findings.

### Training set’s output

It is a report generated based on 28 structured checklists targeting specific abnormalities and their locations. These questions validate whether detected abnormalities substantiate the final impression as agreed upon by radiologists. The answers for the checklists are also collected by radiologists’ crowdsourcing work.

### Output

The output of Task 2 is a causal explanation report generated. This report should provide a structured, explanatory narrative that confirms or denies the final impression, using the detailed anatomical and abnormality-specific information obtained through the training set. The report should demonstrate a logical, evidence-based approach, articulating how individual findings support or contradict the final impression.

### Objective

The objective is to develop a system capable of producing a cohesive and clinically relevant explanation report that mirrors the reasoning and causal interpretation a radiologist might apply in a real-world diagnostic setting. Task performance will be evaluated by comparing the generated causal explanations against a ground-truth report, reflecting both the diagnostic accuracy and the interpretative quality of the causal reasoning.

## Data Format
The data for Task 2 is provided in CSV format, containing relevant information for each case in a structured tabular form. Each row in the CSV file represents a single case, with the following columns:

### Input part
#### A1 (First Impression): 
Initial observations by radiologists. This data serves as the starting point for diagnostic reasoning and may include preliminary hypotheses based on observed findings.<br>
Example: **'emphysema', 'pleural effusion', 'pneumothorax'**

#### A2 (Anatomical Location): 
Specific anatomical locations relevant to the case, helping narrow down the area of focus and refining the diagnostic flow.<br>
Example: **'Subcutaneous tissue', 'Parenchyme', 'RUL(Right Upper Lobe)', 'Parenchyme', 'RML(Right Middle Lobe)', 'Parenchyme', 'RLL(Right Lower Lobe)', 'Parenchyme', 'LUL(Left Upper Lobe)', 'Parenchyme', 'LLL(Left Lower Lobe)', 'Pleural', 'Right Pleural'**

#### A3 (Thoracic Spine Levels): 
Information on thoracic spine levels involved in the case, providing additional context for spine-related findings.<br>
Example: **{'begin': 1, 'end': 12}**

#### A4 (Final Impression): 
The concluding impressions by radiologists after evaluating all available information. This represents the final diagnostic insight derived from the data. <br>
Example: **'emphysema', 'pleural effusion', 'pneumothorax'**

### Ground-truth part
#### Causal section: 
A unique identifier for each case, used to locate the associated ground-truth causality report for validation.<br>
Example: **083663b6-04df-418e-a959-3d0a331d3d81**


Each of these components contributes to the overall diagnostic flow, replicating a radiologist’s structured thought process.

## Output
The output is a report that encapsulates the causality within the radiologists' diagnostic reasoning process, focusing on the causative relationships within the diagnostic flow. This report should interpret and connect the various data points (A1-A4) in a way that mirrors the diagnostic thought process, revealing the causal relationships embedded in the medical observations. The report must begin with the fixed heading "Causal Exploration:" followed by the causality analysis text that reflects the diagnostic flow and reasoning. This structured format is required for consistency.


## Process
- **Utilize Diagnostic Flow Data**: Use the diagnostic flow data (A1-A4) to reconstruct the reasoning path of a radiologist, simulating the process they might follow when examining similar cases.<br>
- **Generate Report Using Custom Model**: Develop your own method to integrate A1 through A4 into a coherent diagnostic report.<br>
- **Format the Report**: Structure the causality analysis into a clear format. Create a section titled "Causal Exploration" where you will output the analyzed causality based on the diagnostic flow data. The report must begin with the fixed heading **"Causal Exploration:"** followed by the causality analysis text. This structure is mandatory to ensure consistency across submissions. This "Causal Exploration" section should include all identified causal links and inferred reasoning derived from the input data (A1-A4). Submit this "Causal Exploration" section, not the full report. <br>
- **Validation and Case Matching**: Match each report with the ground-truth data associated with the 'Causal section' to validate the accuracy and completeness of your causality reasoning.<br>

## Example Output Structure
![Example for Task 2](./images/Task2_ex.png "Task 2 Example Structure")

