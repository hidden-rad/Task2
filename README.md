# Task 2 README: 
# Regenerating Diagnostic Processes and Reports

Overview
This task focuses on generating reports based on crowd-sourced diagnostic impressions It aims to simulate the decision-making process of radiologists and produce an report that includes findings from initial impressions to final conclusions.

Data Description
Case_ID: A unique identifier for each case, used to match with the corresponding 'Ground truth' causality report. These reports are stored in the 'Causality Report' folder.
A1: Data representing the first impression of the case, gathered from crowd-sourcing.
A2: Data regarding the anatomical location, gathered from crowd-sourcing.
A3: Data related to thoracic spine levels, gathered from crowd-sourcing.
A4: Data representing the final impression of the case, gathered from crowd-sourcing.

Input
Reading process answers from crowd-sourcing data, covering impressions from A1 to A4.

Output
A report that contains causality information based on the diagnostic reasoning flow used by radiologists.

Steps for Data Use
Use diagnostic flow data from the "Hidden Rad" dataset (A1-A4) to simulate radiologists' reasoning.
Generate the report using your unique method (model) to align with the causality.
Refer to the 'Case_ID' to find the corresponding ground truth data for validation.

Task Objective
To create a comprehensive diagnostic report that aligns with radiologists' decision-making patterns using crowd-sourced impressions.
