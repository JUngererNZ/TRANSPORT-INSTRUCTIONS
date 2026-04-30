<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# show me the json file

Here is the JSON file content:

```json
{
  "template_info": {
    "packing_list_file": "Copy-of-Packing-list-6P300139-loadplan-excl-bucket.xlsx",
    "transport_instruction_file": "2604DSI2801-TRANSPORT-INSTRUCTION-BA3195-CAT-6030-NATRANS-LOAD1-2.xlsx",
    "notes": [
      "One JSON object in instructions represents one transport instruction workbook copy / one trailer.",
      "Your script can ask how many copies to make, then duplicate the transport template and apply each instructions entry.",
      "The cell references below are placeholders until you confirm the exact destination cells in the TI template."
    ]
  },
  "mapping": {
    "transport_instruction_cells": {
      "trailer_name": "",
      "item_1_description": "",
      "item_1_dimensions": "",
      "item_1_gross_weight": "",
      "item_2_description": "",
      "item_2_dimensions": "",
      "item_2_gross_weight": "",
      "item_3_description": "",
      "item_3_dimensions": "",
      "item_3_gross_weight": ""
    },
    "packing_list_fields": {
      "description": "Description",
      "dimensions_mm": "Dimensions in mm (L x W x H)",
      "gross_weight_kg": "Gross Weight kg",
      "load_no": "LOAD NR"
    }
  },
  "instructions": [
    {
      "copy_no": 1,
      "trailer_name": "load8 - tri-axle",
      "line_items": [
        {
          "description": "Riser AR - FOBS CAB?",
          "dimensions_mm": "3640 x 1900 x 3160",
          "gross_weight_kg": 5700
        },
        {
          "description": "Cooler AR HYD",
          "dimensions_mm": "3900 x 1550 x 2900",
          "gross_weight_kg": 5400
        },
        {
          "description": "CABIN",
          "dimensions_mm": "3760 x 2760 x 3000",
          "gross_weight_kg": 4294
        }
      ]
    }
  ],
  "possible_transport_instruction_label_cells": [
    {
      "cell": "A19",
      "value": "DATE OF LOADING"
    },
    {
      "cell": "F19",
      "value": "LOADING TIME"
    },
    {
      "cell": "H19",
      "value": "TBC - VEHICLES SHOULD BE IN DURBAN AT LEAST 1 DAY PRIOR TO VESSEL ARRIVAL"
    },
    {
      "cell": "A20",
      "value": "VEHICLE REGISTRATION"
    },
    {
      "cell": "A26",
      "value": "LOADING FROM"
    },
    {
      "cell": "A27",
      "value": "LOADING LOCATION"
    },
    {
      "cell": "A31",
      "value": "Vehicle Requirements"
    },
    {
      "cell": "A41",
      "value": "LOADING /CARGO DETAILS"
    },
    {
      "cell": "F43",
      "value": "TRACK FRAME with TRACK 1 (RH) - 7.7 X 1.87 X 1.950M = 40300KGS"
    },
    {
      "cell": "A51",
      "value": "FOR CROSS BORDER LOADS ONLY"
    },
    {
      "cell": "A56",
      "value": "ALL CARGO CARRIED ON BEHALF OF FML FREIGHT SOLUTIONS (PTY) LTD MUST BE COVERED BY YOUR GIT COVERAGE. PHOTOGRAPHS ARE TO BE TAKEN OF ALL EQUIPMENT ONCE LOADED ONTO THE VEHCILES AND PRIOR TO DISPATCH FROM THE LOADING FACILITY (PORT OR ANY OTHER). PLEASE ENSURE THAT THERE ARE PHOTOGRPAHS OF THE HORSE WITH REG & TRAILIER REG. AND THAT THE CARGO LOADED IS TO BE LASHED TO THE VEHICLES WITH NO LESS THAN 4 - 7 CHAINS & 7 - 10 RATCHETS. RUBBER PROTECTION TO BE PLACED ON ALL METAL SURFACES WHERE TIEDOWNS / CHAINS WILL AND CAN DAMAGE METAL / PAINT. PLEASE ENSURE TARPS ARE PROVIDED FOR TRI-AXLE LOADS. WHERE APPLICABLE, THE TRANSPORTER HAS TO ENSURE PORT ACCESS FOR ALL TRUCKS AND DRIVERS AND HAVE A LOAD MASTER PRESENT TO LOAD ITEMS ALLOCATED AS PER LOAD PLAN / INSTRUCTION AT HIS OWN COST."
    },
    {
      "cell": "A58",
      "value": "PLEASE NOTE: ABNORMAL VECHILES CARRYING ABNORMAL CARGO ARE TO TRAVEL WITH ESCORTS AS PER EACH COUNTRIES REGULATIONS. THEY ARE TO ADHERE TO THE SPEED LIMIT AND ALLOWED FOR SAFE FOLLOWING DISTANCE BETWEEN EACH VEHICLE. UPON ENTRY INTO THE DESTINATION COUNTRY ALL VEHICLES ARE TO HAVE ESCORTS AT ALL TIMES AND MAY NOT TRAVEL ARTER DUSK."
    },
    {
      "cell": "A59",
      "value": "***PLEASE ENSURE THIS CARGO IS LOADED ON THE CORRECT TRAILERS FOR TRANSPORTATION IN ACCORDENCE WITH THE ROAD TRAFFIC INSPECTORATE GUIDELINES REFERENCE TO MASS & DIMENSIONS. ALL LOADS UNDERTAKEN ARE TO HAVE THE REQUIRED PERMITS FOR EACH PROVICE & TRANSITING COUNTRIES. COPIES OF PERMITS ARE TO BE PROVIDED TO FML FREIGHT SOLUTIONS (PTY) LTD PRIOR TO LOADING & ARE TO FORM PART OF YOUR PROOF OF DELIVER DOCUMENTATION. SHOULD PERMITS NOT BE MADE AVAILABLE PRIOR TO LOADING, FML FREIGHT SOLUTIONS (PTY) LTD RESERVES THE RIGHT TO WITHDRAW THE LOAD FROM THE NOMINATED HAULIER UNLESS CIRCUMSTANCES PREVAIL WHICH PROHIBIT PERMITS BEING ISSUED PROIR TO ARRIVAL AT DESIGNATED POINT***"
    },
    {
      "cell": "A62",
      "value": "2. The transporter represents and warrants that it has significant knowledge, capability and experience to render the services it has been contracted to render (\"the Services\") and it has and shall continue to have all the necessary labour, vehicles, machinery, equipment, licenses, permits, permissions, accreditations and adequate insurances in place to render the Services. It indemnifies FML Freighjt Solutions (PTY) Ltd against any claims, liabilities, costs, losses, damages whatsoever and how soever arising as a result of any breach of this warranty."
    }
  ]
}
```

I can also turn this into a cleaner editable template with 11 instruction blocks pre-made.

