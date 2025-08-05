# Student Advising System - ASP.NET Web Application

## Project Overview

This repository contains a comprehensive Student Advising System developed as an academic project using ASP.NET Web Forms (.NET Framework 4.8). The system implements a complete university academic management solution with role-based access control, database integration, and web-based user interfaces.

## Technical Architecture

### Framework & Technologies
- **Primary Framework**: ASP.NET Web Forms (.NET Framework 4.8)
- **Programming Language**: C#
- **Database**: SQL Server LocalDB
- **Authentication**: Session-based authentication with role-based access control
- **UI Framework**: ASP.NET Web Controls with HTML/CSS
- **Development Environment**: Visual Studio 2019/2022
- **Database Provider**: System.Data.SqlClient

### Database Schema
The application connects to a SQL Server database named `Advising_System` with the following connection configuration:
```xml
<connectionStrings>
    <add name="Advising_System"
         connectionString="server=(localdb)\MSSQLLocalDB;Initial Catalog=Advising_System;Integrated Security=True" />
</connectionStrings>
```

## Project Structure Analysis

### Core Application Files
```
DB1/
├── WebApplication1/
│   ├── WebApplication1/
│   │   ├── Authentication Pages/
│   │   │   ├── First_Page.aspx - Entry point with role selection
│   │   │   ├── Login.aspx - Admin authentication interface
│   │   │   ├── Login_Student.aspx - Student login interface
│   │   │   ├── login_a.aspx - Advisor login interface
│   │   │   ├── Register.aspx - Student registration form
│   │   │   └── register_a.aspx - Advisor registration form
│   │   ├── Student Functionality/
│   │   │   ├── courses.aspx - Course viewing and management
│   │   │   ├── course_request.aspx - Course registration requests
│   │   │   ├── available_courses.aspx - Available course listings
│   │   │   ├── credithour_request.aspx - Credit hour increase requests
│   │   │   ├── View_for_payments.aspx - Payment status viewing
│   │   │   ├── required_courses.aspx - Required course listings
│   │   │   ├── missing_courses.aspx - Missing course identification
│   │   │   └── View_all_graduation_plans.aspx - Graduation plan viewing
│   │   ├── Advisor Functionality/
│   │   │   ├── advisor.aspx - Main advisor dashboard
│   │   │   ├── All_Students_Advisors.aspx - Student management interface
│   │   │   ├── approve-k.aspx - Course request approval interface
│   │   │   ├── approve-l.aspx - Credit hour request approval
│   │   │   └── Update_a_student_status.aspx - Student status updates
│   │   ├── Administrator Functionality/
│   │   │   ├── Admin2.aspx - Main admin dashboard
│   │   │   ├── Add_Course.aspx - Course addition interface
│   │   │   ├── Delete_a_course.aspx - Course deletion interface
│   │   │   ├── Add_Semester.aspx - Semester management
│   │   │   ├── All_Pending_Requests.aspx - Request processing interface
│   │   │   ├── All_Semester_courses.aspx - Semester course management
│   │   │   ├── All_Instructors_courses.aspx - Instructor-course linking
│   │   │   ├── All_advisors.aspx - Advisor management
│   │   │   ├── All_Students_Advisors.aspx - Student-advisor assignment
│   │   │   ├── View_all_students_transcript.aspx - Transcript viewing
│   │   │   ├── View_for_payments.aspx - Payment management
│   │   │   ├── Issue_installments.aspx - Installment processing
│   │   │   ├── Fetch_details_of_active_students.aspx - Student data retrieval
│   │   │   └── Fetch_semesters.aspx - Semester data retrieval
│   │   ├── Data Management/
│   │   │   ├── insert-d.aspx - Data insertion interface
│   │   │   ├── insert-e.aspx - Additional data insertion
│   │   │   ├── update-f.aspx - Data update interface
│   │   │   ├── delete.aspx - Data deletion interface
│   │   │   ├── view-c.aspx - Data viewing interface
│   │   │   ├── view-h.aspx - Additional data viewing
│   │   │   ├── view-i.aspx - Data viewing interface
│   │   │   └── view-j.aspx - Data viewing interface
│   │   ├── Configuration Files/
│   │   │   ├── Web.config - Application configuration
│   │   │   ├── Web.Debug.config - Debug configuration
│   │   │   ├── Web.Release.config - Release configuration
│   │   │   ├── packages.config - NuGet package dependencies
│   │   │   └── WebApplication1.csproj - Project file
│   │   └── Compiled Output/
│   │       ├── bin/ - Compiled assemblies
│   │       └── obj/ - Intermediate build files
│   └── WebApplication1.sln - Visual Studio solution file
└── SqlQuery_1.sql - Database schema file
```

