<div align="center">

# FreeTV iOS — Full Cycle QA Project

### SRS · STP · STD · STR · API Testing · Security Disclosure

![Status](https://img.shields.io/badge/Status-Completed-7FFF00?style=flat-square)
![Test Cases](https://img.shields.io/badge/Test%20Cases-123-blue?style=flat-square)
![Pass Rate](https://img.shields.io/badge/Pass%20Rate-80%25-7FFF00?style=flat-square)
![Bugs](https://img.shields.io/badge/Defects-9-red?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-iOS-lightgrey?style=flat-square)

</div>

---

## Project Overview

Full-cycle manual QA portfolio project for the **FreeTV iOS streaming application**
(v1.25.32, build 142) executed on iPhone 14 Pro running iOS 26.3.1.

The project covers the complete QA lifecycle from requirements analysis through
test planning, execution, defect reporting, and final test reporting —
following IEEE 830 and IEEE 829 standards.

---

## Test Coverage

| Suite | Total | Passed | Failed | Blocked | Pass Rate |
|-------|-------|--------|--------|---------|-----------|
| Functional | 71 | 67 | 4 | 0 | 94% |
| Non-Functional | 19 | 16 | 3 | 1 | 80% |
| API | 18 | 16 | 2 | 0 | 89% |
| Database | 14 | 0 | 0 | 14 | N/A |
| **TOTAL** | **123** | **99** | **9** | **15** | **80%** |
(excluding Blocked Database cases: 99/109 = **91% Pass Rate**

---

## Key Findings

### 🔴 High Severity
| ID | Title | Requirement |
|----|-------|-------------|
| FTV-5 | OTP remains valid for 60 minutes — industry standard is 10 minutes | FR-007, NFR-011 |
| FTV-8 | Multiple content endpoints accessible without authentication | NFR-010, FR-013 |

### 🟠 Medium Severity
| ID | Title | Requirement |
|----|-------|-------------|
| FTV-7 | Internal system architecture exposed in API error responses | NFR-010 |
| FTV-9 | Playback position not restored after app force-close | NFR-020 |

### 🟢 Low Severity
| ID | Title |
|----|-------|
| FTV-1 | Profile name truncation inconsistency |
| FTV-2 | Silent blocking — no error feedback for invalid phone number |
| FTV-3 | Special characters accepted without error feedback |
| FTV-4 | Search history cleared without confirmation prompt |
| FTV-6 | CATCH UP category label displayed in English |

> ⚠️ **Responsible Disclosure:** Security findings (FTV-7, FTV-8) have been
> reported to the FreeTV development team. Sensitive endpoint URLs and
> internal architecture details are withheld from public documentation.

---

## API Testing

Dual-method API testing approach using:
- **Fiddler** — Primary traffic capture and observation
- **Postman** — Secondary request replay and validation

Key API discoveries:
- OTP validation endpoint uses **PUT** method (not POST as originally designed)
- **4 simultaneous search requests** fire on each keystroke (search-as-you-type)
- Content endpoints return **200 OK without authentication** — security vulnerability
- Watchlist endpoint correctly enforces **device-level authentication**

---

## Tools & Technologies

| Tool | Purpose |
|------|---------|
| TestRail | Test case management — 123 cases across 4 suites |
| JIRA | Bug tracking — 9 defects filed |
| Fiddler | API traffic capture and analysis |
| Postman | API request replay and validation |
| iPhone 14 Pro | Primary test device |
| iOS 26.3.1 | Test environment |

---

## Documentation

| Document | Standard | Description |
|----------|----------|-------------|
| SRS | IEEE 830 | 36 Functional + 19 Non-Functional requirements |
| STP | IEEE 829 | Test planning and strategy |
| STD | IEEE 829 | 123 test cases with steps and evidence |
| STR | IEEE 829 | Full test results, RTM, defect summary |

---

## Project Structure

---

## About

**Tester:** Kirill Kovalevski

**Mentor:** Gal Matalon

**Institution:** המכללה לאוטומציה

**Duration:** April — June 2026

**Environment:** Production (iPhone 14 Pro, iOS 26.3.1, 4G)
