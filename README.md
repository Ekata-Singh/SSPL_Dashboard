# SSPL_Dashboard

# DRDO Scientist Records Dashboard

A secure, full-stack internal portal for **role-based management** of scientists and administrators at DRDO.\
The system enables supervisors and admins to manage personnel records, assign groups, and securely access sensitive information.

---

## 🔍 Objective

To develop a **centralized, digital solution** that streamlines the management of sensitive personnel data, ensuring:

- Quick retrieval of scientist profiles
- Efficient updates to records
- Secure, role-based access for authorized users only

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
  - Add admins and assign them groups
  - Add scientists and assign them to groups
  - Full access across the organization

- **Admin**:

  - Manage scientists within their assigned group only
  - Cannot access or modify data outside their group

---

## 🧭 App Structure

- **Authentication**: JWT-based login → redirects to dashboards based on role
- **Dashboards**:
  - `/supervisor-dashboard` – full organizational control
  - `/admin-dashboard` – limited to own group
- **Sidebar Actions** (Supervisor only):
  - Add Group
  - Add Admin
  - Add Scientist
  - Reassign Admin to a Group

---

## 🧾 Core Features

- 🔎 **Scientist Search**: Fetch full profile using employee number or name
- 📄 **Personal Info Management**: Name, DOB, contact, address, education, ID proofs
- 💼 **Professional Details**: Designation, department, years of service
- 💰 **Salary Records**: Pay grade, allowances, deductions, salary history
- 📆 **Leave Management**: Leave balances, history, request tracking
- 📁 **Document Repository**: Upload/view official documents (joining letter, NOCs, etc.)
- 🔐 **Role-Based Access**: Supervisor and Admin levels, enforced on frontend + backend
- 📊 **Analytics Dashboard** (future scope): Summary stats, charts, and trends

---

## 🔒 Highlights

- ✅ Strict role-based access (frontend + backend)
- ✅ Group-based scientist mapping (one scientist → one group)
- ✅ Supervisor has organization-wide visibility
- ✅ Fully functional backend with JWT authentication
- ✅ Clean UI for both roles
- ✅ Ready for deployment

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

- ✅ Completed and functional system
- 🔒 Secure role-based access with JWT
- 📂 MinIO integrated for file/document storage
- 🖥️ Ready for production deployment
