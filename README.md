# 🏥 Hospital Analytics — Interactive Power BI Dashboard

A comprehensive **Power BI dashboard** built using **PostgreSQL** as the data source and designed in **Figma** for a modern, intuitive UI. This solution provides a **360° view of hospital operations**, including patient management, doctor performance, room occupancy, medicine sales, and financial KPIs—helping administrators and decision-makers optimize resources and improve patient care.

---

## 🔹 Short Description / Purpose
Hospitals generate large volumes of operational and clinical data, but decision-makers often lack a **single source of truth** for monitoring KPIs. This dashboard solves that by integrating data from PostgreSQL into Power BI, offering **real-time insights** into patient flow, doctor performance, medicine inventory, and financial health.

---

## 🧰 Tech Stack
- 🎨 **Figma** – UI/UX design for dashboard layout and navigation.
- 🐘 **PostgreSQL** – Relational database storing hospital data.
- 📊 **Power BI Desktop** – Visualization and interactivity platform.
- 📂 **Power Query** – Data cleaning, transformations, and schema shaping.
- 🗃️ **Data Modeling** – Star schema for optimized performance.

---

## 📚 Data Source
Dummy hospital dataset stored in PostgreSQL, including:
- **Patients**: demographics, admission/discharge details.
- **Doctors**: specialization, salary, commission metrics.
- **Appointments**: schedules and reasons.
- **Rooms**: occupancy status (General, ICU, Private).
- **Medicines**: stock vs sale, monthly trends.
- **Financials**: bills, charges, salaries.
- **Tests**: patient test results and notes.

---

## ✨ Features / Highlights
- **Overview Page**: High-level KPIs, discharge trends, bed occupancy, spend by charge type.
- **Patient Page**: Detailed patient profile, age group analysis, medicine usage, test results.
- **Doctor Page**: Doctor profile, commission calculator, appointment details.
- **Hospital Page**: Room occupancy, patient tests, operational KPIs.
- **Finance Page**: Monthwise medicine sales, spend breakdown, salary KPIs.

---

## 📑 Page-by-Page Business Requirements

### 🏠 Home
- Acts as a **navigation hub** with quick links to all pages.
- Displays hospital branding and dashboard purpose.

---

### 📊 Overview
- **KPIs**: Patients, Doctors, Staff, Total Bill Amount, Total Medicine Sale.
- **Visuals**:
  - Line chart: Patients discharged by month.
  - Donut chart: Available vs Occupied beds.
  - Bar chart: Spend by charge type (Surgery, Room, Test, Doctor, Medicine).
  - Heatmap: Medicine usage by day/month.
- **Insights**:
  - Seasonal discharge trends.
  - Resource utilization (beds, rooms).
  - Cost drivers by charge type.

---

### 🧑‍⚕️ Patient
- **Details**: Admission/discharge dates, diagnosis, doctor assigned.
- **Visuals**:
  - Age group distribution.
  - Medicine sale quantity per patient.
  - Spend breakdown by charge type.
  - Patient test results table.
- **Insights**:
  - Identify high-cost patients.
  - Common diagnoses and medicines.
  - Age group trends for admissions.

---

### 👩‍⚕️ Doctor
- **KPIs**: Commission earned, commission rate, patient spend.
- **Visuals**:
  - Doctor profile card (specialization, salary).
  - Gauge chart for commission calculator.
  - Appointment details table.
- **Insights**:
  - Commission impact on revenue.
  - Appointment load per doctor.
  - High-performing doctors by patient spend.

---

### 🏨 Hospital
- **KPIs**: Beds, rooms, suppliers.
- **Visuals**:
  - Room occupancy by type (General, ICU, Private).
  - Patient tests summary.
  - Doctor appointment list.
- **Insights**:
  - ICU vs General room utilization.
  - Operational bottlenecks in resource allocation.

---

### 💰 Finance
- **KPIs**: Overall bill, total bill amount, total medicine sale, salaries.
- **Visuals**:
  - Monthwise medicine sales trend.
  - Spend by charge type.
  - Stock vs sale percentage for medicines.
- **Insights**:
  - Revenue trends by month.
  - Medicine profitability analysis.
  - Salary distribution for staff and doctors.

---

## 🔧 Data Modeling Notes

### ✅ Star Schema (Recommended)
**Fact Tables**:
- `bills`, `bill_lines`, `admissions`, `discharges`, `appointments`, `med_sales`, `inventory_txn`, `room_status`

**Dimensions**:
- `patients`, `doctors`, `staff`, `rooms`, `charge_types`, `medicines`, `tests`, `calendar`

---

### ✅ Calendar Table
Continuous dates with:
- Year
- Quarter
- Month
- MonthName
- MonthIndex

---

### ✅ Keys & Relationships
- `bills.patient_id → patients.patient_id`
- `bill_lines.bill_id → bills.bill_id`
- `bills.attending_doctor_id → doctors.doctor_id`
- `admissions.patient_id / discharges.patient_id → patients`
- `room_status.room_id → rooms.room_id`
- Date relationships via `calendar[date]` (use `USERELATIONSHIP` when necessary).

---

### ✅ Power Query Steps
- Type conversions (dates, numbers).
- Merge lookups for dimension enrichment.
- Trim/clean text fields.
- Derive `month`, `year` columns.
- Denormalize long-tail entities for faster visuals.
---

## 📸 Dashboard Screens

### 🏠 Home
[![Home Page](https://github.com/rishikesh199/Hospital_PowerBI/blob/main/Hospital_Home.png?raw=1)](https://github.com/rishikesh199/Hospital_PowerBI/blobHome.png)

### 📊 Overview
[![Overview Page](https://github.com/rishikesh199/Hospital_PowerBI/blob/main/Hospital_Overview.png?raw=1)](https://github.com/rishikerBI/blob/main/Hospital_Overview.png)

### 🧑‍⚕️ Patient
[![Patient Page](https://github.com/rishikesh199/Hospital_PowerBI/blob/main/Hospital_Patient1.png?raw=1)](https://github.com/rishikesh199/Hospital_PowerBI/blob/main/Hospita)

### 🧑‍⚕️ Doctor
[![Doctor Page](https://github.com/rishikesh199/Hospital_PowerBI/blob/main/Hospital_Doctor.png?raw=1)](https://github.com/rishikowerBI/blob/main/Hospital_Doctor.png)

### 💰 Finance
[![Finance Page](https://github.com/rishikesh199/Hospital_PowerBI/blob/main/Hospital_Finance.png?raw=1)](https://github.com/rishikesh199/Hospital_PowerBI/blob/main/Hospital_Finance.png)

### 🧑‍⚕️ Patient
[![Patient Page](https://github.com/rishikesh199/Hospital_PowerBI/blob/main/Hospital.png?raw=1)](https://github.com/rishikesh199/Hospital_PowerBI/blob/main/Hospitaloctor)

