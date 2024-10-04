# Observabilidades

Projeto criado para estudo de sistemas de observabilidades em particular grafana, graylog e dynatrace.

## Tecnologias Utilizadas

- Java 21: Versão mais recente do Java, aproveitando as melhorias de desempenho e novos recursos da linguagem.
- Spring Boot: Framework para facilitar o desenvolvimento de aplicações Java com foco em convenção sobre configuração.
- Maven: Gerenciador de dependências e build.

## Requisitos

- Java 21 ou superior
- Maven 3.9.7 ou superior
- Git: https://github.com/ironbats/born-with-observability.git
- Banco de dados: Postgress

## Instalação e Configuração

1. Clonar o Repositório
   Clone o repositório GitLab para sua máquina local:
    ```bash
    git clone https://github.com/ironbats/born-with-observability.git
    ```

2. Navegar para o Diretório do Projeto
    ```bash
    cd nome-do-repositorio
    ```

3. Arquivo de secrets
   Crie um arquivo .env.dev na raiz do projeto e adicione as secrets abaixo

    ```text

    ```

3. Configuração do Banco de Dados
   Subir o arquivo `docker-compose.yml` que esta junto ao projeto.
    ```bash
    docker-compose up -d
    ```

   Certifique-se de que o banco de dados está rodando e rode a aplicação utilizando a variável de ambiente `spring.profiles.active=dev`

4. Executar o Projeto

    ```bash
    mvn spring-boot:run
    ```
   A aplicação estará disponível em http://localhost:8090.

## Estrutura do projeto
```text
/src
  └── /main
        └── /java
              └── com.br.study.monitoring                 # Pacote raiz do projeto
                    └── /grafana.provisioning.datasource  # Configurações da fonte dados do Grafana
                    └── /prometheus                       # Configurações de conexão do Prometheus
        └── /resources
              └── /application.yml                        # Configurações default do Spring Boot
              └── /application-dev.yml                    # Configurações de dev do Spring Boot
  └── /test                                               # Testes unitários e de integração
        └── /java
              └── com.br.study.monitoring                 # Testes organizados por pacote
```

## Padrão de Branch
O projeto segue um padrão de nomenclatura para branches, que facilita a organização e o entendimento do propósito de
cada branch. O formato a ser seguido é:

```text
users/{lastName}/{description}
```

> a descrição deve estar em inglês

### Detalhes:

- lastName: O identificador do desenvolvedor responsável pela criação da branch. Último sobrenome.
- description: Uma breve descrição da finalidade da branch. Use hífens para separar palavras.

## Padrão de Commits
O projeto utiliza o Commitlint para garantir que as mensagens de commit sigam um padrão consistente. A convenção
adotada é baseada no formato Conventional Commits, que facilita o versionamento semântico (semver) e a legibilidade do
histórico do repositório.

### Estrutura da Mensagem de Commit

```text
<type>[scope]: <description>
```

> A descrição breve deve estar em inglês.

#### Tipos de Commits
- feat: Para inclusão de uma nova funcionalidade.
- fix: Para correção de bugs.
- docs: Para mudanças relacionadas à documentação.
- style: Alterações que não afetam o comportamento do código (ex: formatação, espaços em branco, etc.).
- refactor: Alterações no código que não corrigem bugs nem adicionam novas funcionalidades.
- perf: Alterações que melhoram o desempenho.
- test: Inclusão ou alteração de testes.
- build: Mudanças que afetam o sistema de build ou dependências externas (ex: Maven, Gradle).
- ci: Alterações nos arquivos de configuração de CI/CD (ex: .gitlab-ci.yml).
- chore: Atualizações menores, como mudanças de tarefas rotineiras (ex: atualização de bibliotecas).
- revert: Reverter um commit anterior.

#### Exemplo de Mensagem de Commit

```text
feat: add login page
fix: fix null pointer error in method X
docs: update README with setup instructions
```

#### Escopo Opcional

```text
feat(user): implement user creation
fix(auth): fix bug in authentication flow
```

#### Regras Adicionais

A descrição deve ser clara e concisa, com no máximo 72 caracteres.
Não utilizar letra maiúscula na primeira palavra da descrição.
Evitar o uso de ponto final na descrição.

## CI/CD com GitLab
Não adicionado

### Pipeline Padrão

Build: Compilação do projeto.
Test: Execução dos testes unitários.

## Testes
Não iremos focar em testes unitários ou testes de integração inicialmente, apenas no desenvolvimento e
integração com a ferramentas de monitorias.

### Cobertura
Não adicionado

## Executando Testes

Para rodar os testes unitários, utilize o Maven:

```bash
mvn test
```


## Licença
Este projeto está licenciado sob a Licença MIT.