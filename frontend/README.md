# AuditPay frontend

The React interface for AuditPay, with separate admin, payroll officer, and employee screens. Vite runs the development server; Recharts handles the dashboard charts.

## Development

Start the API on port 5000 using the [project setup guide](../README.md), then run from this directory:

```bash
npm install
npm run dev
```

Set `VITE_API_BASE_URL=http://localhost:5000` in `frontend/.env` before starting Vite, then open [localhost:5173](http://localhost:5173).

```bash
npm run build
npm run lint
npm run preview
```

The main screens are in `src/`: `AdminDashboard.jsx`, `EmployeeDashboard.jsx`, `AttendanceModule.jsx`, and `PayrollRunner.jsx`. `App.jsx` handles the app routes.
