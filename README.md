<p align="center">
  <img src="DVLD/Resources/DVLD Logo.png" alt="DVLD Logo" width="200"/>
</p>

<h1 align="center">🚗 Driving & Vehicle License Department (DVLD)</h1>

<p align="center">
  <strong>A comprehensive desktop application for managing driving licenses, vehicle registrations, and related services</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows-blue?style=for-the-badge&logo=windows" alt="Platform"/>
  <img src="https://img.shields.io/badge/Language-C%23-239120?style=for-the-badge&logo=csharp" alt="Language"/>
  <img src="https://img.shields.io/badge/Framework-.NET%20Framework-512BD4?style=for-the-badge&logo=dotnet" alt="Framework"/>
  <img src="https://img.shields.io/badge/Database-SQL%20Server-CC2927?style=for-the-badge&logo=microsoftsqlserver" alt="Database"/>
  <img src="https://img.shields.io/badge/UI-WinForms-68217A?style=for-the-badge" alt="UI"/>
</p>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Architecture](#-architecture)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Database Schema](#-database-schema)
- [Getting Started](#-getting-started)
- [Usage](#-usage)
- [Screenshots](#-screenshots)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🔍 Overview

**DVLD** (Driving & Vehicle License Department) is a full-featured desktop management system built to handle the complete lifecycle of driving license operations. It simulates a real-world government department workflow — from person registration to license issuance, renewal, replacement, and detention management.

The application follows a strict **3-Tier Architecture** design pattern, ensuring clean separation of concerns, maintainability, and scalability.

---

## 🏗 Architecture

The system is built on a **3-Tier Architecture** with clear separation of concerns:

```
┌─────────────────────────────────────────────────┐
│              Presentation Layer (DVLD)           │
│         Windows Forms UI / User Controls         │
├─────────────────────────────────────────────────┤
│           Business Logic Layer (DVLD_Business)   │
│        Validation / Rules / Data Processing      │
├─────────────────────────────────────────────────┤
│          Data Access Layer (DVLD_DataAccess)      │
│         ADO.NET / SQL Server / Stored Procs       │
└─────────────────────────────────────────────────┘
```

| Layer | Project | Responsibility |
|-------|---------|----------------|
| **Presentation** | `DVLD` | WinForms UI, user controls, form navigation, and event handling |
| **Business Logic** | `DVLD_Buisness` | Business rules, validation logic, and data processing |
| **Data Access** | `DVLD_DataAccess` | Database communication via ADO.NET with stored procedures |

---

## ✨ Features

### 👤 People Management
- Add, update, and delete person records
- Advanced search and filtering capabilities
- Person details card with photo support
- National ID–based identification

### 🪪 Local Driving License Applications
- New license application workflow
- Application tracking with status management
- License class selection (e.g., Ordinary, Commercial, Motorcycle, etc.)
- Complete application lifecycle management

### 📝 Testing System
- **Vision Test** — Automated scheduling and result recording
- **Written (Theory) Test** — Knowledge assessment management
- **Street (Practical) Test** — Driving skills evaluation
- Test appointment scheduling with conflict detection
- Test type configuration and fee management
- Retake test functionality

### 🌍 International Driving License
- Issue international licenses based on active local licenses
- International license application management
- License validity tracking

### 🔄 License Services
- **Renew License** — Extend license validity with fee processing
- **Replace Lost License** — Issue replacement for lost licenses
- **Replace Damaged License** — Issue replacement for damaged licenses
- Full audit trail for all license operations

### 🔒 License Detention
- Detain driving licenses
- Release detained licenses with fee processing
- Detained licenses management dashboard

### 👥 User & Access Management
- User authentication (Login / Logout)
- User account management (Add / Update / Delete)
- Password management and change functionality
- Logged-in user session tracking

### ⚙️ System Configuration
- Manage Application Types and their fees
- Manage Test Types and their fees
- Configurable license classes

---

## 🛠 Tech Stack

| Technology | Usage |
|------------|-------|
| **C# (.NET Framework)** | Primary programming language |
| **Windows Forms (WinForms)** | Desktop UI framework |
| **ADO.NET** | Database communication |
| **SQL Server** | Relational database management |
| **Stored Procedures** | Database operations |
| **Visual Studio 2022** | IDE |

---

## 📁 Project Structure

```
Driving-Vehicle-License-Management-System-DVLD/
│
├── DVLD/                              # Presentation Layer
│   ├── Applications/                  # Application-related forms
│   │   ├── Application Types/         # Manage application types
│   │   ├── Controls/                  # Application user controls
│   │   ├── International License/     # International license forms
│   │   ├── Local Driving License/     # Local license application forms
│   │   ├── Renew Local License/       # License renewal forms
│   │   ├── ReplaceLostOrDamagedLicense/ # Lost/damaged replacement
│   │   └── Release Detained License/  # Release detained license forms
│   │
│   ├── Drivers/                       # Driver listing and management
│   ├── Global Classes/                # Utility and helper classes
│   ├── Licenses/                      # License-related forms
│   │   ├── Controls/                  # License display controls
│   │   ├── Detain License/            # License detention forms
│   │   ├── International Licenses/    # International license views
│   │   └── Local Licenses/            # Local license views and controls
│   │
│   ├── Login/                         # Authentication forms
│   ├── People/                        # Person management forms
│   │   └── Controls/                  # Person card user controls
│   │
│   ├── Resources/                     # Images, icons, and assets
│   ├── Tests/                         # Test scheduling and management
│   │   ├── Controls/                  # Test-related user controls
│   │   └── Test Types/                # Test type configuration forms
│   │
│   ├── User/                          # User management forms
│   ├── frmMain.cs                     # Main application form
│   ├── Program.cs                     # Application entry point
│   └── DVLD.sln                       # Visual Studio solution file
│
├── DVLD_Buisness/                     # Business Logic Layer
│   ├── clsApplication.cs             # Application business logic
│   ├── clsApplicationType.cs         # Application type management
│   ├── clsCountry.cs                 # Country data handling
│   ├── clsDetainedLicense.cs         # Detained license logic
│   ├── clsDriver.cs                  # Driver business logic
│   ├── clsInternationalLicense.cs    # International license logic
│   ├── clsLicense.cs                 # License core business logic
│   ├── clsLicenseClass.cs            # License class management
│   ├── clsLocalDrivingLicenseApplication.cs # Local DL application logic
│   ├── clsPerson.cs                  # Person business logic
│   ├── clsTest.cs                    # Test business logic
│   ├── clsTestAppointment.cs         # Test appointment management
│   ├── clsTestType.cs                # Test type business logic
│   └── clsUser.cs                    # User authentication & management
│
├── DVLD_DataAccess/                   # Data Access Layer
│   ├── clsDataAccessSettings.cs      # Database connection configuration
│   ├── clsPersonData.cs              # Person data operations
│   ├── clsApplication.cs             # Application data operations
│   ├── clsDriver.cs                  # Driver data operations
│   ├── clsLicense.cs                 # License data operations
│   ├── clsDetainedLicense.cs         # Detained license data operations
│   ├── clsInternationalLicense.cs    # International license data operations
│   ├── clsLocalDrivingLicenseApplicationData.cs # Local DL app data ops
│   ├── clsTest.cs                    # Test data operations
│   ├── clsTestAppointment.cs         # Test appointment data operations
│   ├── clsTestType.cs                # Test type data operations
│   ├── clsUserData.cs                # User data operations
│   ├── clsCountryData.cs             # Country data operations
│   ├── ApplicationType.cs            # Application type data operations
│   └── LicenseClass.cs               # License class data operations
│
├── .gitignore
└── README.md
```

---

## 🗄 Database Schema

The system uses a **SQL Server** database with the following core tables:

| Table | Description |
|-------|-------------|
| `People` | Personal information records |
| `Users` | System user accounts and credentials |
| `Drivers` | Registered driver records |
| `Applications` | All application records (base table) |
| `LocalDrivingLicenseApplications` | Local driving license application details |
| `Licenses` | Issued license records |
| `InternationalLicenses` | International license records |
| `DetainedLicenses` | Detained/suspended license records |
| `Tests` | Test result records |
| `TestAppointments` | Scheduled test appointments |
| `TestTypes` | Test type configuration (Vision, Written, Street) |
| `ApplicationTypes` | Application type configuration and fees |
| `LicenseClasses` | License class definitions |
| `Countries` | Country reference data |

---

## 🚀 Getting Started

### Prerequisites

- **Windows 10/11**
- **Visual Studio 2022** (or later)
- **SQL Server 2019** (or later) / SQL Server Express
- **.NET Framework 4.7.2** (or later)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Youssef-AbdelRaafi/Driving-Vehicle-License-Management-System-DVLD.git
   ```

2. **Set up the database**
   - Open SQL Server Management Studio (SSMS)
   - Create a new database named `DVLD`
   - Execute the provided database scripts to create tables and stored procedures

3. **Configure the connection string**
   - Open `DVLD_DataAccess/clsDataAccessSettings.cs`
   - Update the connection string to match your SQL Server configuration:
   ```csharp
   public static string ConnectionString = "Server=.;Database=DVLD;User Id=sa;Password=YOUR_PASSWORD;";
   ```

4. **Build and run**
   - Open `DVLD/DVLD.sln` in Visual Studio
   - Restore NuGet packages if prompted
   - Build the solution (`Ctrl + Shift + B`)
   - Run the application (`F5`)

---

## 💡 Usage

1. **Login** — Start the application and log in with valid credentials
2. **Main Dashboard** — Navigate through the menu to access all modules
3. **People Management** — Register and manage person records
4. **Applications** — Create and process license applications
5. **Tests** — Schedule and record test results
6. **License Services** — Renew, replace, or manage license operations
7. **Administration** — Manage users, application types, and test types

---

## 📸 Screenshots

> _Application screenshots can be added here to showcase the UI._

| Screen | Description |
|--------|-------------|
| Login | Secure authentication screen |
| Main Dashboard | Central navigation hub |
| People Management | CRUD operations for person records |
| License Application | New license application workflow |
| Test Scheduling | Test appointment management |

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

<p align="center">
  <strong>Built with ❤️ by <a href="https://github.com/Youssef-AbdelRaafi">Youssef AbdelRaafi</a></strong>
</p>
