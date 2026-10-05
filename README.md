# 🏢 OfficeRepairTracker

A full-cycle workflow automation and IT asset repair tracking system designed to streamline the lifecycle of organizational office equipment repairs — from initial IT inspection and vendor dispatch to quality testing and department reassignment.

---

### 📌 Overview & Business Problem
In many organizations, office equipment (printers, scanners, PCs, peripherals) sent for external maintenance suffers from lack of transparency, lost paperwork, and untracked repair states.

**OfficeRepairTracker** digitizes this entire workflow into a transparent, state-driven lifecycle with complete audit history and accountability.

---

### ⚙️ Workflow Lifecycle
1. **Device Intake & Inspection:** IT logs asset details (Asset Tag / شماره اموال, department, user, failure description).
2. **Vendor Dispatch:** Device assigned to external repair vendors with formal handover tracking.
3. **Repair Tracking:** Multi-state status pipeline:
   - `Queued for Repair` ➔ `In Repair` ➔ `Repaired / Not Repairable`
4. **Return & Verification:** Returned equipment undergoes QA testing:
   - **Passed:** Cleared for return to original department/user.
   - **Failed:** Returned back to vendor with failure logs.
5. **Audit Logs:** Full transition history logged with timestamps and technician notes.

---

### 🛠️ Tech Stack & Architecture
- **Framework:** .NET (ASP.NET Core)
- **Architecture:** Clean 3-Tier Layered Architecture (`Core`, `Infrastructure`, `Web`)
- **Data Access & ORM:** Entity Framework Core (Code-First)
- **Database:** Microsoft SQL Server
- **Frontend / UI:** ASP.NET Core MVC / Razor Pages with Bootstrap

---

### 📂 Solution Structure
- `OfficeRepairTracker.Core` → Domain models, Enums (`TicketStatus`, `DeviceType`), and business contracts.
- `OfficeRepairTracker.Infrastructure` → `ApplicationDbContext`, EF configurations, migrations, and services.
- `OfficeRepairTracker.Web` → Controllers, ViewModels, Razor Views, and UI presentation logic.

---

### 🚀 Getting Started
```bash
git clone https://github.com/Mrjackabasi/OfficeRepairTracker.git
cd OfficeRepairTracker
dotnet restore
dotnet ef database update --project OfficeRepairTracker.Infrastructure --startup-project OfficeRepairTracker.Web
dotnet run --project OfficeRepairTracker.Web
