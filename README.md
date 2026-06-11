# 👗 Vogue Wave

A full-featured e-commerce web application for a fashion store, built with **ASP.NET Core MVC (.NET 9)**. Users can browse products, manage their cart, and place orders — while admins manage the catalog and monitor orders. The project follows the **Repository & Interface design patterns** for clean, maintainable architecture.

---

## 🚀 Tech Stack

| Technology | Purpose |
|---|---|
| [ASP.NET Core MVC](https://learn.microsoft.com/en-us/aspnet/core/mvc/) (.NET 9) | Web framework |
| [Entity Framework Core](https://learn.microsoft.com/en-us/ef/core/) v9 | ORM & database access |
| [SQL Server](https://www.microsoft.com/en-us/sql-server) (LocalDB / Express) | Relational database |
| [ASP.NET Core Identity](https://learn.microsoft.com/en-us/aspnet/core/security/authentication/identity) | Authentication & authorization |
| [MailKit](https://github.com/jstedfast/MailKit) | Email sending |
| C# / Razor Views | Backend logic & HTML templating |
| HTML, CSS, JavaScript | Frontend UI |

---

## 📁 Project Structure

```
Vogue-Wave/
├── Controllers/         # MVC Controllers (Products, Cart, Orders, Admin...)
├── Models/              # Entity models (Product, Order, ApplicationUser...)
├── Views/               # Razor view templates
├── Interface/           # Repository interfaces (IProductRepository, IOrderRepository...)
├── Repository/          # Concrete repository implementations
├── Migrations/          # EF Core database migrations
├── wwwroot/             # Static files (CSS, JS, images)
├── Properties/          # Launch settings
├── Program.cs           # App entry point & service registration
├── appsettings.json     # App configuration & connection strings
└── Online_Store.csproj  # Project file & NuGet packages
```

---

## ⚙️ Prerequisites

- **Visual Studio 2022** or later
- **.NET 9 SDK** — [Download here](https://dotnet.microsoft.com/download/dotnet/9.0)
- **SQL Server LocalDB** or **SQL Server Express**

---

## 🛠️ Installation

```bash
# 1. Clone the repository
git clone https://github.com/Amratef0/Vogue-Wave.git
cd Vogue-Wave
```

```
# 2. Open the solution in Visual Studio
```

```bash
# 3. Restore NuGet packages (auto-restores on build, or manually)
dotnet restore
```

---

## 🔧 Configuration

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

---

## 🗄️ Database Setup

Run the following in **Package Manager Console** (Visual Studio):

```powershell
Update-Database
```

Or via the .NET CLI:

```bash
dotnet ef database update
```

---

## ▶️ Running the App

```bash
dotnet run
```

Or press **F5** in Visual Studio. The app will be available at `https://localhost:5001`.

---

## 🎯 Features

**Customer**
- Browse and search products by category
- Add products to shopping cart
- Place and track orders
- Receive order confirmation emails via MailKit
- Register / Login with ASP.NET Core Identity

**Admin**
- Manage product listings (Create, Edit, Delete)
- View and manage customer orders
- Role-based access control

---

## 🏗️ Architecture

The project follows the **Repository Pattern** with interfaces to decouple data access from business logic:

```
Controller → Interface → Repository → DbContext (EF Core) → SQL Server
```

This makes the codebase easier to test, maintain, and extend.

---

## 🗺️ Roadmap

- [x] Product browsing and cart
- [x] Order placement
- [x] Email notifications
- [ ] Product search and filtering
- [ ] User reviews and ratings system
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