## Technical Implementation Details

### Authentication System
The application implements a multi-tier authentication system:
- **Session Management**: Uses ASP.NET session state for user authentication
- **Role-Based Access**: Three distinct user roles (Student, Advisor, Administrator)
- **Login Interfaces**: Separate login pages for each user type
- **Registration System**: Student and advisor registration capabilities

### Database Integration
- **Connection Management**: Centralized connection string in Web.config
- **SQL Queries**: Direct SQL queries using SqlCommand and SqlDataReader
- **Data Access Pattern**: ADO.NET for database operations
- **Error Handling**: Try-catch blocks for database operation exceptions

### User Interface Implementation
- **Web Forms**: ASP.NET Web Forms with code-behind files
- **Server Controls**: Extensive use of ASP.NET server controls
- **Event Handling**: Server-side event handling for user interactions
- **Data Binding**: GridView and other data-bound controls for data display

### Business Logic Implementation

#### Student Module
- **Course Registration**: Multi-step course registration process
- **Academic Planning**: Graduation plan viewing and course requirement checking
- **Payment Management**: Installment tracking and payment status viewing
- **Request System**: Credit hour increase and course change requests

#### Advisor Module
- **Student Management**: View and manage assigned students
- **Request Processing**: Approve/reject student requests
- **Academic Guidance**: Provide course recommendations and academic advice
- **Status Updates**: Update student academic status and progress

#### Administrator Module
- **System Management**: Complete system administration capabilities
- **User Management**: Add, edit, and delete users across all roles
- **Course Administration**: Full course lifecycle management
- **Semester Management**: Academic semester configuration
- **Request Processing**: Handle all pending system requests

## Code Structure Analysis

### Page Structure Pattern
Each ASPX page follows a consistent pattern:
```csharp
// Code-behind file structure
public partial class PageName : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        // Page initialization logic
    }
    
    // Event handlers for user interactions
    protected void Button_Click(object sender, EventArgs e)
    {
        // Business logic implementation
    }
}
```

### Database Access Pattern
```csharp
// Standard database access pattern used throughout
using (SqlConnection conn = new SqlConnection(connectionString))
{
    conn.Open();
    using (SqlCommand cmd = new SqlCommand(query, conn))
    {
        // Parameter binding and execution
        SqlDataReader reader = cmd.ExecuteReader();
        // Data processing
    }
}
```

### Session Management
```csharp
// Session-based authentication implementation
Session["UserID"] = userID;
Session["UserRole"] = userRole;
Session["UserName"] = userName;
```

## Development Environment Setup

### Prerequisites
- **Visual Studio**: 2019 or 2022 (Community Edition or higher)
- **SQL Server**: LocalDB instance (included with Visual Studio)
- **.NET Framework**: Version 4.8
- **Operating System**: Windows 10/11
- **Web Browser**: Any modern web browser for testing

### Project Configuration
1. **Solution File**: `WebApplication1.sln` - Main Visual Studio solution
2. **Target Framework**: .NET Framework 4.8
3. **Compilation**: Debug configuration enabled
4. **IIS Express**: Configured for local development
5. **SSL Port**: 44392 (development HTTPS)

### Database Configuration
- **Server Instance**: `(localdb)\MSSQLLocalDB`
- **Database Name**: `Advising_System`
- **Authentication**: Windows Authentication (Integrated Security)
- **Connection String**: Configured in Web.config

## Build and Deployment Process

### Local Development Setup
1. **Clone Repository**: Download project files to local machine
2. **Open Solution**: Open `WebApplication1.sln` in Visual Studio
3. **Restore Packages**: NuGet package restoration (if prompted)
4. **Database Setup**: Create and configure `Advising_System` database
5. **Build Solution**: Compile project (Ctrl+Shift+B)
6. **Run Application**: Press F5 to start debugging

