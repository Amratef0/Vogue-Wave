# 👗 Vogue Wave

![.NET](https://img.shields.io/badge/.NET-9.0-512BD4?logo=dotnet)
![EF Core](https://img.shields.io/badge/EF%20Core-9-512BD4)
![SQL Server](https://img.shields.io/badge/SQL%20Server-LocalDB%20%2F%20Express-CC2927?logo=microsoftsqlserver&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5-7952B3?logo=bootstrap&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)

A full-featured e-commerce web application for a fashion store, built with **ASP.NET Core MVC (.NET 9)**. Customers browse products, manage a cart, and place orders, while admins manage the catalog and monitor orders. The project follows the **Repository & Interface design patterns** with Dependency Injection for a clean, maintainable architecture.

---

## 📌 Table of Contents

- [Tech Stack](#-tech-stack)
- [Features](#-features)
- [Architecture](#️-architecture)
- [Project Structure](#-project-structure)
- [Getting Started](#️-getting-started)
- [Roadmap](#️-roadmap)
- [Contributing](#-contributing)

---

## 🚀 Tech Stack

| Technology | Purpose |
|---|---|
| [ASP.NET Core MVC](https://learn.microsoft.com/en-us/aspnet/core/mvc/) (.NET 9) | Web framework |
| [Entity Framework Core](https://learn.microsoft.com/en-us/ef/core/) v9 (Code First) | ORM & database access |
| [SQL Server](https://www.microsoft.com/en-us/sql-server) (LocalDB / Express) | Relational database |
| [ASP.NET Core Identity](https://learn.microsoft.com/en-us/aspnet/core/security/authentication/identity) | Authentication & authorization |
| [MailKit](https://github.com/jstedfast/MailKit) | Email sending |
| C# / Razor Views | Backend logic & HTML templating |
| HTML, CSS, JavaScript, Bootstrap 5 | Responsive frontend UI |

---

## 🎯 Features

### 🛍️ Customer
- Browse products and filter by category
- Add products to a session-based shopping cart
- Place orders and track order status after checkout
- Register, log in, and manage the profile (ASP.NET Core Identity)
- Receive order confirmation emails (MailKit)
- Contact page and blog section

### 🛠️ Admin
- Manage product listings (create, edit, delete)
- Manage categories and users
- View and manage customer orders
- Role-based access control: only authenticated users can perform actions, and admin features are restricted to the Admin role

### 🧪 Quality
- Form validation and error handling
- Responsive, mobile-friendly layout

---

## 🏗️ Architecture

The project follows the **Repository Pattern** with interfaces to decouple data access from the controllers, and services are registered through ASP.NET Core's built-in dependency injection in `Program.cs`.

```
Controller → Interface → Repository → DbContext (EF Core) → SQL Server
```

| Principle | How it is applied |
|---|---|
| **MVC** | Clear separation between models, views, and controllers |
| **Repository & Interfaces** | `IProductRepository`, `IOrderRepository`, and others hide EF Core from the controllers |
| **Dependency Injection** | Interfaces are bound to implementations in `Program.cs` |
| **Separation of Concerns** | Controllers, ViewModels, interfaces, and repositories each have one job |
| **Code First** | The database schema is generated from the models with EF Core migrations |

This makes the codebase easier to test, maintain, and extend.

---

## 📁 Project Structure

```
Vogue-Wave/
├── Controllers/         # MVC controllers (Products, Cart, Orders, Admin, ...)
├── Models/              # Entity models (Product, Order, ApplicationUser, ...)
├── Views/               # Razor view templates
├── Interface/           # Repository interfaces (IProductRepository, IOrderRepository, ...)
├── Repository/          # Concrete repository implementations
├── Migrations/          # EF Core database migrations
├── wwwroot/             # Static files (CSS, JS, images)
├── Properties/          # Launch settings
├── Program.cs           # App entry point & service registration
├── appsettings.json     # App configuration & connection strings
└── Online_Store.csproj  # Project file & NuGet packages
```

---

## ⚙️ Getting Started

### Prerequisites

- **Visual Studio 2022** or later (or any editor with the .NET CLI)
- **.NET 9 SDK** — [Download here](https://dotnet.microsoft.com/download/dotnet/9.0)
- **SQL Server LocalDB** or **SQL Server Express**

### 1. Clone and restore

```bash
git clone https://github.com/Amratef0/Vogue-Wave.git
cd Vogue-Wave
dotnet restore
```

### 2. Configure the app

Update `appsettings.json` with your connection string and email settings:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=VogueWaveDb;Trusted_Connection=True;"
  },
  "MailSettings": {
    "Host": "smtp.gmail.com",
    "Port": 587,
    "SenderEmail": "your_email@gmail.com",
    "SenderPassword": "your_app_password",
    "SenderName": "Vogue Wave"
  }
}
```

> 🔒 **Keep secrets out of Git.** For Gmail, use an [App Password](https://support.google.com/accounts/answer/185833), and store it with [user secrets](https://learn.microsoft.com/en-us/aspnet/core/security/app-secrets) instead of committing it:
>
> ```bash
> dotnet user-secrets set "MailSettings:SenderPassword" "your_app_password"
> ```

### 3. Create the database

In **Package Manager Console** (Visual Studio):

```powershell
Update-Database
```

Or with the .NET CLI:

```bash
dotnet ef database update
```

### 4. Run the app

```bash
dotnet run
```

Or press **F5** in Visual Studio. The app is available at `https://localhost:5001`.

---

## 🗺️ Roadmap

- [x] Product browsing and cart
- [x] Order placement and tracking
- [x] Email notifications
- [ ] Advanced product search
- [ ] User reviews and ratings
- [ ] Payment gateway integration

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a new branch: `git checkout -b feature/your-feature`
3. Commit your changes with clear messages
4. Submit a pull request

---

## 📜 License

This project is open source under the **MIT License**.

---

## 👤 Author

**Amr Atef** — [@Amratef0](https://github.com/Amratef0)
