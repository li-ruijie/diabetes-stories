# Diabetes Stories Dataset

A processed dataset of oral history interviews from the [Diabetes Stories](https://diabetesmemories.com/) project, prepared for qualitative research and NLP experimentation.

## Contents

- [Background](#background)
- [Repository Structure](#repository-structure)
  - [Transcripts](#transcripts)
  - [Themes](#themes)
  - [Database](#database)
  - [Images](#images)
- [Data Formats](#data-formats)
- [Credits](#credits)
- [Copyright](#copyright)

## Background

This repository contains 102 interview transcripts from the Diabetes Stories project, converted from Word format to plain text with non-ASCII characters replaced by ASCII equivalents.

The interviews capture personal experiences with diabetes from three perspectives:
- People with diabetes (58 interviewees)
- Healthcare professionals (32 interviewees)
- Family members (25 interviewees)

Note: Some interviewees belong to multiple groups.

## Repository Structure

```
processed/
├── transcripts/
│   ├── txt/           # Plain-text transcripts (001.txt - 102.txt)
│   └── pdf/           # PDF versions
├── themes/
│   ├── topics-by-uid.json
│   └── uid-by-topics.json
├── database/
│   ├── interviews.xlsx
│   ├── profession.xlsx
│   ├── family.xlsx
│   ├── family-talked.xlsx
│   ├── marital-status.xlsx
│   └── paste-error.xlsx
└── images/            # Photographs of interviewees
```

### Transcripts

Plain-text interview transcripts numbered 001-102. Paragraphs are marked with numbers in parentheses: (1), (2), (3), etc. Interviewer questions appear as unnumbered text.

### Themes

Coded segments of the transcripts organised into 8 main topics:

1. Causes
2. Treatment
3. Financial costs
4. Medical staff
5. Living together; living alone
6. Responses from society
7. Effects on personality
8. Reflections

Each topic contains multiple subtopics with references to specific paragraphs in the transcripts.

**topics-by-uid.json** - Coded segments indexed by interviewee UID. Use this to find all topics discussed by a specific person.

**uid-by-topics.json** - Coded segments indexed by topic hierarchy. Use this to find all interviewees who discussed a specific topic.

### Database

Excel files containing structured metadata about interviewees:
- **interviews.xlsx** - Core interview metadata
- **profession.xlsx** - Occupational information
- **family.xlsx** - Family composition
- **family-talked.xlsx** - Family members mentioned in interviews
- **marital-status.xlsx** - Marital status data

### Images

Photographs of interviewees, named by UID and description (e.g., `001-01-ann-aged-9.jpg`).

## Data Formats

### Transcript Format

```
(1) First paragraph of the interview...

(2) Second paragraph continues here...

Interviewer question appears without numbering?

(3) Response to the question...
```

### Theme JSON Structure

**topics-by-uid.json**:
```json
{
  "uid": 1,
  "group": ["person with diabetes"],
  "topics": [
    {
      "index-topic": 2,
      "index-subtopic": 22,
      "topic": "Treatment",
      "subtopic": "Learning to inject.",
      "paragraph": [2]
    }
  ]
}
```

**uid-by-topics.json**:
```json
{
  "topic": "Treatment",
  "index-topic": 2,
  "subtopics": [
    {
      "index-subtopic": 22,
      "subtopic": "Learning to inject.",
      "coded-segment": [
        {
          "uid": 1,
          "group": ["person with diabetes"],
          "paragraph": [2]
        }
      ]
    }
  ]
}
```

## Credits

### Original Project

The Diabetes Stories oral history project was created at the Oxford Centre for Diabetes, Endocrinology and Metabolism (OCDEM), University of Oxford, with funding from the Wellcome Trust.

| Role | Name |
|------|------|
| Project Lead | David Matthews, Professor of Diabetic Medicine |
| Oral Historian / Interviewer | Helen Lloyd |
| Research Nurse | Sue Beatty |

### This Repository

This repository contains a reformatted version of the original data, with transcripts converted to plain text and theme codings structured as JSON for programmatic access.

## Copyright

All data belongs to the original authors of the Diabetes Stories project.
