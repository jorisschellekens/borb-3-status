
# ![borb logo](https://github.com/jorisschellekens/borb/raw/master/logo/borb_64.png) borb-3

[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![Public Method Documentation: 100%](https://img.shields.io/badge/public%20method%20documentation-100%25-green)]()
[![Tests: 1000+](https://img.shields.io/badge/tests-1000%2B-green)]()
[![Python Versions: 3.10, 3.11, 3.12](https://img.shields.io/badge/python-3.10%20|%203.11%20|%203.12-green)]()
[![Type Checking: 100%](https://img.shields.io/badge/type%20checking-100%25-green)]()
[![Downloads](https://pepy.tech/badge/borb)](https://pepy.tech/project/borb)
[![Monthly Downloads](https://pepy.tech/badge/borb/month)](https://pepy.tech/project/borb)

`borb` is a powerful and flexible Python library for creating and manipulating PDF files.

## ▶️ Progress

The table below represents a small selection of commits that highlight the progress made in developing the new borb library. These are only a handful of the contributions so far; the library is shaping up to be a powerful tool for working with PDFs.

At this stage, the core functionality of reading and writing PDF documents is nearly complete. Remaining features, such as HTML-to-PDF, Markdown-to-PDF, and OCR integration, are tangential to the core purpose and will follow once the foundational functionality is polished.

Currently, I am focused on reading PDF documents. My approach is pragmatic: I process a large corpus of PDF documents and analyze the library's behavior when something fails. This iterative approach helps identify edge cases, improve the code, and ensure robust support for a wide variety of PDF documents.

| Date       | Commit     | Description                                                                    |
| ---------- | ---------- | ------------------------------------------------------------------------------ |
| 10/04/2024 | `044340ea` | Initial commit                                                                 |
| 10/21/2024 | `09ae5a49` | Add DropDownList, CountryDropDownList, GenderDropDownList and associated tests |
| 10/27/2024 | `2daf9ced` | Add markdown files for code of conduct, license                                |
| 10/29/2024 | `83927fd3` | Re-do SmartArt                                                                 |
| 11/04/2024 | `1e1baf8a` | Start work on reading PDF documents                                            |
| 11/09/2024 | `b798b0af` | Writing PDF documents, reading PDF documents, adding reference type            |
| 11/28/2024 | `83b4dc8f` | Get rid of most typing issues                                                  |
| 11/30/2024 | `c4210ebf` | Trying out mermaid for documentation diagramming                               |
| 12/01/2024 | `d8138db6` | Apply black formatting                                                         |
| 12/01/2024 | `d8138db6` | Apply black formatting                                                         |
| 12/06/2024 | `0dc509fc` | Add TrueTypeFont                                                               |
| 12/08/2024 | `90b0ff67` | Add MarkdownParagraph                                                          |
| 12/11/2024 | `61dc1c42` | Add GoogleTrueTypeFont                                                         |
| 12/11/2024 | `12a9c3ed` | Add tests for TrueTypeFont                                                     |

## Text Extraction Test Results

The table below summarizes the latest test results for text extraction in `borb`. The first column represents the difference in character count (as a percentage) between the extracted text from a PDF and the expected "ground truth" character count. For instance, if a PDF is expected to have 200 characters but the extraction yields 180 characters, this represents a 10% difference and falls into the "10" bucket. The second column shows the fraction of documents that fall into each bucket.

| Difference (%) | Fraction of Documents |
|----------------|-----------------------|
| 0              | 82                    |
| 10             | 2                     |
| 20             | 2                     |
| 30             | 1                     |
| 40             | 0                     |
| 50             | 1                     |
| 60             | 1                     |
| 70             | 0                     |
| 80             | 3                     |
| 90             | 2                     |
| 100            | 4                     |

### Notes

While the results are not yet ideal, they represent an early stage of development. Future improvements will include:

- Implementing additional text-showing operators.
- Supporting composite fonts.
- Debugging existing functionality for better accuracy and reliability.


## 📖 Overview

`borb` provides a pure Python solution for PDF document management, allowing users to read, write, and manipulate PDFs. It models PDF files in a JSON-like structure, using nested lists, dictionaries, and primitives (numbers, strings, booleans, etc.). Created and maintained as a solo project, `borb` prioritizes common PDF use cases for practical and straightforward usage.

## ✨ Features

Explore `borb`’s capabilities in the [examples repository](https://github.com/jorisschellekens/borb-examples) for practical, real-world applications, including:

- PDF Metadata Management (reading, editing)
- Text and Image Extraction
- Adding Annotations (notes, links)
- Content Manipulation (adding text, images, tables, lists)
- Page Layout Management with `PageLayout`

…and much more!

## 🚀 Installation

Install `borb` directly via `pip`:

```bash
pip install borb
```

To ensure you have the latest version, consider the following commands:

```bash
pip uninstall borb
pip install --no-cache borb
```

## 👋 Getting Started: Hello World

Create your first PDF in just a few lines of code with `borb`:

```python
from pathlib import Path
from borb.pdf import Document, Page, PageLayout, SingleColumnLayout, Paragraph, PDF

# Create an empty Document
d: Document = Document()

# Create an empty Page
p: Page = Page()
d.append_page(p)

# Create a PageLayout
l: PageLayout = SingleColumnLayout(p)

# Add a Paragraph
l.append_layout_element(Paragraph('Hello World!'))

# Write the PDF
PDF.write(what=d, where_to="assets/output.pdf")

```

## 🛠 License

`borb` is dual-licensed under AGPL and a commercial license. 

The AGPL (Affero General Public License) is an open-source license, but commercial use cases require a paid license, especially if you intend to:

- Offer paid PDF services (e.g., PDF generation in cloud applications)
- Use `borb` in closed-source projects
- Distribute `borb` in any closed-source product

For more information, [contact our sales team](https://borbpdf.com/).

## 🙏 Acknowledgements

Special thanks to:

- Aleksander Banasik
- Benoît Lagae
- Michael Klink

Your contributions and guidance have been invaluable to `borb`'s development.
