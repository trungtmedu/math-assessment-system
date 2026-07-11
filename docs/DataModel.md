# Data Model
Version: 1.0

---

# 1. Design Principles

The Math Assessment System (MAS) stores all information using Excel Tables.

Rules:

- Every record has one Primary Key.
- Every table has one responsibility.
- No duplicated business data.
- Calculated values are separated from raw data.
- Office Scripts never access individual cells directly.

---

# 2. Data Domains

The workbook is divided into five logical domains.

Master Data

Assessment

Scores

System

Logs

---

# 3. Master Data

## tblStudents

| Field | Type | Required |
|-------|------|----------|
| StudentID | Text | Yes |
| StudentCode | Text | Yes |
| FullName | Text | Yes |
| Gender | Text | Yes |
| DateOfBirth | Date | Yes |
| ClassID | Text | Yes |
| Status | Text | Yes |
| CreatedAt | DateTime | Auto |
| UpdatedAt | DateTime | Auto |

Primary Key

StudentID

---

## tblTeachers

TeacherID

TeacherCode

FullName

Email

Department

Status

---

## tblClasses

ClassID

ClassName

AcademicYearID

Grade

ProgramID

TeacherID

Status

---

## tblPrograms

ProgramID

ProgramName

---

## tblAcademicYears

AcademicYearID

AcademicYearName

StartDate

EndDate

Status

---

# 4. Assessment

## tblAssessmentPlans

PlanID

Semester

OfficialScore

Category

Week

Weight

---

## tblAssessmentEvents

EventID

PlanID

EventName

ClassID

OpenDate

CloseDate

Status

---

## tblIndicators

IndicatorID

EventID

IndicatorName

Weight

---

## tblRubrics

RubricID

IndicatorID

Level

Description

Score

---

# 5. Scores

## tblRawScores

ScoreID

StudentID

EventID

IndicatorID

Score

Remark

CreatedAt

---

## tblOfficialScores

StudentID

Semester

TX1

TX2

TX3

TX4

GK

CK

---

## tblSemesterScores

StudentID

Semester

Average

Ranking

Level

---

# 6. System

## tblSettings

Key

Value

---

## tblFeatureFlags

Feature

Enabled

---

## tblPermissions

Role

Permission

---

# 7. Logs

## tblAuditLogs

Time

User

Module

Action

RecordID

OldValue

NewValue

---

## tblErrors

Time

Module

Message

Severity

Resolved

---

## tblNotifications

Time

Level

Message

Status

---

# 8. Relationships

AcademicYear

↓

Classes

↓

Students

↓

Assessment Plans

↓

Assessment Events

↓

Raw Scores

↓

Official Scores

↓

Semester Scores

---

# 9. Naming Convention

StudentID

...

TeacherID

TC-01

ClassID

CL-10.1.3

Assessment Event

AE-HK1-01

Score

SC-000001

---

# 10. Metadata

Every business table contains:

CreatedAt

CreatedBy

UpdatedAt

UpdatedBy

RecordStatus

---

# 11. Future Extensions

Attendance

Behavior

Portfolio

AI Insights

Parent Reports

These modules can be added without changing the current database structure.
