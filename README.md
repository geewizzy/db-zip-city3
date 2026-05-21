# 📍 db_zip-city3 Viewer

An interactive, fast, and mobile-friendly database of US Zip Codes, Cities, Counties, and States.

**Live Demo**: [https://yourusername.github.io/zip-city-viewer/]([https://yourusername.github.io/zip-city](https://github.com/geewizzy/db-zip-city3/)-viewer/)  
*(Replace with your actual GitHub Pages link after setup)*

---

## ✨ Features

- ⚡ **Fast search** — type city, county, state, or zip (supports multiple words)
- 🗺️ **One-click Google Maps** link for every location
- 📱 **Fully responsive** — works great on phones and tablets
- 📊 **Pagination** + real-time stats
- 📥 **Export** filtered results as CSV or JSON
- 🎨 Clean, modern design with sticky headers

---

## How to Use

1. Open the [live viewer]([https://yourusername.github.io/zip-city](https://github.com/geewizzy/db-zip-city3/)-viewer/)
2. Type in the search box (e.g. `Austin Texas` or `90210` or `Los Angeles county`)
3. Click any **🗺️ Open in Google Maps** link
4. Use **Export** buttons to download your filtered results

---

## Files in this Repository

- `index.html` → The main interactive viewer (single file app)
- `db_zip-city3.csv` → The database (converted from pipe `|` to comma `,` format)
- `README.md` → This file

---

## Setup / Troubleshooting

### If the table says "File not found" or stays on "Loading..."

Most common fixes:

1. Make sure **`db_zip-city3.csv`** and **`index.html`** are in the **root** of the repository.
2. The file must be named exactly **`db_zip-city3.csv`** (not .txt).
3. Wait 30–60 seconds after uploading and refresh the page.

### How to Convert .txt to .csv (if needed)

Download the conversion script or run this in Command Prompt / Terminal (in the same folder):

```python
import csv
import os

input_file = 'db_zip-city3.txt'
output_file = 'db_zip-city3.csv'

try:
    with open(input_file, 'r', encoding='utf-8') as infile, \
         open(output_file, 'w', newline='', encoding='utf-8') as outfile:
        
        reader = csv.reader(infile, delimiter='|')
        writer = csv.writer(outfile)
        row_count = 0
        for row in reader:
            writer.writerow([field.strip() for field in row])
            row_count += 1
    print(f"✅ Converted {row_count} rows successfully!")
except Exception as e:
    print(f"❌ Error: {e}")

input("\nPress Enter to close...")
