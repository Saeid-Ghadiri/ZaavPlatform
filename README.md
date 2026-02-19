# Zaavosh Platform - System Architecture Document

**Solution Name:** ZaavoshPlatform

## Projects
- ZaavApp.Api
- ZaavApp.Portal (Vue/Nuxt)
- ZaavApp.Admin (Blazor or MVC)

---

## Table of Contents

* [Introduction](#introduction)
* [Technology Stack](#technology-stack)
* [Solution Structure](#solution-structure)
* [Modules](#modules)
* [Architecture](#architecture)
* [Setup & Installation](#setup--installation)
* [Running the Project](#running-the-project)
* [Testing](#testing)
* [Contributing](#contributing)
* [License](#license)

---

## Introduction

Zaavosh Platform یک پلتفرم جامع است که شامل:

* فروشگاه اینترنتی چندفروشنده (Marketplace)
* مدیریت محتوا (CMS)
* ماژول‌های سازمانی: HR، مالی، زنجیره تامین، انبار
* قابلیت‌های پیشرفته مانند جستجو، پیشنهاددهنده محصول، سیستم چندزبانه، و تقویم شمسی

---

## Technology Stack

**Backend:**

* ASP.NET Core 10 LTS
* C#
* Entity Framework Core
* Microsoft Identity + JWT
* Serilog + MongoDB
* Redis Cache

**Frontend:**

* **Admin:** Blazor WebAssembly یا ASP.NET Core MVC + Razor Pages
* **Shop (Client):** Vue / Nuxt
* Bootstrap 5.3 + RTL / LTR
* HTML / CSS / JS

**Architecture:**

* Clean Architecture
* DDD Pragmatic
* Repository & Unit of Work
* Modular / Layered

---

## Solution Structure

```
ZaavoshPlatform.sln
│
├── src/
│   ├── ZaavApp.Domain/
│   ├── ZaavApp.Application/
│   ├── ZaavApp.Infrastructure/
│   ├── ZaavApp.Admin/
│   └── ZaavApp.Portal/
│
└── tests/
    ├── UnitTests/
    ├── IntegrationTests/
    └── FunctionalTests/
```

---

## Modules

**Core Modules:**

* User Management
* Role & Permission Management
* CMS (Pages, Posts, Categories)
* Settings

**Business Modules:**

* Shop / Marketplace (Multi-Vendor Ready)
* HR System
* Inventory & Supply Chain
* Finance

---

## Architecture

* Domain Layer: Entities, ValueObjects, Events, Domain Services
* Application Layer: Services, DTOs, Validators, Repository Interfaces, UnitOfWork
* Infrastructure Layer: Repository Implementations, EF DbContext, Identity, Logging, Caching, Messaging
* Presentation Layer: Admin (Blazor/MVC), Shop Client (Vue/Nuxt)

**Multi-Vendor:** VendorId روی تمام Product/Order/Cart/Payment اعمال شده و Transactionها از طریق UnitOfWork مدیریت می‌شوند.

**Large Scale Ready:** طراحی ماژولی و Transaction-safe برای توسعه فروشگاه‌های بزرگ و چندفروشنده

---

## Setup & Installation

1. Clone the repository:

```bash
git clone https://github.com/YourUserName/ZaavoshPlatform.git
```

2. Restore packages:

```bash
dotnet restore
```

3. Apply Migrations:

```bash
cd src/ZaavApp.Infrastructure
dotnet ef database update
```

4. Configure `appsettings.json` for DB, Redis, and JWT.

---

## Running the Project

* Backend API:

```bash
cd src/ZaavApp.Api
dotnet run
```

* Admin Panel (Blazor / MVC):

```bash
cd src/ZaavApp.Admin
dotnet run
```

* Shop Portal (Vue / Nuxt):

```bash
cd src/ZaavApp.Portal
npm install
npm run dev
```

---

## Testing

* Unit Tests:

```bash
dotnet test tests/UnitTests
```

* Integration Tests:

```bash
dotnet test tests/IntegrationTests
```

* Functional Tests:

```bash
dotnet test tests/FunctionalTests
```

---

## Contributing

لطفاً قبل از ایجاد Pull Request، مطمئن شوید کد تست شده و مطابق **Clean Architecture** توسعه داده شده است.

---

## License

این پروژه تحت [MIT License](LICENSE) قرار دارد.
