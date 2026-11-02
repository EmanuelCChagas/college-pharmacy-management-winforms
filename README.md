# Pharmacy Management

A Windows desktop project for managing pharmacy customers, products, and checkout. Developed with C#, Windows Forms, and MySQL for **Hands On Work IV** (2021). The application interface is in Portuguese.

## Features in the available source

- Create, list, update, and deactivate customers.
- Product data operations for names, barcodes, prices, and active status.
- Select customers and products for a sale.
- Calculate checkout totals and record payment methods.
- Store sales and individual sale items in the database.

## Technology

| Component | Technology |
| --- | --- |
| Language and interface | C# / Windows Forms |
| Runtime | .NET Framework 4.7.2 |
| Database | MySQL-compatible server |
| Database connector | MySql.Data 8.0.26 |
| IDE | Visual Studio |

## Project status

**The checked-in source is incomplete and cannot be rebuilt as-is.** The project file references missing files, including `Program.cs`, `Produtos_Form.cs`, `Relat_Form.cs`, `Sobre_Form.cs`, and files under `Properties/` and `Resources/`. Those files must be recovered before a source build can succeed.

The repository includes historical build output under `bin/Debug/`, but that does not replace the missing source. Payment forms perform local input checks rather than processing real transactions.

## Setup and recovery

1. Clone the repository:

   ```bash
   git clone https://github.com/EmanuelCChagas/pharmacy-management-winforms.git
   ```

2. On Windows, install Visual Studio with .NET desktop development support and the .NET Framework 4.7.2 targeting pack.
3. Open [Hands On Work IV_2.sln](Hands%20On%20Work%20IV_2.sln) and recover the missing files referenced by the project.
4. Resolve the `MySql.Data` assembly reference using version 8.0.26. No NuGet package restore configuration is included.
5. Create a local database named `farmacia_db` and import [farmacia_db (1).sql](farmacia_db%20%281%29.sql). The dump defines `clientes`, `produtos`, `vendas`, and `vendas_info` and includes existing records; use a separate development database.
6. Search the C# source for `datasource=` and update the embedded connection settings for your local database.
7. After restoring the missing source and dependencies, build and run from Visual Studio.

The original academic setup used XAMPP for the database environment.

## Source guide

- [Hands On Work IV](Hands%20On%20Work%20IV): Windows Forms project and available application source.
- `Clientes_Form.cs` and `Classe_Clientes.cs`: customer interface and database operations.
- `Classe_Produtos.cs`: product database operations.
- `Caixa_Form.cs` and `Classe_Caixa.cs`: checkout interface and sale persistence.
- `Adicionar_Clientes_Caixa.cs` and `Adicionar_Produtos_Caixa.cs`: checkout selection dialogs.
- [Database dump](farmacia_db%20%281%29.sql): database structure and sample records from the original project.
