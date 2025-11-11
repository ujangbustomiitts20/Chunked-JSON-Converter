# PDF to Chunked JSON Converter (English Version)

This script is designed to **extract text from PDF files** and split it into structured chunks using `Langchain RecursiveCharacterTextSplitter`.
The resulting output is stored in `.json` format, ready for use in NLP pipelines or RAG (Retrieval-Augmented Generation) systems.

## Features

* Reads all `.pdf` files from a specified folder
* Splits text into customizable chunk sizes
* Uses `RecursiveCharacterTextSplitter` from `Langchain`
* Saves results in ready-to-use `.json` format
* Automatically detects files that take too long to process

## Folder Structure

```
project_root/
├── pdf_chunker.py          # Main script
├── pdf_dokumen/            # Input folder containing PDF files
├── chunk_json/             # Output folder containing JSON results
```

## Configuration

You can adjust the following parameters inside the script:

```python
PDF_FOLDER = "./pdf_dokumen"             # Folder where PDF files are stored
CHUNK_OUTPUT_FOLDER = "./chunk_json"     # Output folder for generated chunks
MAX_ALLOWED_TIME_PER_FILE = 60           # Timeout per file (in seconds)
```

## How to Run

1. **Clone this repository or copy the script**
2. **Install the Python dependencies**

```bash
pip install pdfplumber langchain tqdm
```

3. **Place your PDF files into the `pdf_dokumen/` folder**
4. **Run the script**

```bash
python pdf_chunker.py
```

5. **Check the results in the `chunk_json/` folder**

Each `.pdf` file will produce a corresponding `.json` file containing a list of chunks, for example:

```json
[
  {
    "filename": "dokumen1.pdf",
    "chunk_id": "dokumen1.pdf_chunk_0",
    "text": "Content of the first text chunk..."
  },
  ...
]
```

## Notes

* Blank or non-extractable pages are automatically skipped.
* The output is suitable for preprocessing in document-based QA systems, LLM training, RAG pipelines, and more.

---

Created with ❤️ using `Langchain`, `pdfplumber`, and `tqdm`.
Feel free to fork and modify it as needed.
