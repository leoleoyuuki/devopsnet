# DevOps Nexus App

Este projeto é um WebApp .NET 8 utilizando a arquitetura MVC com Razor Pages, voltado para o gerenciamento de empresas. Ele permite o cadastro, edição e visualização de dados empresariais, facilitando o controle de informações como nome, setor de atuação, tamanho, localização geográfica, número de funcionários e outras características relevantes.

O aplicativo foi containerizado usando Docker, o que possibilita um ambiente padronizado para execução e facilita a implantação em diferentes plataformas. No caso deste projeto, o deploy está sendo feito na Azure, aproveitando a infraestrutura escalável da nuvem, garantindo que o sistema esteja sempre disponível para os usuários.

## Vídeo Youtube
[Vídeo Demonstração .NET on Azure](https://youtu.be/KPkYR2Zunfo?si=foaHKMt548F2AHdb)

## Tecnologias Utilizadas

- **.NET 8**
  - ASP.NET Core MVC
  - Razor Pages
  - Entity Framework Core
  - Validação de Dados
- **SQL Server** (para desenvolvimento)
- **Docker** (para containerização)
- **Azure** (para deploy)

## Configuração do Projeto

### Pré-requisitos

- .NET SDK 8.0
- Docker
- Conta no Docker Hub
- Conta no Azure

### Passos para Build e Deploy

1. **Clone o repositório:**

```bash
git clone https://github.com/guibk/DEVOPS-TOOLS-E-CLOUD-COMPUTING.git
cd SistemaDeRecomendação
```

2. **Build do projeto com .NET CLI:**

   Execute o comando abaixo para compilar o projeto e gerar o arquivo `.dll`:

```bash
dotnet publish -c Release -o out
```

3. **Criação da Imagem Docker:**

   Com a aplicação publicada, crie a imagem Docker:

```bash
docker build -t harthleyteixeiraa/sistemaderecomendacao:v1 .
```

4. **Envio da Imagem para o Docker Hub:**

   Faça login no Docker Hub e envie a imagem:

```bash
docker login
docker push harthleyteixeiraa/sistemaderecomendacao:v1
```

5. **Deploy no Azure:**

   - Crie um Web App no Azure, selecionando a opção **Docker Container**.
   - Na aba **Docker**, configure para usar a imagem `harthleyteixeiraa/sistemaderecomendacao:v1` do Docker Hub.

6. **Verificar Log Stream:**

   Após o deploy, você pode monitorar o status do aplicativo pelo Log Stream no portal da Azure.

## Contribuição

Se desejar contribuir com o projeto, siga os passos:

1. Faça um fork do repositório
2. Crie uma nova branch: `git checkout -b minha-feature`
3. Commit suas mudanças: `git commit -m 'Adicionando nova feature'`
4. Faça o push da branch: `git push origin minha-feature`
5. Abra um pull request
