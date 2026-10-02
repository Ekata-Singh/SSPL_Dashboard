# SSPL_Dashboard

# DRDO Scientist Records Dashboard

A full-stack internal portal for **role-based management** of scientists and administrators in a DRDO-style organization. The current implementation is a working prototype focused on secure access, scientist record management, group assignment, and document handling.

---

## 🔍 Objective

To build a **centralized internal solution** for managing sensitive personnel data, ensuring:

- Quick retrieval of scientist profiles
- Efficient updates to records
- Secure, role-based access for authorized users only
- Group-scoped management of employee information

---

## 🚀 Tech Stack

| Layer        | Technology              |
| ------------ | ----------------------- |
| Frontend     | React.js, Tailwind CSS  |
| Backend      | Node.js, Express.js     |
| Database     | MySQL                   |
| Auth         | JWT (role-based access) |
| File Storage | MinIO Object Storage    |

---

## 🔐 Roles & Access

- **Supervisor**:

  - Create & manage groups
  - Add admins and assign them to groups
  - Add scientists and assign them to groups
  - View organization-level hierarchy and group assignments

- **Admin**:

  - Manage scientists within their assigned group only
  - Update scientist details and view relevant profile information
  - Cannot access or modify data outside their group

---

## 🧭 App Structure

- **Authentication**: JWT-based login → redirects to dashboards based on role
- **Dashboards**:
  - `/SupervisorDashboard` – organization-level control
  - `/AdminDashboard` – limited to the assigned group
- **Sidebar Actions** (Supervisor only):
  - Add Group
  - Add Admin
  - Add Scientist
  - Reassign Admin to a Group

---

## 🧾 Core Features

- 🔎 **Scientist Search**: Fetch profile information using employee ID or name
- 📄 **Personal Info Management**: Name, DOB, contact, address, education, ID proofs
- 💼 **Professional Details**: Designation, department, years of service
- 📁 **Document Repository**: Upload and retrieve official documents via MinIO storage
- 🔐 **Role-Based Access**: Supervisor and Admin levels enforced on both frontend and backend
- 🧩 **Group-Based Mapping**: Scientists are associated with a specific group and accessed through group-scoped permissions

---

## 🔒 Highlights

- ✅ Strict role-based access (frontend + backend)
- ✅ Group-based scientist mapping (one scientist → one group)
- ✅ Supervisor-level visibility across organization structure
- ✅ JWT authentication and protected routes
- ✅ Functional MySQL + MinIO-backed prototype
- ✅ Clean dashboard UI for both roles

---

## 🗒️ Sample .env File

```env
DB_HOST = 'localhost'
DB_USER = 'root'
DB_PASSWORD = 'root'
DB_NAME = 'sspl_drdo_2'
JWT_SECRET = 'your_jwt_secret'

# MinIO Storage
MINIO_ENDPOINT = '192.168.1.4'
MINIO_API_PORT = 9000
MINIO_ACCESS_KEY = 'minioadmin'
MINIO_SECRET_KEY = 'minioadmin'
MINIO_BUCKET = 'ssplerp'
```

---

## 🗄️ Start MinIO Object Storage Server

Run the following command (replace `<MinIO-storage-directory>` with your MinIO installation directory):

```
minio.exe server C:\<MinIO-storage-directory> --console-address :9001
```

---

## 📦 Status

- ✅ Prototype implemented and functional for role-based scientist management
- 🔒 JWT authentication and route protection are in place
- 📂 MinIO is integrated for document upload and retrieval
- 🧪 This project currently reflects a working internal dashboard prototype rather than a full production-ready HR system
