# GEMINI.md - Project Overview

## Directory Overview

This directory is an Obsidian vault for managing course notes across multiple subjects. It is organized into a clean, hierarchical structure based on subject directories.

## Vault Organization

The vault is structured in a three-level hierarchy to ensure clear and scalable organization.

1.  **Root Index (`Main Index.md`)**: The single, top-level index file for the entire vault. It contains links to each subject's main index file.

2.  **Subject Index (`<Subject>/Index.md`)**: Each subject has its own directory (e.g., `DBMS/`, `Python/`). Inside each directory, an `Index.md` file serves as the main entry point for that subject, linking to different categories of notes (e.g., CT Notes, Semester Notes).

3.  **Content Index (`<Subject>/<Category>/Index.md`)**: Within a subject, notes are further organized into category directories (e.g., `2ND CT/`). An `Index.md` file within a category directory lists the actual notes.

## Key Directories & Files

*   `Main Index.md`: The primary index file for the entire vault.
*   `DBMS/`: Directory for all DBMS-related notes.
    *   `Index.md`: Main index for the DBMS subject.
    *   `2ND CT/`: Contains notes for the 2nd CT.
        *   `Index.md`: Lists all the 2nd CT notes for DBMS.
*   `Python/`: Directory for all Python-related notes.
    *   `Index.md`: Main index for the Python subject.
    *   `2ND CT/`: Contains notes for the 2nd CT.
        *   `Index.md`: Lists all the 2nd CT notes for Python.
*   `.obsidian/`: This directory contains the configuration files for the Obsidian vault.

## Answer Generation Workflow

To automate the creation of answers from a question file, the following conventions must be used:

- **Question Types**: Answers can be generated in two styles:
    - **SAQ**: Short Answer Questions (30-40 words).
    - **LAQ**: Long Answer Questions (approx. 60 words).

- **Trigger Methods**: To specify the desired answer type, use one of the following methods:
    1.  **File-based**: Ensure the very first line of the question file contains only the word `SAQ` or `LAQ`.
    2.  **Prompt-based**: Start your prompt with `ANS SAQ` or `ANS LAQ`, followed by the path to the question file.

## Usage

This directory is an Obsidian vault and is intended to be used with the [Obsidian](https://obsidian.md/) application. To use this vault:

1.  Download and install Obsidian.
2.  Open Obsidian and select "Open folder as vault".
3.  Navigate to this directory (`E:\Obsidian Files\DBMS 1ST SEM MCA`) and select it.

The vault is structured to be explored as a mind map. You can start with the `Main Index.md` file and navigate through the notes using the links.
