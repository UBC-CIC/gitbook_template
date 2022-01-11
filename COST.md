---
description: AWS Service Pricing Estimate
---

Put a simplified version of cost analysis here. It is a bit tedious, but you'll have to manually copy/paste the data from excel into this table. Try to keep it short, with enough info to show how you got to the final price. It is much more convenient to edit this page on GitBook instead of inside a text editor.

- Assumptions
  - assumption 1
  - assumption ...
  - assumption n
- Facts
  - fact 1
  - fact ...
  - fact n

<table><thead><tr><th>Category</th><th data-type="number">Quantity</th><th>Units</th></tr></thead><tbody><tr><td></td><td></td><td></td></tr></tbody></table>

[Link to Full Pricing Spreadsheet](#)

Example from Census Explorer:

- Assumptions
  - 1000 User Sessions per Month
  - Each user performs 20 Queries
- Facts
  - Each time the site is accessed, it requests all of the T1 data.
  - Total number of rows in T1 data: 21333
  - Total number of rows in Census data: 753678 Number of FSAs: 1620

<table><thead><tr><th>Category</th><th data-type="number">Quantity</th><th>Units</th></tr></thead><tbody><tr><td>Number of FSAs   </td><td>1620</td><td>FSA</td></tr><tr><td>Assumed Number of Sessions Per Month </td><td>1000</td><td>Sessions</td></tr><tr><td>Assumed Number of Queries</td><td>20</td><td>Queries</td></tr><tr><td>Number of T1 Rows </td><td>21333</td><td>T1 Rows</td></tr><tr><td>Number of Census Rows</td><td>753678</td><td>Census Rows</td></tr><tr><td>Number of Similar Searches</td><td>10</td><td>Searches</td></tr><tr><td>Cost of Reading Entire T1 DB for 1 session</td><td>0.005866575</td><td>USD / Session</td></tr><tr><td>Cost for 20 Queries of Each Category</td><td>0.014776575</td><td>USD / 20 Queries</td></tr><tr><td>Cost for 20000 Queries Per Month</td><td>14.776575</td><td>USD / Month</td></tr><tr><td>Cost of a Similar Search</td><td>0.000141075</td><td>USD / Search</td></tr><tr><td>Cost for 10000 Searches </td><td>1.41075</td><td>USD / Month</td></tr><tr><td>Overall Cost</td><td>16.187325</td><td>USD / Month</td></tr></tbody></table>

[Link to Full Pricing Spreadsheet](https://docs.google.com/spreadsheets/d/14xJuSoBesNGClJyIhLuN8EDKVdYXVstGtgh5EPCUHKg/edit#gid=0)
