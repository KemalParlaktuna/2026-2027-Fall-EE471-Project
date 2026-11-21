# EE471 Power System Analysis I — 2026–2027 Fall Term Project

Template repository for the EE471 term project: a general-purpose **Newton–Raphson load flow** tool with a user interface, written in **Python 3.11 or higher**.

## Project summary

Develop a load flow tool that:

- reads power system cases in the JSON format described in [`docs/EE471_Case_Data_Format.pdf`](docs/EE471_Case_Data_Format.pdf),
- lets the user load a case, **add new network components** and **edit existing components** in the loaded system,
- lets the user **select a solution method**, **configure its parameters** (e.g. tolerance, maximum iterations), run the analysis on the modified system and view the results.

A graphical drawing of the network is **not** required.

### Required outputs

Each analysis must report:

| Quantity | Unit |
|---|---|
| Voltage magnitude at each bus | per unit |
| Voltage angle at each bus | degrees |
| Total active power losses | MW |
| Total reactive power losses | MVAR |

## Repository layout

```
.
├── README.md            This file
├── docs/
│   ├── EE471_2026_Fall_Project_Definition.pdf   Official project definition
│   └── EE471_Case_Data_Format.pdf               Case data format (all tables, fields and element models)
└── cases/
    ├── json/            Case files in JSON format (input of your tool)
    │   ├── ieee14.json
    │   ├── ieee30.json
    │   ├── ieee57.json
    │   ├── ieee118.json
    │   └── ieee300.json
    └── excel/           The same cases as Excel workbooks (one sheet per table)
        ├── ieee14.xlsx
        ├── ieee30.xlsx
        ├── ieee57.xlsx
        ├── ieee118.xlsx
        └── ieee300.xlsx
```

The JSON and Excel files contain the same data. The JSON files are the input your tool must read; the Excel workbooks are provided for convenient inspection (each JSON table is a sheet with the same name and the same columns).

### Provided cases

| Case | Buses | Generators | Loads | Shunts | Lines | Transformers |
|---|---:|---:|---:|---:|---:|---:|
| IEEE 14  | 14  | 4  | 11  | 1  | 15  | 5   |
| IEEE 30  | 30  | 5  | 21  | 2  | 34  | 7   |
| IEEE 57  | 57  | 6  | 42  | 3  | 63  | 17  |
| IEEE 118 | 118 | 53 | 99  | 14 | 173 | 13  |
| IEEE 300 | 300 | 68 | 201 | 29 | 283 | 128 |

Generators above exclude the external grid (slack); every case has exactly one external grid.

Each case file also contains reference load flow results (`Result_*` tables). Use them to verify your implementation; your tool must compute these values itself.

## Milestones

| Milestone | Dates | Notes |
|---|---|---|
| First review | 23.11.2026 – 04.12.2026 | Initial Newton–Raphson implementation and a functional user interface. Not graded, but approval is required to continue. Additional requirements may be introduced after the review. |
| Final evaluation | 26.12.2026 – 27.12.2026 | Random groups analyze an assigned case with their own tools and present their technical findings. |

## Submission

- Keep your source code in a **GitHub repository** and share it with the teaching assistant.
- The final source code must be available in the shared repository.
- Include a standalone, runnable **Windows 11 compatible executable (`.exe`)** of the project in the repository.

## Generative AI policy

All students must read and accept the Generative AI Course Policy on ODTUClass ("EE471 2026 Fall GenAI Course Policy.pdf"); the project will not be graded otherwise. In short:

- You are fully responsible for the correctness and integrity of everything you submit; verify any AI-generated equations, algorithms and results.
- AI may support learning, debugging, documentation and language improvement, but must not produce complete solutions or programming work with minimal personal contribution.
- Include a brief **AI Usage Statement** (tool, purpose, extent of contribution) whenever GenAI is used.
- You must understand every line of your code and be able to modify and explain it during demonstrations.

Refer to the official [project definition](docs/EE471_2026_Fall_Project_Definition.pdf) and the course policy for the complete rules.
