# MLH Software Engineering Code Sample

This README showcases my contributions to the scribe open-source project. Below are examples of pull requests I worked on, with links and summaries of each.

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
