# HackRx Bill Extraction API

FastAPI service that extracts line items from bill/invoice images, following the HackRx Datathon spec.

## Features

- `POST /extract-bill-data`
- Input: JSON with `document` (URL to image)
- Output:
  - `pagewise_line_items` with:
    - `page_no`
    - `page_type` (`Bill Detail | Final Bill | Pharmacy`)
    - `bill_items` (`item_name`, `item_amount`, `item_rate`, `item_quantity`)
  - `total_item_count`
- Simple heuristic OCR-based line item extraction
- Ready to plug in an LLM or more advanced OCR if desired

## Setup

```bash
git clone https://github.com/<your-username>/hackrx-bill-extraction.git
cd hackrx-bill-extraction

python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
