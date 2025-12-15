# 🌸 Projeto Hanami Backend — API de Análise de Dados

Este projeto é parte integrante da iniciativa Recode PRO e tem como objetivo o desenvolvimento de uma **API web** em **C#** usando **ASP.NET Web API**, voltada à análise e visualização de dados.

---

## 📦 Tecnologias Utilizadas

- **Linguagem:** C#
- **Framework:** .NET / ASP.NET MVC / ASP.NET Web API
- **Banco de Dados:** SQL Server
- **IDE recomendada:** Visual Studio Code
- **Controle de Versão:** Git & GitHub

---

## ⚙️ Setup do Projeto

### ✅ Pré-requisitos

Antes de iniciar, verifique se você tem instalado:

- [.NET SDK](https://dotnet.microsoft.com/download) (versão mais recente)
- [SQL Server](https://www.microsoft.com/pt-br/sql-server/sql-server-downloads)
- [Visual Studio Code](https://code.visualstudio.com/)
- [Git](https://git-scm.com/)

### 🚀 Instalação

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/Flimars/hanami-backend-mvc.git
   cd seu-repositorio
   ```

2. **Restaure as dependências do projeto:**

   ```bash
   dotnet restore
   ```

3. **Configure o banco de dados:**

   - Crie um banco de dados no SQL Server.
   - Atualize a string de conexão no arquivo `appsettings.json` conforme necessário.

   ```json
   "ConnectionStrings": {
     "DefaultConnection": "Server=localhost;Database=HanamiDB;Trusted_Connection=True;"
   }
   ```

4. **Rode as migrações (se aplicável):**

   ```bash
   dotnet ef database update
   ```

5. **Execute o projeto:**

   ```bash
   dotnet run
   ```

---

## 🧱 Estrutura de Pastas

```plaintext
.
├── Controllers
├── Models
├── Data
├── Services
├── DTOs
├── Migrations
├── Hanami.API.csproj
└── appsettings.json
```

---

## 📌 Funcionalidades (em desenvolvimento)

- [ ] Cadastro e autenticação de usuários
- [ ] Upload e análise de dados
- [ ] Geração de relatórios
- [ ] API RESTful com endpoints documentados
- [ ] Integração com frontend (futuro)

---

## 📖 Como Contribuir

1. Faça um fork do projeto
2. Crie uma branch: `git checkout -b feature/nome-da-sua-feature`
3. Commit suas mudanças: `git commit -m 'Adiciona nova funcionalidade'`
4. Push para a branch: `git push origin feature/nome-da-sua-feature`
5. Abra um Pull Request

---

## 🧑‍💻 Desenvolvido por

- Flávio Lima - Desenvolvedor Júnior
- Mentoria e suporte: Equipe Recode PRO, PO, Scrum Master e Tech Leader

---

## 📄 Licença

Este projeto está licenciado sob a [MIT License](LICENSE).
