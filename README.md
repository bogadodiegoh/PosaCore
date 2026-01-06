# 💳 PosaCore: Digital Asset Activation System

[![.NET 8](https://img.shields.io/badge/.NET-8.0-512bd4?logo=dotnet)](https://dotnet.microsoft.com/)
[![Angular](https://img.shields.io/badge/Angular-17+-dd0031?logo=angular)](https://angular.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**PosaCore** is a full-stack simulation of a **POSA (Point of Sales Activation)** system. This project demonstrates the secure lifecycle of digital prepaid codes (similar to Nintendo eShop, PlayStation Network, or Xbox cards), from inactive generation to retail activation and final user redemption.

---

## 🚀 The Business Problem
Physical gift cards in retail stores have no value until they are officially scanned at the checkout. This prevents inventory theft and fraud. This system implements the logic required to:
1. **Generate** unique, cryptographically secure codes.
2. **Activate** codes via a "Cashier" interface (simulating the POS scan).
3. **Redeem** codes securely, preventing brute-force attacks and double-spending.

## 🛠️ Tech Stack
- **Backend:** .NET 8 Web API with Entity Framework Core.
- **Frontend:** Angular 17+ with Angular Material.
- **Database:** SQLite (Prototyping) / SQL Server (Production ready).
- **Security:** Rate Limiting, Code Encryption, and State Validation.

## 📋 System Workflow (Lifecycle)
| State | Description | Trigger |
| :--- | :--- | :--- |
| **Inactive** | Code exists in DB but has no monetary value. | Initial Generation. |
| **Active** | Code has been paid for. Ready for redemption. | POS Activation (Cashier). |
| **Redeemed** | Value has been transferred to a user's wallet. | Client Redemption (Console/App). |

## 🏗️ Project Architecture
- `/src/PosaCore.API`: Business logic, code algorithm validation, and database management.
- `/src/PosaCore.Client`: Dual-purpose dashboard (Cashier Mode / User Mode).

## 🔧 Getting Started
1. Clone the repository:
   ```bash
   git clone [https://github.com/bogadodiegoh/PosaCore.git](https://github.com/bogadodiegoh/PosaCore.git)
   ```
2. Run the Backend:
   ```bash
      cd src/PosaCore.API
      dotnet run
   ```
3. Run the Frontend:
   ```bash
   cd src/PosaCore.Client
   npm install
   ng serve
   ```
## 🛣️ Roadmap
- [ ] Random code generation excluding confusing characters (I, O, Z).
- [ ] Implementation of Rate Limiting to prevent brute-force attacks.
- [ ] Real-time activation metrics dashboard.
- [ ] Transaction history and idempotency logic for redemptions.

*Created by [Diego Bogado](https://github.com/bogadodiegoh)*
