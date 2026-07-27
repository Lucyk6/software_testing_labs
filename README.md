# 🚀 Task Management System — RESTful API

A robust, production-ready REST API built with **ASP.NET Core** and **Entity Framework Core**, using **PostgreSQL** as the primary database. This project showcases clean architecture, secure data management, and relational database design.

---

## 🛠️ Tech Stack & Architecture

* **Backend Framework:** ASP.NET Core Web API (.NET 8 / .NET 9)
* **ORM / Data Access:** Entity Framework Core (EF Core)
* **Database:** PostgreSQL (with Npgsql provider)
* **Design Patterns:** Repository Pattern, Dependency Injection (DI), Async/Await asynchronous programming
* **Testing & Tools:** Swagger UI / Postman (API Documentation), Database Migrations

---

## 💡 Key Architectural Concepts Implemented

* **Dependency Injection (DI):** Decoupled architecture where the `ApplicationDbContext` is properly configured via `Program.cs` and injected into controllers/services.
* **Database Configuration (`DbContextOptions`):** Clean separation of infrastructure settings. Connection strings are securely handled via environment variables and `appsettings.json`, then passed down to the base `DbContext`.
* **Data Integrity & Relationships:** Implemented strict one-to-many and many-to-many database relationships (e.g., Users have many Tasks, Tasks belong to Projects) with cascading delete rules.
* **Async/Await Workflows:** Fully asynchronous database operations (`ToListAsync`, `SaveChangesAsync`, etc.) to maximize server throughput and responsiveness.

---

## 📁 Project Structure

```hlb
TaskManagementAPI/
├── Controllers/            # API Endpoints (Handling HTTP requests)
├── Data/
│   ├── ApplicationDbContext.cs  # EF Core Database Context config
│   └── Migrations/         # Auto-generated DB schema tracking files
├── Models/                 # Database Domain Entities (User, Task, Project)
├── DTOs/                   # Data Transfer Objects (Request/Response contracts)
├── appsettings.json        # Configuration & Connection Strings
└── Program.cs              # Application entry point & DI container setup
```

---

## 🛠️ Database Setup & Configuration

### 1. Prerequisite
Ensure you have a running PostgreSQL instance and a valid Connection String specified in your `appsettings.json`:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Host=localhost;Database=TaskDb;Username=postgres;Password=your_secure_password"
  }
}
```

### 2. Running Migrations
To generate and apply the database schema, run the following commands in the Package Manager Console or Terminal:

```bash
# Add a new migration tracking changes
dotnet ef migrations add InitialCreate

# Apply migrations directly to your PostgreSQL database
dotnet ef database update
```

---

## 🚀 Getting Started

1. Clone this repository locally.
2. Navigate to the project root directory.
3. Run the application using the .NET CLI:

```bash
dotnet restore
dotnet run
```

4. Once started, navigate to `http://localhost:5000/swagger` (or the port specified in your console) to explore and test the endpoints interactively via **Swagger UI**.

---

## ✉️ Contact & Feedback

* **Author:** Lusine Kazaryan  
* **GitHub:** [@Lucky6](https://github.com/Lucky6)  
* **Email:** Luckykazaryan16@gmail.com
