# MLH Software Engineering Code Sample

This README showcases my contributions to the [scribe-data open-source project](https://github.com/scribe-org/Scribe-Data). Below are examples of pull requests I worked on, with links and summaries of each.

---

## 1. [Moving from Old Language Metadata Structure to Support Sub-languages and Simplified JSON ](https://github.com/scribe-org/Scribe-Data/pull/402)

- **Description**  
  This PR introduces several enhancements to the Scribe-Data project, focusing on improving language metadata handling, simplifying utility functions, and enhancing the CLI's robustness. Key updates include restructuring how languages and their sub-languages are managed, updating test cases to reflect new features, and improving documentation for contributors.

---
- **Highlights**  
  - **Refactored Language Metadata**:
    - Migrated the structure of `language_metadata.json` to support a more modular and extensible representation, including sub-languages.
    - Centralized sub-language handling logic into utility functions like `format_sublanguage_name()` and `list_all_languages()` for consistency.
  - **CLI Enhancements**:
    - Improved the display of languages and their attributes in CLI commands, supporting nested sub-languages in listings.
  - **Testing and Validation**:
    - Added robust error handling and validations for invalid languages and data types.
    - Updated existing unit tests and added parameterized tests to validate the new sub-language features.

---

- **Key Impacts**  
  - **User Experience**: Improved clarity and usability of CLI commands, especially for language-specific queries and data manipulations.
  - **Developer Efficiency**: Simplified and centralized logic reduces duplication and potential bugs, making it easier to add new languages or features in the future.
  - **Scalability**: Restructured language metadata to handle a wider range of languages and sub-languages, ensuring compatibility with diverse linguistic datasets.
  - **Testing Coverage**: Strengthened test suite to capture edge cases and validate new functionality, ensuring reliability and reducing regression risks.

---

## 2. [Add identifier_case option to convert camelCase to snake_case and update documentation](https://github.com/scribe-org/Scribe-Data/pull/486)

- **Description**:  
  This PR introduces an enhancement to the CLI tools by adding support for configurable identifier case formats. Users can now specify whether the identifiers in output data should follow camelCase (default) or snake_case, improving flexibility in data formatting. The changes include updates to CLI commands, new parameters in data conversion functions, and corresponding updates in documentation and tests.

- **Highlights**:  
  - Added a new CLI parameter (`--identifier-case`) to support camelCase and snake_case formatting.  
  - Modified core functions (`convert_to_json`, `convert_to_csv_or_tsv`, `convert_to_sqlite`, etc.) to handle identifier case transformation dynamically.  
  - Implemented a utility function `camel_to_snake` for consistent conversion.  
  - Updated documentation (`cli.rst`) to reflect the new functionality.  
  - Enhanced test coverage to validate the new feature.

---
- **Key Impact**:  
  - Improves usability by accommodating different coding standards for identifier formatting.  
  - Ensures consistency in case conversion across multiple data export formats (JSON, CSV, TSV, SQLite).  
  - Strengthens code reliability with comprehensive unit tests for the new feature.  

**_________________________________________________________________________________________________________________________________________________**



## Workflow: SPARQL Query Validation

### Overview  
This workflow introduces extensive validation for SPARQL queries to ensure accuracy and adherence to metadata-driven standards. It focuses on variable order, QID validation, optional statements, and docstring consistency.

### Objectives  
- Validate and enforce proper order of variables in `SELECT` and `WHERE` clauses.  
- Ensure alignment of QIDs in optional statements with metadata criteria.  
- Standardize SPARQL docstring formatting.  
- Maintain consistency in variable order across query components.

### Implementation Details  

1. **Validation of SELECT and WHERE Clause Variable Orders**  
   - **[PR 1: Check SELECT-WHERE Label Order](https://github.com/scribe-org/Scribe-Data/pull/481)**  
     - Implemented the `check_forms_order` function to validate that `SELECT` clause variables match their order in the `WHERE` clause.  
     - Handles labeling services and ensures consistency in variable alignment.  

2. **SPARQL Docstring Validation**  
   - **[PR 2: Docstring Format Check](https://github.com/scribe-org/Scribe-Data/pull/489)**  
     - Added the `check_docstring` function to validate SPARQL query docstrings against a predefined format.  
     - Integrated this validation into the query checking process for better automation.  

3. **Variable Order Based on JSON Metadata**  
   - **[PR 3: Validate and Sort Variables with Metadata](https://github.com/scribe-org/Scribe-Data/pull/503)**  
     - Introduced sorting based on `lexeme_forms.json`, prioritizing data type variables, shortest names, and lexicographical order.  
     - Enhanced the main validation function to include metadata-based checks.  

4. **Optional QID Order Validation**  
   - **[PR 4: Check Optional QID Order](https://github.com/scribe-org/Scribe-Data/pull/507)**  
     - Added `check_optional_qid_order` to validate the order of QIDs in optional statements.  
     - Refactored label decomposition logic into `decompose_label_features` for better code reuse.  
     - Ensures that optional clause QIDs align with metadata expectations while handling exceptions for duplicate entries.  

### Key Outcomes  
- **Improved Query Consistency**: Ensures alignment of variables and QIDs with metadata definitions.  
- **Enhanced Readability**: Validated and standardized docstrings improve code clarity.  
- **Robust Error Handling**: Identifies mismatches in variable and QID orders, providing clear error messages for resolution.  

### Usage  
- The validation workflow is integrated into the main query-checking process.  
- Errors and suggested corrections are logged for review.  
- Validation scripts can be run as part of CI/CD pipelines or during manual checks.
