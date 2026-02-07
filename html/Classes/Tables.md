
## What is an HTML Table?

An **HTML table** is a structured arrangement of data organized into **rows** (horizontal lines of cells) and **columns** (vertical lines of cells), where the smallest unit is a **cell** (a single box holding data).

This format allows displaying information like lists, schedules, or summaries in a grid-like visual structure, making complex data readable—think of it like a spreadsheet where data is neatly boxed for clarity.

Rows run horizontally across the table, while columns run vertically; for example, in a table of student data, one row might hold "ID: 1, Name: John, Gender: Male," spanning three cells and columns.

## Essential HTML Table Tags

Every table starts with the `<table>` tag, which creates the overall container.

- **`<tr>` (Table Row)**: Defines a single row inside the table; all rows are built using this tag.
- **`<td>` (Table Data)**: Creates a cell within a row to hold actual content like text or numbers; multiple `<td>` tags per `<tr>` define columns.
- **`<th>` (Table Header)**: Similar to `<td>` but for headings, typically bolder and centered; used for column labels like "Name" or "Salary."

To visualize, a basic table with one row and three cells looks like this empty structure first (add `border="1"` to `<table>` for visibility):
```html
<table border="1">
  <tr>
    <td>Cell 1</td>
    <td>Cell 2</td>
    <td>Cell 3</td>
  </tr>
</table>
```


These tags build the foundation—`<tr>` for rows, `<td>` or `<th>` for cells—allowing uniform grids before advanced modifications.

## Table Structure: thead, tbody, tfoot

Tables are semantically divided into three sections for better organization and accessibility: **`<thead>`** (headers), **`<tbody>`** (body content), and **`<tfoot>`** (footer, like summaries).

- **`<thead>`**: Contains headings using `<th>` tags; all column headers go here, e.g., "Student ID, Name, Gender." This builds on basic `<th>` by grouping them logically at the top.
- **`<tbody>`**: Holds the main data rows using `<tr>` and `<td>`; actual content like student records goes here.
- **`<tfoot>`**: For summaries or totals at the bottom, e.g., "Total Expense: 4600"; uses `<tr>` and `<td>`, often with spans for merged cells.

> **💡 Key Insight:** Use this structure because `<thead>` keeps headers fixed visually in large tables, `<tbody>` for scrollable data, and `<tfoot>` for calculations—mirroring real-world reports.

A complete structured table skeleton:
```html
<table border="1">
  <thead>
    <tr><th>Header 1</th><th>Header 2</th></tr>
  </thead>
  <tbody>
    <tr><td>Data 1</td><td>Data 2</td></tr>
  </tbody>
  <tfoot>
    <tr><td>Total</td><td>Sum</td></tr>
  </tfoot>
</table>
```


This hierarchy matters for screen readers and styling, connecting basic tags to professional layouts.

## Merging Cells: rowspan and colspan Attributes

Cells can merge across multiple rows or columns using **rowspan** (vertical merge) and **colspan** (horizontal merge), preventing repetition and matching observed UI layouts.

- **rowspan="n"**: Extends a `<td>` or `<th>` across $$n$$ rows downward; count how many rows the cell visually spans in the target table.
- **colspan="n"**: Extends across $$n$$ columns rightward; ideal for headers or totals spanning multiple columns.

**Why it matters:** Without spans, tables repeat data unnecessarily; spans create irregular, realistic grids like merged schedule blocks.

> **⚠️ Warning:** When spanning, skip creating new cells in overlapped positions—do not repeat data or add empty `<td>` where the span covers; count spans precisely by observing the UI first.

Example of colspan=3 for a total cell:
```html
<tfoot>
  <tr>
    <td colspan="3">Total Expense: 4600</td>
  </tr>
</tfoot>
```


These attributes build directly on `<td>`/`<th>`, enabling complex designs from simple observations.

## Step-by-Step: Creating a Basic Employee Table

Observe the UI: 4 columns (Number, Full Name, Position, Salary), 4 data rows in `<tbody>`, no spans.

