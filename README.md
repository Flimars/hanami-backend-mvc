# **Hanami Backend – ASP.NET Core MVC**

Projeto backend desenvolvido em **C#** utilizando **ASP.NET Core MVC**, como parte da Sprint 1 do Programa Recode PRO.
O objetivo desta fase é configurar o ambiente de desenvolvimento, estruturar o projeto no padrão MVC e estabelecer a base necessária para as próximas entregas.

---

## **Índice**

1. Visão Geral
2. Tecnologias Utilizadas
3. Arquitetura do Projeto (MVC)
4. Estrutura de Pastas
5. Requisitos
6. Instalação e Configuração
7. Executando o Projeto
8. Configuração do Banco de Dados
9. Testes (opcional nesta Sprint)
10. Kanban do Projeto
11. Padrões de Commits
12. Licença

---

# **1. Visão Geral**

Este repositório corresponde ao backend do Projeto Hanami, iniciado com a arquitetura **ASP.NET Core MVC**, ideal para aplicações web escaláveis e organizadas.
Na **Sprint 1**, são entregues:

* Criação da solução base em MVC
* Estruturação inicial do projeto
* Configuração de repositório e versionamento
* Documentação inicial
* Preparação do ambiente para migrações e persistência de dados

Este documento orienta qualquer desenvolvedor a instalar, executar e compreender o funcionamento inicial da aplicação.

---

# **2. Tecnologias Utilizadas**

* **C# 12 (ou superior)**
* **ASP.NET Core MVC (.NET 8+)**
* **Entity Framework Core**
* **SQL Server**
* **Razor Pages / Views**
* Git + GitHub
* VS Code / Visual Studio

---

# **3. Arquitetura do Projeto (MVC)**

A aplicação segue o padrão **Model–View–Controller**, uma arquitetura amplamente utilizada em aplicações web.

* **Models**
  Representam os dados da aplicação e regras de negócio.

* **Views**
  São responsáveis pela apresentação visual ao usuário (HTML + Razor).

* **Controllers**
  Recebem as requisições, processam a lógica e encaminham dados para as Views.

Fluxo simplificado:

```bash
Usuário → Controller → Model → View → Usuário
```

Diagrama lógico:

```bash
┌───────────────┐      ┌────────────┐      ┌─────────────┐
│    Controller  │ <--> │   Model    │ ---> │     View     │
└───────────────┘      └────────────┘      └─────────────┘
```

A Web API poderá ser adicionada futuramente dentro do mesmo projeto ou em projeto separado.

---

# **4. Estrutura de Pastas**

```bash
/Hanami.Mvc
│
├── Controllers/
│   └── HomeController.cs
│
├── Models/
│   └── ExemploModel.cs  (placeholder)
│
├── Views/
│   ├── Home/
│   │   └── Index.cshtml
│   └── Shared/
│       └── _Layout.cshtml
│
├── Data/
│   └── ApplicationDbContext.cs  (configuração para EF Core)
│
├── wwwroot/
│   ├── css/
│   ├── js/
│   └── img/
│
├── appsettings.json
├── Program.cs
├── Hanami.Mvc.csproj
│
├── docs/
│   └── arquitetura.md
│
└── README.md
```

---

# **5. Requisitos**

Antes de iniciar, instale:

* [.NET SDK 8+](https://dotnet.microsoft.com/download)
* SQL Server (LocalDB, Developer, Docker ou remoto)
* Git
* Editor de código:

  * Visual Studio Code
  * Visual Studio
  * JetBrains Rider

---

# **6. Repositório do projeto no GitHub

[Link GitHub](https://github.com/Flimars/hanami-backend-mvc)

### Instalação e Configuração**


### **1. Clonar o repositório**

```bash
git clone https://github.com/Flimars/hanami-backend-mvc.git
cd hanami-backend-mvc
```

### **2. Restaurar dependências**

```bash
dotnet restore
```

### **3. Estrutura criada via CLI**

Caso queira recriar o projeto:

```bash
dotnet new mvc -n Hanami.Mvc
```

---

# **7. Executando o Projeto**

Dentro da pasta raiz:

```bash
dotnet run --project Hanami.Mvc
```

A aplicação rodará em:

```
http://localhost:5000
https://localhost:5001
```

---

# **8. Configuração do Banco de Dados**

### **1. Ajustar connection string**

No arquivo `appsettings.json`:

```json
"ConnectionStrings": {
  "DefaultConnection": "Server=SEU_SERVIDOR;Database=HanamiDb;Trusted_Connection=True;TrustServerCertificate=True;"
}
```

### **2. Criar DbContext**

Arquivo `Data/ApplicationDbContext.cs`:

```csharp
using Microsoft.EntityFrameworkCore;

namespace Hanami.Mvc.Data
{
    public class ApplicationDbContext : DbContext
    {
        public ApplicationDbContext(DbContextOptions<ApplicationDbContext> options)
            : base(options)
        {
        }
    }
}
```

### **3. Registrar serviço no Program.cs**

```csharp
builder.Services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(builder.Configuration.GetConnectionString("DefaultConnection")));
```

### **4. Migrations (para próximas sprints)**

```bash
dotnet ef migrations add InitialCreate
dotnet ef database update
```

---

# **9. Testes (Opcional nesta Sprint)**

Caso os testes sejam criados:

```bash
dotnet test
```

---

# **10. Kanban do Projeto**

Organização das tarefas da Sprint no Notion:

**Link para o Kanban:**
[AQUI LINK](https://www.notion.so/Projeto-Hanami-Backend-API-de-An-lise-de-Dados-2c4fac5d0d9a81908ec9e06d3bd2d5ab)

---

# **11. Padrões de Commits (Convenção Recomendada)**

* `feat:` nova funcionalidade
* `fix:` correção de bug
* `docs:` alteração de documentação
* `chore:` mudanças internas sem impacto funcional
* `refactor:` melhoria estrutural sem mudar comportamento
* `style:` ajustes estéticos de código

Exemplo:

```bash
feat: add initial HomeController with Index action
```

---

# **12. Licença**

Projeto criado para fins educacionais como parte do Programa Recode PRO.
Todos os direitos reservados.

---
