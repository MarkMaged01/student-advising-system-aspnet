# Student Advising System - ASP.NET Web Application

## 📋 Project Overview

This is a comprehensive **Student Advising System** built using ASP.NET Web Forms (.NET Framework 4.8). The application serves as a complete academic management system for a university, providing functionality for students, advisors, and administrators to manage academic processes, course registrations, and administrative tasks.

## 🎯 Project Status: **COMPLETE** ✅

The project has been fully implemented with all core features functional and ready for deployment.

## 🏗️ Architecture

- **Framework**: ASP.NET Web Forms (.NET Framework 4.8)
- **Database**: SQL Server (LocalDB)
- **Language**: C#
- **UI**: ASP.NET Web Forms with HTML/CSS
- **Authentication**: Role-based access control (Student, Advisor, Admin)

## 🚀 Key Features

### 👨‍🎓 Student Features
- **Registration & Login**: Student account creation and authentication
- **Course Management**: View available courses, register for courses, request course changes
- **Academic Planning**: View graduation plans, check required courses
- **Transcript Access**: View academic transcript and grades
- **Payment Management**: View payment status and installments
- **Credit Hour Requests**: Submit requests for additional credit hours

### 👨‍🏫 Advisor Features
- **Student Management**: View assigned students and their academic progress
- **Course Approval**: Approve/reject student course requests
- **Academic Guidance**: Provide academic advice and course recommendations
- **Student Status Updates**: Update student academic status

### 👨‍💼 Administrator Features
- **User Management**: Manage students, advisors, and instructors
- **Course Administration**: Add, delete, and manage courses and semesters
- **System Configuration**: Manage academic semesters and course offerings
- **Request Processing**: Handle pending requests from students and advisors
- **Payment Management**: Issue installments and manage financial records
- **Academic Planning**: Manage graduation plans and academic requirements

## 📁 Project Structure

```
DB1/
├── WebApplication1/
│   ├── WebApplication1/
│   │   ├── Pages/
│   │   │   ├── Authentication/
│   │   │   │   ├── Login.aspx
│   │   │   │   ├── Register.aspx
│   │   │   │   └── First_Page.aspx
│   │   │   ├── Student/
│   │   │   │   ├── courses.aspx
│   │   │   │   ├── course_request.aspx
│   │   │   │   ├── available_courses.aspx
│   │   │   │   ├── credithour_request.aspx
│   │   │   │   └── View_for_payments.aspx
│   │   │   ├── Advisor/
│   │   │   │   ├── advisor.aspx
│   │   │   │   ├── All_Students_Advisors.aspx
│   │   │   │   └── approve-k.aspx
│   │   │   └── Admin/
│   │   │       ├── Admin2.aspx
│   │   │       ├── Add_Course.aspx
│   │   │       ├── Delete_a_course.aspx
│   │   │       ├── All_Pending_Requests.aspx
│   │   │       └── View_all_students_transcript.aspx
│   │   ├── Web.config
│   │   ├── WebApplication1.csproj
│   │   └── packages.config
│   └── WebApplication1.sln
└── SqlQuery_1.sql
```

## 🛠️ Technology Stack

- **Backend**: ASP.NET Web Forms (.NET Framework 4.8)
- **Database**: SQL Server LocalDB
- **Authentication**: Session-based authentication
- **UI Framework**: ASP.NET Web Controls
- **Development Environment**: Visual Studio 2019/2022

## 📋 Prerequisites

Before running this application, ensure you have:

- **Visual Studio 2019** or **Visual Studio 2022** (Community Edition or higher)
- **SQL Server LocalDB** (included with Visual Studio)
- **.NET Framework 4.8** (usually pre-installed with Visual Studio)
- **Windows 10/11** (for development)

## 🚀 Installation & Setup

### 1. Clone the Repository
```bash
git clone <repository-url>
cd DB1
```

### 2. Database Setup
1. Open **SQL Server Management Studio** or **Visual Studio SQL Server Object Explorer**
2. Connect to your LocalDB instance: `(localdb)\MSSQLLocalDB`
3. Create a new database named `Advising_System`
4. Import the database schema from `SqlQuery_1.sql` (if available)

### 3. Configure Connection String
The application is configured to use LocalDB. The connection string in `Web.config` is:
```xml
<connectionStrings>
    <add name="Advising_System"
         connectionString="server=(localdb)\MSSQLLocalDB;Initial Catalog=Advising_System;Integrated Security=True" />
</connectionStrings>
```

### 4. Build and Run
1. Open `WebApplication1.sln` in Visual Studio
2. Restore NuGet packages (if prompted)
3. Build the solution (Ctrl+Shift+B)
4. Press F5 to run the application

## 🎯 Usage Guide

### Getting Started
1. **Launch the application** - The application will open in your default browser
2. **Navigate to the home page** - You'll see role selection options
3. **Choose your role** - Select Student, Advisor, or Admin
4. **Login/Register** - Use appropriate credentials for your role

### Role-Specific Workflows

#### Student Workflow
1. Register as a new student or login with existing credentials
2. View available courses for the current semester
3. Submit course registration requests
4. Check academic progress and graduation requirements
5. View payment status and manage financial records

#### Advisor Workflow
1. Login with advisor credentials
2. View assigned students and their academic progress
3. Review and approve/reject student course requests
4. Provide academic guidance and recommendations
5. Update student academic status as needed

#### Administrator Workflow
1. Login with admin credentials
2. Manage users (students, advisors, instructors)
3. Add/remove courses and semesters
4. Process pending requests from students and advisors
5. Manage system configuration and academic policies

## 🔧 Configuration

### Database Configuration
- **Server**: LocalDB instance
- **Database**: Advising_System
- **Authentication**: Windows Authentication (Integrated Security)

### Application Settings
- **Target Framework**: .NET Framework 4.8
- **Compilation**: Debug mode enabled
- **Runtime**: ASP.NET 4.8

## 📊 Features Status

| Feature | Status | Description |
|---------|--------|-------------|
| User Authentication | ✅ Complete | Login/Register for all user types |
| Student Management | ✅ Complete | Full student lifecycle management |
| Course Management | ✅ Complete | Add, delete, view courses |
| Registration System | ✅ Complete | Course registration and approval |
| Payment System | ✅ Complete | Installment and payment tracking |
| Academic Planning | ✅ Complete | Graduation plans and requirements |
| Advisor Functions | ✅ Complete | Student advising and approval |
| Admin Functions | ✅ Complete | System administration |
| Database Integration | ✅ Complete | Full SQL Server integration |
| UI/UX | ✅ Complete | Functional web interface |

## 🐛 Known Issues

- None reported - All features are functional
- Application has been tested and is ready for production use

## 🔮 Future Enhancements

Potential improvements for future versions:
- Modern UI redesign with responsive design
- API integration for mobile applications
- Enhanced reporting and analytics
- Email notification system
- Advanced search and filtering capabilities


## 📄 License

This project is developed for academic purposes. Please ensure compliance with your institution's policies regarding software usage and distribution.

---

**Last Updated**: December 2024  
**Version**: 1.0.0  
**Status**: ✅ **COMPLETE** - Ready for Production Use 