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
- A CSV file containing ICD-10 codes that will be harmonized with SNOMED CT terminology during the semantic enrichment process.

![Upload](case_of_use/1.3.upload.png)

Additional features such as Loading panel in between pages to increase the feeling of dynamic workspace.

#### Workflow Initialization

Once the required files have been provided, the platform processes the uploaded content and prepares the environment for the subsequent FAIRification stages. A loading screen provides feedback on the current operation and ensures a smooth transition between workflow steps.

![Loading](case_of_use/1.4.loading_panel.png)

### 2. Terminology Service

When the workspace has been initialized and the source data uploaded, the workflow proceeds to the Terminology Service stage. This component supports semantic harmonization by enabling researchers to align local codes and textual values with standardized terminologies.
To facilitate this process, the platform provides a preview of the uploaded datasets, displaying the first records and the distinct values available for each column. This allows users to inspect the data before performing terminology operations.
In addition to data exploration, the Terminology Service offers several semantic enrichment capabilities, including:
- Code-to-code translation between standard terminologies (ICD-10, LOINC, SNOMED CT, and ATC).
- Text-to-code matching, enabling free-text values to be associated with standardized concepts.
- Terminology lookup and concept exploration to support informed decision-making during the FAIRification process.

![Terminology](case_of_use/2.1.terminology_service.png)

#### Terminology Translation

In this use case, the CSV file containing diagnostic codes is selected and the `icd10-diagnosis` column is chosen as the source field. The **Code Translation** operation is then configured to translate ICD-10 concepts into SNOMED CT concepts.

![CodeTranslation](case_of_use/2.2.code_translation.png)

If the configuration is complete, the terminology service is executed and the translation process begins.

![CodeLoading](case_of_use/2.3.run_codetrans.png)

#### Reviewing Terminology Suggestions

After the translation has finished, the platform presents the candidate mappings identified for each source code.
In many cases, a single equivalent concept can be identified automatically. However, when multiple candidate concepts are available, user validation is required to determine the most appropriate semantic match. This semi-automated approach combines computational assistance with expert knowledge, improving the quality and reliability of the resulting mappings.

![Suggestions](case_of_use/2.4.terminology_suggestions.png)

Once the terminology mappings have been reviewed and accepted, the translated concepts can be stored within the working dataset. These harmonized values become available for subsequent workflow stages, ensuring that the mapping process is based on standardized and interoperable terminology.

![Stored](case_of_use/2.5.suggestions_stored.png)

### Visual Mapping

### Validation

### FAIRness Assessment
