# FAIRSalud Documentation
Official Repo for the Data Curation Tool 2.0 of FAIRSalud project

## Observation Resource Transformation Workflow
This case of use demonstrates how the FAIRSalud platform transforms source data into a FHIR Observation resource through a six-stage workflow covered in five steps:
-> Upload
-> Terminology Service
-> Visual Mapping
-> Validation
-> FAIRness Assessment

### 1. Upload

The FAIRSalud Data Curation Tool (DCT 2.0) is an open-source, web-based solution designed for deployment within federated environments. The platform follows an ephemeral data processing approach when handling Electronic Health Records (EHRs), minimizing data persistence and supporting compliance with data sovereignty and privacy requirements.
Access to the platform is restricted to authorized institutions. Users must authenticate using credentials provided by the FAIRSalud technical support team, ensuring secure access to the FAIRification workspace.

![LoginPage](case_of_use/1.1.login.png)

#### FAIRification Workspace

After successful authentication, users are directed to the FAIRification Workspace. The interface is organized around a five-stage workflow that guides the transformation process from source data to FAIR-compliant FHIR resources.
A navigation panel on the left displays the workflow stages and remains visible throughout the process, allowing users to track their progress. The main panel provides contextual information and guidance for each step.

![NewFair](case_of_use/1.2.new_fair.png)

#### Data Upload

The platform supports the ingestion of data from multiple sources, including CSV, XLSX, PostgreSQL databases, and REDCap projects.
In this example, two files are uploaded:
- An XLSX dataset containing clinical information to be transformed into a FHIR Observation resource.
- A CSV file containing ICD-10 codes that will later be harmonized with SNOMED CT terminology during the semantic enrichment process.

![Upload](case_of_use/1.3.upload.png)

Additional features such as Loading panel in between pages to increase the feeling of dynamic workspace.

#### Workflow Initialization

Once the required files have been provided, the platform processes the uploaded content and prepares the environment for the subsequent FAIRification stages. A loading screen provides feedback on the current operation and ensures a smooth transition between workflow steps.

![Loading](case_of_use/1.4.loading_panel.png)

### Terminology Service

### Visual Mapping

### Validation

### FAIRness Assessment
