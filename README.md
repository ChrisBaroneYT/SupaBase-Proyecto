# 🔐 User Management System with Supabase

![System Preview](./preview.png) <!-- Add a screenshot if available -->

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
Database Setup
Execute this SQL in your Supabase SQL editor:

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
Security Configuration
sql
Copy
-- Enable Row-Level Security
ALTER TABLE usuarios ENABLE ROW LEVEL SECURITY;

-- Basic access policy
CREATE POLICY "Enable access for authenticated users"
ON usuarios FOR ALL
TO authenticated
USING (true);
Important: For production environments, implement more restrictive security policies tailored to your requirements.

Connect to Your Supabase Project
Update these values in index.html:

javascript
Copy
const SUPABASE_URL = 'your-project-url';
const SUPABASE_KEY = 'your-anon-key';
Find these credentials at:
Supabase Dashboard → Project Settings → API

📂 Project Structure
Copy
user-management-system/
├── index.html          # Main application entry point
├── README.md           # Project documentation
└── styles.css          # All CSS styles
🖥️ System Components
Component	Description
Authentication	Secure login/registration with validation
User Dashboard	Interactive table with sort/filter capabilities
User Editor	Unified form for adding/editing user records
Confirmation Dialogs	Safety prompts for destructive actions
🛡️ Security Implementation
Validation Rules:

Names: Letters and spaces only

Emails: Must contain @ and valid domain

Passwords: Required for new users

Access Control:

Normal users: Read-only access

Admins: Can manage normal users

Super Admins: Full system control

🔍 Troubleshooting Guide
Issue	Solution
.reset() is not a function	Ensure form elements use <form> tags
Authentication failures	Verify Supabase credentials and user data
Missing permissions	Check RLS policies in Supabase
📜 License
MIT License - See LICENSE for full details.

🤝 How to Contribute
Fork the repository

Create a feature branch (git checkout -b feature/your-feature)

Commit your changes (git commit -m 'Add some feature')

Push to the branch (git push origin feature/your-feature)

Open a Pull Request

📬 Contact Information
Developer: Cristian Sánchez
Email: co.cristiand@gmail.com
GitHub: https://github.com/ChrisBaroneYT

For support requests, please include:

Detailed description of the issue

Steps to reproduce

Screenshots if applicable

Copy

Key improvements:
1. Better visual hierarchy with consistent emoji usage
2. More detailed feature descriptions
3. Improved security section
4. Clearer troubleshooting table
5. Enhanced contribution guidelines
6. Professional contact information format
7. Better organization of technical details
8. More prominent callouts for important notes
9. Consistent formatting throughout
10. Added placeholder for system preview image

The README now presents a more professional image while maintaining all technical details and being easier to navigate.