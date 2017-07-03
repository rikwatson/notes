# Manipulating Excel with Python

[`openpyxl`](https://openpyxl.readthedocs.io/en/default/) is the recommended module for reading and writing Excel files in Python.

```python
from openpyxl import load_workbook

wb = load_workbook(filename = 'excel-spreadsheet.xlsx')
```

```python
for sheet in wb.worksheets:
    print (sheet)
```

```python
for name in wb.get_sheet_names():

    print (name)
    if name.startswith("1"):
        process_summary(wb[name])
```

```python
def process_summary(sheet):
    print (sheet['A1'].value)
```
