# AuditPay

A payroll and attendance app built as a DBMS course project at VIT Chennai. It brings employee records, leave requests, payroll calculations, and activity logs into one interface.

The frontend uses React and Vite, with Recharts for the dashboard. The API is built with Express and stores data in MongoDB through Mongoose.

## What you can do

| Role | Main workflow |
| --- | --- |
| Admin | Manage employees, review leave requests, view analytics and activity logs |
| Payroll & Attendance Officer | Record attendance, generate payroll, and mark payments as paid |
| Employee | View attendance and salary history, request leave, and review payslips |

The app also includes sample employee generation and historical payroll synchronisation for demonstrations.

## Run locally

Use Node.js 22.12+ and a running MongoDB instance.

```bash
git clone https://github.com/kailashp-27/Audit-Pay.git
cd Audit-Pay/backend
npm install
```

Create `backend/.env`:

```env
MONGO_URI=mongodb://127.0.0.1:27017/Audit_Payn
PORT=5000
```

Start the API from `backend/`:

```bash
node server.js
```

Create `frontend/.env` with the API address used by the login screen:

```env
VITE_API_BASE_URL=http://localhost:5000
```

In another terminal, from the repository root:

```bash
cd frontend
npm install
npm run dev
```

Open [localhost:5173](http://localhost:5173). The frontend expects the API on port 5000.

For a local demonstration, the admin login is username `ADMIN` and password `ADMIN`. Employee and PAO accounts can be added through the app.

## Payroll rules

The demonstration uses a daily rate of `BaseSalary / 30`, a 10% tax deduction, and a 5% provident fund deduction for employees with PF enabled. Leave deductions and bonuses are included where applicable.

```text
Net pay = Base salary - Leave deductions - Tax - PF + Bonus
```

These are project rules, not a complete payroll policy.

## Code guide

- `backend/server.js` contains the API routes and payroll calculations.
- `backend/models/` defines employee, attendance, leave, payroll, and log records.
- `frontend/src/` contains the role dashboards and management screens.

From `frontend/`, run `npm run build` to create a production bundle or `npm run lint` to check the frontend.

## Current scope

This is a coursework prototype. The login endpoint returns demo tokens, and the admin credentials are fixed in the code. Role-specific screens and stored activity logs should not be treated as production authentication or tamper-proof auditing.
