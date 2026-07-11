# Workbook Structure
Version: 1.0

---

# 1. Purpose

This document defines the physical structure of the MAS workbook.

The workbook is designed following three principles:

- Separation of concerns
- Easy maintenance
- GitHub friendly

---

# 2. Worksheet Layout

| No | Worksheet | Purpose |
|----|-----------|---------|
|01|HOME|Navigation|
|02|TEACHER|Teacher Workspace|
|03|DEPARTMENT|Department Dashboard|
|04|REPORTS|Reports|
|05|MASTER_DATA|Master Tables|
|06|ASSESSMENT|Assessment Tables|
|07|SCORES|Score Tables|
|08|SYSTEM|System Configuration|
|09|CACHE|Performance Cache|
|10|LOGS|Audit Logs|
|11|LISTS|Validation Lists|

---

# 3. HOME

Purpose

Landing page

Contains

- Navigation buttons
- Current Semester
- Current Academic Year
- Workbook Version
- Last Update
- Developer Mode

No business data stored here.

---

# 4. TEACHER

Teacher daily workspace.

Contains

- Selected Class
- Selected Assessment
- Student List
- Score Input
- Save Button
- Calculate Button

No formulas except display formulas.

---

# 5. DEPARTMENT

Contains

Dashboard only.

Examples

Average

Top Students

Missing Scores

Class Ranking

Level Distribution

Charts

Pivot Tables

No editing.

---

# 6. REPORTS

Contains

Student Report

Class Report

Semester Report

Export Area

No data entry.

---

# 7. MASTER_DATA

Contains Excel Tables

tblStudents

tblTeachers

tblClasses

tblPrograms

tblAcademicYears

No calculations.

---

# 8. ASSESSMENT

Contains

tblAssessmentPlans

tblAssessmentEvents

tblIndicators

tblRubrics

tblAssessmentStructure

Only Office Scripts modify this sheet.

---

# 9. SCORES

Contains

tblRawScores

tblOfficialScores

tblSemesterScores

Teachers never edit these tables directly.

---

# 10. SYSTEM

Contains

tblSettings

tblFeatureFlags

tblPermissions

tblThemes

Read by Office Scripts.

---

# 11. CACHE

Contains

tblDashboardCache

tblStatisticsCache

tblRankingCache

Automatically refreshed.

Never manually edited.

---

# 12. LOGS

Contains

tblAuditLogs

tblErrors

tblNotifications

Append-only.

---

# 13. LISTS

Contains

Gender

Semester

Program

Assessment Status

Role

Permission

Indicator

Category

Academic Year

No business data.

---

# 14. Protection Policy

HOME

Unlocked

TEACHER

Partially unlocked

DEPARTMENT

Protected

REPORTS

Protected

MASTER_DATA

Developer only

ASSESSMENT

Developer only

SCORES

Developer only

SYSTEM

Developer only

CACHE

Hidden

LOGS

Hidden

LISTS

Hidden

---

# 15. Hidden Sheets

When Developer Mode = FALSE

Hidden

SYSTEM

CACHE

LOGS

LISTS

MASTER_DATA

ASSESSMENT

SCORES

When Developer Mode = TRUE

All worksheets visible.

---

# 16. Color Convention

Blue

Input

Green

Calculated

Gray

Locked

Red

Errors

Yellow

Warning

---

# 17. Table Convention

Every table starts in Cell A1.

Every table uses Excel Structured References.

No merged cells.

No blank columns.

No blank rows.

---

# 18. Formula Convention

Never reference

A1:B20

Always reference

tblStudents[StudentID]

Named Tables only.

---

# 19. Office Script Convention

Office Scripts never modify dashboard cells.

Office Scripts modify only Excel Tables.

Dashboard refreshes automatically from tables.

---

# 20. Versioning

Workbook Version stored in

tblSettings

Version

Build

ReleaseDate

Developer
