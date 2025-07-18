I have a Google‑Sheets workbook named “SY25‑26_JULY_12_*THRIVE*Inclusive_Workbook”.
[
](https://docs.google.com/spreadsheets/d/146CRqCG8d0QQjGRo1HzyEuZ3rI6XO0jYjdzmDqu4wmM/edit?gid=976022590#gid=976022590)
Tabs:
  • GrdK_Math_Unit_Planner … Gr6_Math_Unit_Planner
  • Dashboard tab: IC_Map_Dashboard_Math (imports each grade via QUERY(IMPORTRANGE))

Problem:
  Manual edits caused #REF! spill errors and wiped dropdowns in Columns G & H.

Deliverables (7 tasks):
1. Restore seven QUERY(IMPORTRANGE) arrays in IC_Map_Dashboard_Math (Grades K‑6).
   – one blank row between each; wrap each in IFERROR.
   – range A12:K; select clause ends with Col11.
2. Protect A2:K1000 (dashboard) with “warning on edit”.
3. Re‑create named ranges on hidden sheet Tab List:
   – Adaptations_List = A1:A11 (11 items)
   – Toolbox_List = B1:B11 (11 items)
   – Generalise_List = C1:C3 (3 items)
4. Re‑apply data validation to every planner tab:
   – Column G rows 9‑200 → multi‑select from Adaptations_List
   – Column H rows 9‑200 → single‑select from Toolbox_List (warning on invalid)
   – Column I rows 9‑200 → single‑select from Generalise_List
5. Re‑install conditional‑format: range D12:K200
   formula =AND($A12<>"", OR($D12<>TRUE,$G12="", $I12="", $J12=""))
6. Add custom menu “THRIVE Tools → Validate Planner”:
   checks named ranges & DV; alerts if missing.
7. (Optional) nightly trigger that clears stray text like "2"() in dashboard but leaves formulas.

Acceptance:
  • Fill Unit‑1 row in any grade → planner row white, dashboard cell green (<1 min).
  • “Validate Planner” reports “All good”.
  • No #REF! in dashboard.

Shared copy of the workbook (editor access): <PASTE‑DRIVE‑LINK‑HERE>
