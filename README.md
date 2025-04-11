# 🔐 User Management System with Supabase

A robust, full-featured user management system with secure authentication, role-based access control, and complete CRUD functionality, powered by Supabase's backend services.

## 🌟 Key Features

- **Secure Authentication**  
  🔐 Unique identification-based login system  
  📝 Registration with comprehensive validation  
  🔄 Automatic session persistence

- **User Management**  
  👥 Three-tier role system (User/Admin/Super Admin)  
  ➕ Create new user accounts  
  ✏️ Edit existing user information  
  🗑️ Delete users with confirmation  

- **Technical Excellence**  
  ⚡ Direct Supabase REST API integration  
  📱 Fully responsive design  
  🛡️ Client-side input validation  
  ⏳ Loading indicators for async operations

## 🚀 Quick Start

### Prerequisites
- Modern web browser (Chrome, Firefox, Edge recommended)
- Supabase account ([sign up for free](https://supabase.com/))

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/ChrisBaroneYT/user-management-system.git
   cd user-management-system
   ```

2. Launch the application:
   Simple method: Double-click index.html
   Recommended method: Use a local server like VS Code Live Server

### ⚙️ Backend Configuration

- **Database Setup**
Execute this SQL in your Supabase SQL editor:
```bash
CREATE TABLE usuarios (
  id_usuario SERIAL PRIMARY KEY,
  identificacion BIGINT UNIQUE NOT NULL,
  nombre_usuario TEXT NOT NULL,
  email TEXT NOT NULL,
  clave_encriptada TEXT NOT NULL,
  usuario_normal BOOLEAN DEFAULT FALSE,
  usuario_administrador BOOLEAN DEFAULT FALSE,
  usuario_superadministrador BOOLEAN DEFAULT FALSE
);
```
### 🔐 Security Configuration
   ```bash
-- Enable Row-Level Security
ALTER TABLE usuarios ENABLE ROW LEVEL SECURITY;

-- Basic access policy
CREATE POLICY "Enable access for authenticated users"
ON usuarios FOR ALL
TO authenticated
USING (true);
  ```

Connect to Your Supabase Project
Update these values in index.html:
   ```bash
const SUPABASE_URL = 'your-project-url';
const SUPABASE_KEY = 'your-anon-key';
Find these credentials at:
   ```
Supabase Dashboard → Project Settings → API

### 📂 Project Structure
   ```bash
user-management-system/
├── index.html          # Main application entry point
├── README.md           # Project documentation
└── styles.css          # All CSS styles
  ```

### 🤝 How to Contribute
📬 Contact Information:
:Developer: Cristian Sánchez
:Email: [co.cristiand@gmail.com]
:GitHub: [https://github.com/ChrisBaroneYT]
