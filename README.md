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

## 🗄️ Database Schema

The system uses a comprehensive SQL Server database with the following main tables:

### Core Tables
- **Advisor**: Academic advisors information
- **Student**: Student records and academic information
- **Course**: Course catalog and details
- **Instructor**: Faculty information
- **Semester**: Academic semester management
- **Graduation_Plan**: Student graduation planning
- **Request**: Student requests and approvals
- **Payment**: Financial records and installments

### Relationship Tables
- **Student_Phone**: Student contact information
- **Student_Instructor_Course_take**: Course enrollment and grades
- **Instructor_Course**: Course-instructor assignments
- **Course_Semester**: Course offerings by semester
- **GradPlan_Course**: Graduation plan course requirements
- **PreqCourse_course**: Course prerequisites
- **Slot**: Course scheduling and time slots

## 🛠️ Installation & Setup

### Prerequisites
- Visual Studio 2019 or later
- .NET Framework 4.8
- SQL Server LocalDB
- IIS Express (included with Visual Studio)

### Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone [repository-url]
   cd DB1
   ```

2. **Database Setup**
   - Open `SqlQuery_1.sql` in SQL Server Management Studio
   - Execute the script to create the database and tables
   - The database will be created as `Advising_System`

3. **Application Setup**
   - Open `WebApplication1/WebApplication1.sln` in Visual Studio
   - Restore NuGet packages if prompted
   - Update connection string in `Web.config` if needed:
     ```xml
     <connectionStrings>
       <add name="Advising_System"
            connectionString="server=(localdb)\MSSQLLocalDB;Initial Catalog=Advising_System;Integrated Security=True" />
     </connectionStrings>
     ```

4. **Run the Application**
   - Press F5 or click "Start Debugging" in Visual Studio
   - The application will open in your default browser

## 📁 Project Structure

```
DB1/
├── SqlQuery_1.sql                 # Database schema and procedures
├── WebApplication1/
│   ├── WebApplication1.sln        # Solution file
│   └── WebApplication1/
│       ├── *.aspx                 # Web pages
│       ├── *.aspx.cs              # Code-behind files
│       ├── *.aspx.designer.cs     # Designer files
│       ├── Web.config             # Application configuration
│       ├── packages.config        # NuGet packages
│       └── WebApplication1.csproj # Project file
```

## 🔐 User Roles & Access

### Student Access
- **Login**: `Login_Student.aspx`
- **Registration**: `Register.aspx`
- **Main Features**: Course registration, transcript viewing, payment status

### Advisor Access
- **Login**: `login_a.aspx`
- **Registration**: `register_a.aspx`
- **Main Features**: Student management, course approvals, academic guidance

### Administrator Access
- **Login**: `Login.aspx`
- **Main Features**: System administration, user management, course management

## 🎨 User Interface

The application features a clean, user-friendly interface with:
- Role-based navigation
- Responsive design
- Intuitive forms and data entry
- Comprehensive data display and reporting

## 🔧 Technical Details

### Database Connection
- Uses SQL Server LocalDB for development
- Connection string configured in `Web.config`
- Integrated Security for authentication

### Security Features
- Password-based authentication
- Role-based access control
- Session management
- Input validation and sanitization

### Code Organization
- Separation of concerns (UI, Business Logic, Data Access)
- Code-behind pattern for ASP.NET Web Forms
- Stored procedures for database operations

## 📊 Key Functionality

### Academic Management
- Course registration and enrollment
- Grade management and transcript generation
- Graduation planning and tracking
- Prerequisite checking and enforcement

### Administrative Tasks
- User account management
- Course catalog maintenance
- Semester scheduling
- Financial record keeping

### Communication
- Student-advisor communication
- Request and approval workflows
- Notification system for status updates

## 🚀 Deployment

### Development Environment
- Visual Studio 2019/2022
- IIS Express for local development
- SQL Server LocalDB

### Production Considerations
- SQL Server Standard/Enterprise
- IIS Web Server
- Windows Server environment
- SSL certificate for HTTPS

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📝 License

This project is developed for academic purposes and educational use.


## 🔄 Version History

- **v1.0**: Initial release with complete functionality
- Full student, advisor, and administrator features
- Comprehensive database schema
- Complete web application interface

---

**Note**: This is a complete, production-ready academic management system designed for university use. All core features have been implemented and tested. 