### Database Schema Implementation
The database schema includes tables for:
- **Users**: Students, advisors, and administrators
- **Courses**: Course catalog and offerings
- **Semesters**: Academic term management
- **Registrations**: Student course registrations
- **Requests**: Various academic requests
- **Payments**: Financial transaction tracking
- **Academic Records**: Transcripts and grades

## Technical Features Implementation

### Data Validation
- **Client-Side**: ASP.NET validation controls
- **Server-Side**: C# validation logic in code-behind files
- **Database Constraints**: SQL Server constraints and triggers

### Error Handling
- **Exception Management**: Try-catch blocks throughout application
- **User Feedback**: Error messages displayed to users
- **Logging**: Basic error logging implementation

### Security Implementation
- **Input Validation**: SQL injection prevention through parameterized queries
- **Session Security**: Session timeout and validation
- **Role-Based Access**: Page-level access control

## Code Quality and Standards

### Naming Conventions
- **Files**: PascalCase for page names (e.g., `Add_Course.aspx`)
- **Classes**: PascalCase for class names
- **Methods**: PascalCase for method names
- **Variables**: camelCase for local variables

### Code Organization
- **Separation of Concerns**: UI logic separated from business logic
- **Code-Behind Files**: Each ASPX page has corresponding .cs file
- **Database Access**: Centralized connection management

### Documentation
- **Inline Comments**: Code comments for complex logic
- **Method Documentation**: XML documentation for public methods
- **Configuration Comments**: Web.config documentation

## Testing and Quality Assurance

### Manual Testing Performed
- **User Authentication**: Login/logout functionality for all roles
- **Data Operations**: CRUD operations for all entities
- **Business Logic**: Course registration and approval workflows
- **UI Functionality**: All user interface interactions
- **Database Integration**: All database operations and queries

### Known Technical Limitations
- **Browser Compatibility**: Designed for modern browsers
- **Scalability**: Optimized for small to medium user bases
- **Performance**: Basic optimization implemented

## Future Technical Enhancements

### Potential Improvements
- **Modern UI Framework**: Migration to ASP.NET Core or MVC
- **API Development**: RESTful API implementation
- **Mobile Support**: Responsive design implementation
- **Advanced Security**: JWT token authentication
- **Performance Optimization**: Caching and query optimization
- **Logging Framework**: Structured logging implementation
- **Unit Testing**: Automated test suite development

### Code Refactoring Opportunities
- **Repository Pattern**: Implement data access abstraction
- **Dependency Injection**: Modern dependency management
- **Async/Await**: Asynchronous programming patterns
- **Modern C# Features**: Utilize latest C# language features

## Academic Project Context

This project was developed as part of an academic curriculum focusing on:
- **Database Management Systems**: SQL Server implementation
- **Web Development**: ASP.NET Web Forms framework
- **Software Engineering**: System design and implementation
- **User Interface Design**: Web-based user experience
- **Business Logic Implementation**: Real-world application development

## Technical Documentation

### Database Schema Documentation
- **Entity Relationship Diagrams**: Available in project documentation
- **Table Descriptions**: Comprehensive table structure documentation
- **Stored Procedures**: Database procedure documentation
- **Triggers**: Database trigger implementation details

### API Documentation
- **Page Interfaces**: Detailed page functionality documentation
- **Method Signatures**: Public method documentation
- **Parameter Descriptions**: Input/output parameter documentation
- **Return Values**: Method return value specifications

## Conclusion

This Student Advising System represents a comprehensive implementation of web-based academic management using ASP.NET Web Forms. The project demonstrates proficiency in database design, web development, user interface design, and business logic implementation. The codebase serves as a foundation for understanding enterprise-level web application development and can be extended for additional features and improvements.

---

**Project Status**: Complete and Functional  
**Last Updated**: December 2024  
**Technical Stack**: ASP.NET Web Forms (.NET Framework 4.8)  
**Database**: SQL Server LocalDB  
**Development Environment**: Visual Studio 2019/2022 