1. Start with `<table border="1">`, add `<thead>` with 4 `<th>`: "Number, Full Name, Position, Salary."
2. In `<tbody>`, create 4 `<tr>` each with 4 `<td>`: e.g., first row "1, Bill Gates, Founder, 1000."
3. No `<tfoot>` needed.

This teaches counting columns first, placing headers in `<thead>`, data in `<tbody>`—a foundation for all examples.

## Advanced Example: Founder Table with rowspan and colspan

UI shows: Founders list with "Company Founder" spanning 4 rows (rowspan=4), "Total Expense" colspan=3 in footer.

1. `<thead>`: 4 `<th>` – "Number, Name, Founder, Salary."
2. `<tbody>` first row: `<td>1</td><td>Bill Gates</td><td>Microsoft</td><td>1000</td>`; last `<td>` in row 1: `<td rowspan="4">Company Founder</td>` (spans down).
3. Subsequent rows skip the spanned column: e.g., row 2: `<td>2</td><td>Steve Jobs</td><td>Apple</td><td>1200</td>`.
4. `<tfoot>`: `<tr><td colspan="3">Total Expense</td><td>4600</td></tr>`.

**Connection:** Rowspan avoids repeating "Company Founder"; observe spans before coding to match UI exactly.

## Schedule/Expense Table: Multi-Span Practice

Target UI: 7 columns (Country, State, City, Street,?, Gender, Amount?), irregular spans like "1" rowspan=8, "Kerala" rowspan=4.

1. Count: `<thead>` 7 `<th>` (Country, State, City, Street, Male/Female, Ideal?, Amount?).
2. `<tbody>`: First row `<td rowspan="8">1</td><td rowspan="4">Kerala</td><td>1</td><td>New Street</td><td>500</td><td>600</td><td>6</td>`.
3. Skip spanned cells in later rows: e.g., row 2 starts after "1" and "Kerala," adding unique data like "300."
4. Continue for "Maharashtra rowspan=4," "Mumbai rowspan=2," etc., verifying no overlaps.

**Key process:** Observe each cell's span count visually (e.g., "1" covers 8 rows vertically), apply rowspan/colspan, fill only new data.

> **ℹ️ Note:** Add `border="1"` early to preview structure; adjust data without restructuring spans.

## Student Table: Headers and Simple Rows

Simple case: `<thead>` with "Student ID, Name, Gender, Age"; `<tbody>` 3 rows of 4 `<td>` each, no spans.

1. Use `<thead><tr>` with 4 `<th>`.
2. `<tbody>`: Copy `<tr><td>...</td>...</tr>` pattern for each row.

This reinforces `<thead>` for fixed headers, scaling to larger tables.

## Complex Multi-Row Span Table (Homework Example)

Homework UI: 3 columns, spans like "Monday" rowspan=2, "Seminar" rowspan=3, "Schedule" rowspan=2.

1. Identify rows/columns, place spans in first occurrence: e.g., "Monday <td rowspan="2">".
2. Skip spanned positions in subsequent rows.
3. Fill remaining `<td>` with data like "Topic."

**Significance:** Practice replicates real tasks—count spans accurately to avoid gaps or overlaps.

## Best Practices and Observation Workflow

Always start by observing the target table:
- Count total rows (excluding header), columns from widest row.
- Note headings for `<thead>`, data for `<tbody>`, totals for `<tfoot>`.
- Identify spans: Vertical (rowspan by row count), horizontal (colspan by column count).
- Code skeleton first (`<table><thead>...</thead><tbody>...</tbody><tfoot>...</tfoot></table>`), then fill data.

> **⚠️ Common Misconception:** Do not recreate spanned cells or repeat data—spans cover them automatically; verify with `border="1"` preview.

This workflow turns any visual table into code, building confidence through repetition.

Practice more by searching "estimate tables" on Google Images or creating timetables—focus on span counting for vertical/horizontal merges.
