<div align="center">

# 🛍️ SmartPOS
### Enterprise Point of Sale & Retail Management System

[![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=nextdotjs&logoColor=white)](https://nextjs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![.NET](https://img.shields.io/badge/.NET-512BD4?style=flat&logo=dotnet&logoColor=white)](https://dotnet.microsoft.com)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat&logo=tailwindcss&logoColor=white)](https://tailwindcss.com)


**Developed by Syeda Subhana Wasim — Full Stack Developer (2025)**

[Features](#-features) • [Architecture](#-architecture) • [Tech Stack](#-tech-stack) • [Setup](#-getting-started) • [Roles](#-role-based-access)

</div>

---

## 📖 Overview

**SmartPOS** is a production-ready, enterprise-grade Point of Sale and Retail Management System designed for multi-store operations with seamless **FBR (Federal Board of Revenue, Pakistan)** integration. Built on **Next.js 14** (App Router) with a robust **.NET backend**, it delivers real-time inventory tracking, comprehensive sales analytics, automated tax compliance, and role-based workflows for Admins, Managers, and Cashiers.

The system streamlines retail operations from checkout to compliance — featuring barcode scanning, multi-payment processing, customer management, purchase entry, automated invoice generation, audit logging, and business intelligence dashboards.

---

## ✨ Features

### 🔐 Role-Based Authentication & Access Control
- JWT-based authentication with secure token management
- Role detection on login with automatic dashboard routing (`/dashboard/admin`, `/dashboard/manager`, `/dashboard/cashier`)
- Protected routes with server-side and client-side session validation
- Three distinct user roles: **Admin**, **Manager**, **Cashier**
- Granular permission system with feature-level access control

### 🛡️ Admin Dashboard
- **Multi-Store Management**: Monitor and manage 24+ store locations with device status tracking
- **User & Role Management**: Create, update, and assign roles with fine-grained permissions
- **System Analytics**: Real-time metrics for stores, online devices, FBR API health, and audit alerts
- **FBR Compliance Monitoring**: Live sync status with Federal Board of Revenue API
- **Invoice Oversight**: View, manage, and export all system invoices
- **Audit Log Access**: Immutable compliance logs with timestamp and user tracking
- **Sales Report Export**: Download comprehensive sales data in PDF/Excel format
- **Product Registration**: Add new products with barcode, pricing, and stock initialization

### 👨‍💼 Manager Dashboard
- **Sales Analytics**: Daily and monthly revenue tracking with trend analysis (PKR-based)
- **Tax Reporting**: Automated 18% tax calculation with FBR submission tracking
- **Purchase Entry**: Record supplier purchases with stock auto-update
- **Invoice Management**: Review and manage store-level transactions
- **Data Mining**: Advanced analytics with predictive insights and pattern detection
- **Failed Invoice Alerts**: Monitor and resolve FBR submission failures
- **Inventory Oversight**: Low-stock alerts and reorder recommendations
- **Performance Metrics**: Store-wise sales comparison and KPI dashboards

### 🧑‍💻 Cashier Dashboard (Point of Sale)
- **Real-Time POS Interface**: Fast, intuitive checkout with keyboard shortcuts
- **Barcode Scanner Integration**: Hardware barcode scanner support with auto-add to cart
- **Product Search**: Quick lookup by name, barcode, or product ID with auto-complete
- **Shopping Cart Management**: Add, update, remove items with live stock validation
- **Customer Lookup**: Phone-based customer search with purchase history
- **New Customer Registration**: Quick customer onboarding with name, phone, and CNIC
- **Multi-Payment Processing**: Support for Cash, Card, and QR payments in a single transaction
- **Split Payment**: Partial payments with running balance calculation
- **Discount Application**: Percentage-based discounts with real-time total recalculation
- **Tax Calculation**: Automatic 18% sales tax with breakdown display
- **Invoice Generation**: Instant PDF invoice creation with QR code for FBR verification
- **Stock Alerts**: Real-time out-of-stock and low-stock warnings during checkout

### 📦 Inventory Management
- **Real-Time Stock Tracking**: Live inventory levels across all stores
- **Barcode System**: Unique barcode assignment for every product
- **Stock Alerts**: Configurable low-stock thresholds (default: 10 units)
- **Automatic Stock Updates**: Real-time deduction on sales, addition on purchases
- **Product Categories**: Organized product hierarchy with unit management
- **Multi-Store Inventory**: Separate stock levels per store location
- **Stock Transfer**: Inter-store inventory movement tracking

### 💳 Payment & Invoicing
- **Multi-Payment Methods**: Cash, Card (debit/credit), and QR code payments
- **Split Transactions**: Accept multiple payment methods in a single sale
- **Payment Reference Tracking**: Card transaction IDs and QR payment references
- **Auto-Invoice Generation**: Instant PDF invoice with company branding
- **FBR Invoice Integration**: Automated submission to Pakistan's Federal Board of Revenue
- **Invoice Download**: Direct PDF download with customer and tax details
- **Payment History**: Complete transaction audit trail

### 👥 Customer Management
- **Customer Database**: Centralized customer records with purchase history
- **Phone-Based Lookup**: Quick customer search by mobile number
- **CNIC Integration**: National ID card linkage for compliance
- **Recent Customer Cache**: Fast access to frequent customers
- **Customer Creation**: In-POS customer registration without workflow interruption
- **Purchase History**: View customer transaction timeline

### 📊 Business Intelligence & Reporting
- **Sales Dashboards**: Real-time revenue tracking with period comparisons
- **Trend Analysis**: Daily, weekly, and monthly sales patterns
- **Tax Reports**: Automated GST/sales tax summaries for FBR
- **Audit Logs**: Immutable system activity logs for compliance
- **Export Capabilities**: Download reports in PDF and Excel formats
- **Failed Transaction Monitoring**: Track and resolve FBR submission errors
- **Data Mining Module**: Predictive analytics for demand forecasting

### 🇵🇰 FBR (Federal Board of Revenue) Integration
- **Automated Tax Compliance**: Real-time invoice submission to FBR portal
- **Live Sync Status**: Monitor connection health with last sync timestamp
- **Error Handling**: Automatic retry for failed submissions with alert system
- **Invoice Verification**: QR code generation for customer tax verification
- **Audit Trail**: Complete FBR submission history for government inspections
- **Tax Calculation**: Automatic 18% sales tax with proper categorization

### 🔒 Security & Audit
- **JWT Authentication**: Secure token-based session management
- **Role-Based Access Control (RBAC)**: Feature-level permission enforcement
- **Audit Logging**: Immutable logs for all critical operations
- **Session Management**: Automatic logout on token expiration
- **401 Handling**: Graceful authentication error handling with redirect
- **Protected API Endpoints**: Authorization checks on every backend request

---

## Screens 
[SmartPOS Visuals.pdf](https://github.com/user-attachments/files/27490556/SmartPOS.Visuals.pdf)




## 🏗️ Architecture

```
SmartPOS/
│
├── Frontend (Next.js 14 App Router)
│   ├── app/
│   │   ├── page.tsx                          # Root: authentication check + role redirect
│   │   ├── layout.tsx                        # Global layout with Geist font
│   │   ├── globals.css                       # Global Tailwind styles
│   │   │
│   │   ├── login/
│   │   │   └── page.tsx                      # JWT login with role detection
│   │   ├── forgot-password/
│   │   │   └── page.tsx                      # Password reset request
│   │   ├── reset-password/
│   │   │   └── page.tsx                      # Password reset confirmation
│   │   │
│   │   ├── dashboard/
│   │   │   ├── admin/
│   │   │   │   ├── page.tsx                  # Admin dashboard (stores, devices, FBR)
│   │   │   │   ├── users/page.tsx            # User management with role assignment
│   │   │   │   ├── invoices/page.tsx         # All invoices across stores
│   │   │   │   ├── products/
│   │   │   │   │   └── register/page.tsx     # Product registration form
│   │   │   │   ├── reports/page.tsx          # Sales & tax reports
│   │   │   │   ├── roles/page.tsx            # Role & permission management
│   │   │   │   └── audit/page.tsx            # Immutable audit logs
│   │   │   │
│   │   │   ├── manager/
│   │   │   │   ├── page.tsx                  # Manager dashboard (sales, tax, alerts)
│   │   │   │   ├── invoices/page.tsx         # Store-level invoice view
│   │   │   │   ├── purchases/page.tsx        # Purchase entry form
│   │   │   │   └── data-mining/page.tsx      # Analytics & predictions
│   │   │   │
│   │   │   └── cashier/
│   │   │       ├── page.tsx                  # Cashier dashboard (quick stats)
│   │   │       ├── pos/page.tsx              # Point of Sale interface
│   │   │       └── invoices/page.tsx         # Invoice history
│   │   │
│   │   └── api/                              # Next.js API routes (if any)
│   │
│   ├── components/
│   │   ├── LoginForm.tsx                     # Authentication form component
│   │   ├── Navbar.tsx                        # Role-based navigation bar
│   │   ├── ProtectedLayout.tsx               # Route protection wrapper
│   │   ├── admin/
│   │   │   └── AddUserModal.tsx              # User creation modal
│   │   └── ui/                               # shadcn/ui components
│   │       ├── button.tsx
│   │       ├── card.tsx
│   │       ├── dialog.tsx
│   │       ├── input.tsx
│   │       ├── select.tsx
│   │       ├── table.tsx
│   │       ├── InvoiceForm.tsx               # Invoice creation form
│   │       └── InvoiceList.tsx               # Invoice table component
│   │
│   ├── lib/
│   │   ├── api.ts                            # Axios instance with interceptors
│   │   ├── auth.ts                           # JWT token management
│   │   ├── report.ts                         # Report generation utilities
│   │   └── utils.ts                          # Helper functions
│   │
│   └── types/
│       └── auth.d.ts                         # TypeScript type definitions
│
└── Backend (.NET Core API)
    ├── Controllers/
    │   ├── AuthController.cs                 # Login, register, token refresh
    │   ├── InventoryController.cs            # Product & stock management
    │   ├── POSController.cs                  # Sales transaction processing
    │   ├── InvoiceController.cs              # Invoice CRUD & PDF generation
    │   ├── CustomerController.cs             # Customer management
    │   ├── PurchaseController.cs             # Supplier purchase entry
    │   ├── ReportController.cs               # Sales & tax reporting
    │   └── AuditController.cs                # Audit log access
    │
    ├── Services/
    │   ├── FBRService.cs                     # FBR API integration
    │   ├── InvoiceService.cs                 # PDF generation
    │   ├── AuthService.cs                    # JWT token generation
    │   └── StockService.cs                   # Inventory calculations
    │
    ├── Models/
    │   ├── User.cs                           # User entity with roles
    │   ├── Product.cs                        # Product & inventory
    │   ├── Sale.cs                           # Sales transaction
    │   ├── Invoice.cs                        # Invoice entity
    │   ├── Customer.cs                       # Customer records
    │   └── AuditLog.cs                       # Audit trail
    │
    └── Data/
        └── ApplicationDbContext.cs           # Entity Framework DB context
```

---

## 🛠️ Tech Stack

### Frontend
| Layer | Technology |
|-------|-----------|
| **Framework** | Next.js 14 (App Router) |
| **Language** | TypeScript |
| **Styling** | Tailwind CSS + shadcn/ui |
| **State Management** | React Hooks (useState, useEffect) |
| **HTTP Client** | Axios with interceptors |
| **Forms** | shadcn/ui Form components |
| **Icons** | Lucide React |
| **Fonts** | Geist Sans & Geist Mono |

### Backend
| Layer | Technology |
|-------|-----------|
| **Framework** | .NET Core / ASP.NET Core |
| **Language** | C# |
| **Database** | SQL Server / PostgreSQL |
| **Authentication** | JWT (JSON Web Tokens) |
| **ORM** | Entity Framework Core |
| **PDF Generation** | iTextSharp / QuestPDF |
| **FBR Integration** | Custom API client |

### Infrastructure
| Component | Technology |
|-----------|-----------|
| **Version Control** | Git + GitHub |
| **API Communication** | REST (https://localhost:61510/api) |
| **Security** | Bearer Token Authentication |
| **Session Management** | localStorage + JWT |

---

## 🔐 Role-Based Access

| Feature | Admin | Manager | Cashier |
|---------|:-----:|:-------:|:-------:|
| Multi-store management | ✅ | ❌ | ❌ |
| User & role management | ✅ | ❌ | ❌ |
| FBR API monitoring | ✅ | ✅ | ❌ |
| System audit logs | ✅ | ❌ | ❌ |
| Product registration | ✅ | ❌ | ❌ |
| View all invoices | ✅ | ✅ (store-level) | ✅ (own sales) |
| Sales reports | ✅ | ✅ | ❌ |
| Purchase entry | ❌ | ✅ | ❌ |
| Data mining & analytics | ❌ | ✅ | ❌ |
| Point of Sale (POS) | ❌ | ❌ | ✅ |
| Customer management | ✅ | ✅ | ✅ (create only) |
| Barcode scanning | ❌ | ❌ | ✅ |
| Multi-payment processing | ❌ | ❌ | ✅ |
| Invoice generation | ✅ | ✅ | ✅ |
| Inventory view | ✅ | ✅ | ✅ (read-only) |
| Stock management | ✅ | ✅ | ❌ |

---

## 🚀 Getting Started

### Prerequisites
- **Node.js** `>=18.0.0`
- **npm** or **yarn**
- **.NET 6.0 SDK** or higher
- **SQL Server** or **PostgreSQL** database
- **Visual Studio** or **VS Code** (for backend development)

### Frontend Installation

```bash
# 1. Clone the repository
git clone https://github.com/subhana-web/smartpos.git
cd smartpos

# 2. Install frontend dependencies
npm install

# 3. Set up environment variables
cp .env.example .env.local
# Fill in your values (see Environment Variables section)

# 4. Run the development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### Backend Setup

```bash
# 1. Navigate to backend directory
cd backend/SmartPOS.API

# 2. Restore NuGet packages
dotnet restore

# 3. Update database connection string in appsettings.json

# 4. Run database migrations
dotnet ef database update

# 5. Start the API server
dotnet run
```

The backend API will run on `https://localhost:61510`.

### Environment Variables

Create a `.env.local` file in the frontend root:

```env
# API Configuration
NEXT_PUBLIC_API_URL=https://localhost:61510/api

# Authentication
NEXT_PUBLIC_JWT_SECRET=your-jwt-secret-key

# Feature Flags
NEXT_PUBLIC_ENABLE_FBR=true
NEXT_PUBLIC_ENABLE_BARCODE_SCANNER=true

# Company Details
NEXT_PUBLIC_COMPANY_NAME=Your Store Name
NEXT_PUBLIC_TAX_RATE=0.18
```

### Backend Configuration (`appsettings.json`)

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost;Database=SmartPOS;Trusted_Connection=true;"
  },
  "JwtSettings": {
    "SecretKey": "your-super-secret-key-min-32-chars",
    "Issuer": "SmartPOS",
    "Audience": "SmartPOS-Clients",
    "ExpiryMinutes": 1440
  },
  "FBRSettings": {
    "ApiUrl": "https://fbr.gov.pk/api/v1",
    "ApiKey": "your-fbr-api-key",
    "TaxRate": 0.18
  }
}
```

---

## 📡 API Reference

### Authentication
| Endpoint | Method | Description | Access |
|----------|--------|-------------|--------|
| `/api/auth/login` | POST | Login with email/password, returns JWT | Public |
| `/api/auth/register` | POST | Register new user (Admin only) | Admin |
| `/api/auth/refresh` | POST | Refresh expired JWT token | Authenticated |
| `/api/auth/forgot-password` | POST | Request password reset email | Public |
| `/api/auth/reset-password` | POST | Reset password with token | Public |

### Inventory
| Endpoint | Method | Description | Access |
|----------|--------|-------------|--------|
| `/api/inventory` | GET | Get all products with stock levels | All roles |
| `/api/inventory/low-stock` | GET | Get products below threshold | Manager+ |
| `/api/products` | POST | Create new product | Admin |
| `/api/products/{id}` | PUT | Update product details | Admin |
| `/api/products/{id}` | DELETE | Delete product | Admin |

### Point of Sale
| Endpoint | Method | Description | Access |
|----------|--------|-------------|--------|
| `/api/pos/sale` | POST | Process POS transaction | Cashier+ |
| `/api/pos/validate-stock` | POST | Check product availability | Cashier+ |

### Invoices
| Endpoint | Method | Description | Access |
|----------|--------|-------------|--------|
| `/api/invoices` | GET | Get all invoices (filtered by role) | All roles |
| `/api/invoices/{id}` | GET | Get invoice details | All roles |
| `/api/invoices/{id}/download` | GET | Download PDF invoice | All roles |
| `/api/invoices/fbr-status` | GET | Check FBR submission status | Manager+ |

### Customers
| Endpoint | Method | Description | Access |
|----------|--------|-------------|--------|
| `/api/customers/by-phone/{phone}` | GET | Search customer by phone | Cashier+ |
| `/api/customers` | POST | Create new customer | Cashier+ |
| `/api/customers/{id}` | GET | Get customer details | Manager+ |

### Reports
| Endpoint | Method | Description | Access |
|----------|--------|-------------|--------|
| `/api/reports/sales` | GET | Download sales report (PDF/Excel) | Manager+ |
| `/api/reports/tax` | GET | Download tax summary | Manager+ |
| `/api/reports/audit` | GET | Download audit logs | Admin |

### Purchases
| Endpoint | Method | Description | Access |
|----------|--------|-------------|--------|
| `/api/purchases` | GET | Get all purchase entries | Manager+ |
| `/api/purchases` | POST | Record new purchase | Manager+ |

---

## 🔑 Key Technical Decisions

**Next.js 14 App Router** — Leverages server components, streaming, and nested layouts for optimal performance. Client components are used strategically for interactive features like the POS interface.

**.NET Backend with Entity Framework** — Provides robust type safety, built-in dependency injection, and powerful ORM capabilities for complex retail operations. SQL Server ensures ACID compliance for financial transactions.

**JWT Authentication** — Stateless authentication with role-based claims embedded in tokens. Automatic token refresh prevents session interruptions during active sales.

**Axios Interceptors** — Centralized request/response handling ensures consistent token attachment, error logging, and 401 redirect behavior across the application.

**FBR Integration** — Real-time invoice submission to Pakistan's Federal Board of Revenue ensures tax compliance. Automatic retry mechanism handles network failures, with manual override for critical situations.

**Multi-Payment Architecture** — Flexible payment processing supports partial payments, split transactions, and future payment gateway integrations (Stripe, JazzCash, EasyPaisa).

**Barcode Scanner Support** — Hardware barcode scanner integration via keyboard event listeners enables rapid product entry without mouse interaction — critical for high-volume checkout.

**Audit Logging** — Write-only audit table with timestamp, user ID, action type, and payload ensures compliance with financial regulations and provides forensic investigation capabilities.

---

## 🎯 Use Cases

### Retail Stores
- Grocery stores, pharmacies, and convenience stores
- Apparel and fashion boutiques
- Electronics and mobile shops
- Book and stationery stores

### Multi-Store Chains
- Franchise operations with centralized reporting
- Department stores with multiple branches
- Supermarkets with regional locations

### Compliance-Focused Businesses
- Businesses requiring FBR invoice submission
- Tax-registered retail operations in Pakistan
- Audited retail chains

---

## 🔮 Future Enhancements

- **Mobile App**: React Native POS app for tablet-based checkout
- **Payment Gateway Integration**: JazzCash, EasyPaisa, and bank payment gateways
- **E-Commerce Module**: Online store with inventory sync
- **Advanced Analytics**: Machine learning for demand forecasting
- **Multi-Currency Support**: International sales with exchange rate handling
- **Loyalty Program**: Customer rewards and points management
- **Offline Mode**: Local database sync with online reconciliation
- **E-Invoice QR Code**: Enhanced QR code with full invoice details
- **SMS Notifications**: Customer order confirmations and promotions
- **WhatsApp Integration**: Invoice delivery via WhatsApp Business API

---

## 👩‍💻 About the Developer

Built by **Syeda Subhana Wasim** — Full Stack Developer, BS CS Graduate from Rawalpindi Women University (2025).

Specialized in enterprise web applications with expertise in Next.js, TypeScript, .NET Core, and database design.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/syeda-subhana-wasim-93b6aa26a)
[![Email](https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white)](mailto:subhanasyeda009@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/subhana-web)

---



---

## 🙏 Acknowledgments

- **Federal Board of Revenue (FBR), Pakistan** — For API documentation and compliance guidelines
- **Next.js Team** — For the exceptional App Router and React Server Components
- **shadcn/ui** — For the beautiful and accessible UI component library
- **Vercel** — For Next.js framework and deployment platform

---

## 📞 Support

For issues, questions, or feature requests:
- Open an issue on [GitHub](https://github.com/subhana-web/smartpos/issues)
- Email: subhanasyeda009@gmail.com
- LinkedIn: [Syeda Subhana Wasim](https://linkedin.com/in/syeda-subhana-wasim-93b6aa26a)

---

<div align="center">
  <sub>Built with Next.js 💙 & .NET 💜 | Pakistan 🇵🇰 | 2025</sub>
</div>
