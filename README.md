# User Management System with Supabase

<div align="center">
  <img src="https://supabase.com/_next/image?url=%2Fimages%2Fproduct%2Fsupabase-logo-wordmark--dark.png&w=3840&q=75" width="400" alt="Supabase Logo">
  <br><br>
</div>

A complete user management system with authentication via ID number and role-based access control.

## ✨ Features

- 🔐 ID-based authentication (no email required)
- 👥 User CRUD operations
- 🛡️ Three user roles (Normal, Admin, Super Admin)
- 📱 Responsive design
- 🔄 Session persistence with localStorage
- ⚡ Direct Supabase REST API integration

## 🚀 Quick Start

1. Clone the repository:
```bash
git clone https://github.com/yourusername/user-management-system.git
Open index.html in your browser or use Live Server

🛠 Supabase Setup
Database Table
sql
Copy
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
RLS Policies
sql
Copy
ALTER TABLE usuarios ENABLE ROW LEVEL SECURITY;

CREATE POLICY "Enable access for authenticated users" 
ON usuarios FOR ALL 
TO authenticated 
USING (true);
📂 Project Structure
Copy
user-management-system/
├── index.html            # Main application file
├── README.md            # Documentation
└── assets/
    └── styles.css       # All CSS styles
🎨 UI Components
Component	Description
Auth Screen	Login/Register forms
User Dashboard	CRUD interface for user management
Modals	For adding/editing users
🔧 Configuration
Replace these values in index.html:

javascript
Copy
const SUPABASE_URL = 'your-supabase-url';
const SUPABASE_KEY = 'your-supabase-key';
📜 License
MIT License - See LICENSE for details