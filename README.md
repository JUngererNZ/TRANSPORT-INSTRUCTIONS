# Transport Instruction JSON Mapper

A small automation project for turning manually prepared load-plan data into repeatable transport instruction Excel files.

This project uses a JSON file as the editable input layer between a packing list workbook and a transport instruction workbook, so repeated copy-paste into multiple transport instruction files can be replaced with a structured, script-driven process [1][2]. The goal is to map trailer-specific load data from the packing list into the correct cells of each transport instruction workbook, especially the fixed header cells and the `LOADING / CARGO DETAILS` section in `F43:F50` [1][2].

## Problem

The transport instruction workbook is filled in manually, even when the source data already exists in the packing list workbook [1][2]. In cases where there are many transport instructions for one shipment, such as 11 copies, the process becomes repetitive and error-prone because the same structure is recreated by copy-paste for each trailer load [2].

## Solution

The project introduces a JSON template that stores the transport instruction content in the same order as the Excel sheet, making the file easier to read, edit, and validate against the workbook layout . A Python script reads that JSON file, duplicates the transport instruction template, writes fixed values into known cells like `A18`, `F18`, `F20`, `A21`, `A25`, and `A46`, and then fills the cargo area in `F43:F50` from the `loading_cargo_details.rows` array [2].

## Files

| File | Purpose |
|------|---------|
| `Copy-of-Packing-list-6P300139-loadplan-excl-bucket.xlsx` | Source workbook containing load-plan splits by trailer, item descriptions, dimensions, and weights [1] |
| `2604DSI2801-TRANSPORT-INSTRUCTION-BA3195-CAT-6030-NATRANS-LOAD1-2.xlsx` | Base transport instruction workbook used as the output template [2] |
| `transport_instruction_excel_ordered_template.json` | Editable JSON template with 11 instruction blocks ordered to match the Excel sheet  |
| `fill_transport_instructions_from_excel_ordered_json.py` | Script that reads the JSON file and generates the transport instruction workbooks  |

## JSON structure

Each instruction block contains two main sections :

- `sheet_fields`: fixed-value cells written directly into known Excel addresses.
- `loading_cargo_details`: repeating cargo rows for the `F43:F50` area.

Example structure:

```json
{
  "copy_no": 10,
  "sheet_fields": {
    "A18_transporter": "ORIENTO",
    "F18_transporter_contact_person": "DANIEL",
    "F20_client": "BARTRAC EQUIPMENT",
    "A21_fml_freight_solutions_ref": "2604DSI2801",
    "A25_deliver_to": "MUTANDA MINING SARL, MUTANDA MINING SARL SIEGE SOCIAL, PROVINCE DE LUALABA,",
    "A46_ref_nr": "BA3195"
  },
  "loading_cargo_details": {
    "range": "F43:F50",
    "rows": [
      {
        "source_load_nr": 11,
        "description": "LINK1",
        "measurement": "",
        "gross_weight_kg": ""
      }
    ]
  }
}
```

## Workflow

1. Review the packing list workbook and identify the items grouped under each trailer or load number [1].
2. Fill the JSON file with one instruction block per transport instruction workbook .
3. Keep the fixed sheet values in `sheet_fields` and the repeating cargo lines in `loading_cargo_details.rows` .
4. Run the Python script to generate one Excel output file per `copy_no` .

## Script behavior

The Python script performs the following steps :

- Opens the JSON template.
- Loops through all `instructions` entries.
- Copies the transport instruction template workbook for each block.
- Writes fixed sheet values by extracting the cell reference from keys such as `A18_transporter`.
- Expands the `F43:F50` range vertically and fills one row per cargo entry.
- Saves each output workbook into a generated output folder.

## Run

Place these files in the same working folder:

- `transport_instruction_excel_ordered_template.json` 
- `fill_transport_instructions_from_excel_ordered_json.py` 
- `2604DSI2801-TRANSPORT-INSTRUCTION-BA3195-CAT-6030-NATRANS-LOAD1-2.xlsx` [2]

Then run:

```bash
python fill_transport_instructions_from_excel_ordered_json.py
```

The script will create one output workbook per instruction block in a `generated_transport_instructions` folder .

## Current scope

The current implementation is designed around fixed header cells and the `F43:F50` cargo block already identified in the workbook [2]. It is a strong starting point for replacing manual copy-paste, but it can be extended later to map measurements and gross weights into separate neighboring cells if the worksheet layout requires more granular writing than a single combined line per cargo entry [2].

## Next improvements

Possible next steps include:

- Add separate target mappings for description, measurement, and gross weight if they belong in different cells [2].
- Parse the packing list workbook directly to pre-build the JSON automatically for each load number [1].
- Support `.xlsm` output while preserving macros if the transport instruction template needs to remain macro-enabled [2].
- Add validation to warn when there are more cargo lines than the `F43:F50` range can hold .

## Why this format works

Using JSON as the editable layer makes the process easier to maintain than repeated workbook edits because the data entry is separated from the Excel formatting and layout . Ordering the JSON fields to match the Excel sheet makes the template more human-friendly for transport staff who need to cross-check values against the workbook during setup and testing .