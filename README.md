# Monitoramento de Métricas de GC do .NET com Prometheus e Grafana

Este projeto implementa uma stack de monitoramento para aplicações .NET, focada em métricas de Garbage Collector (GC). A stack utiliza Docker Compose para orquestrar os seguintes serviços:

*   **Prometheus**: Coleta as métricas da aplicação.
*   **Grafana**: Visualiza as métricas em um dashboard pré-configurado.
*   **Aplicação .NET**: A aplicação a ser monitorada (simulada no `docker-compose.yml`).

## Estrutura do Projeto

```
/
├── docker-compose.yml
├── grafana-provisining/
│   ├── dashboards/
│   │   ├── dashboard.yml
│   │   └── net-metrics-dashboard.json
│   └── datasources/
│       └── datasource.yml
└── prometheus-config/
    └── prometheus.yml
```

*   `docker-compose.yml`: Define e configura os serviços da stack (Prometheus, Grafana e a aplicação).
*   `grafana-provisining/`: Contém as configurações de provisionamento do Grafana.
    *   `dashboards/`: Armazena as configurações e o JSON do dashboard.
    *   `datasources/`: Define a fonte de dados do Prometheus para o Grafana.
*   `prometheus-config/`: Armazena o arquivo de configuração do Prometheus (`prometheus.yml`), que define os alvos de scraping.

## Pré-requisitos

*   [Docker](https://docs.docker.com/get-docker/)
*   [Docker Compose](https://docs.docker.com/compose/install/)

## Como Executar

1.  **Clone o repositório:**

    ```bash
    git clone <URL_DO_REPOSITORIO>
    cd <NOME_DO_DIRETORIO>
    ```

2.  **Inicie a stack de monitoramento:**

    Execute o seguinte comando na raiz do projeto para iniciar todos os serviços em segundo plano:

    ```bash
    docker-compose up -d
    ```

3.  **Acesse o Grafana:**

    Abra seu navegador e acesse [http://localhost:3000](http://localhost:3000).

4.  **Visualize o Dashboard:**

    *   Faça login no Grafana com as credenciais padrão (`admin`/`admin`). Você será solicitado a alterar a senha no primeiro login.
    *   Navegue até a seção "Dashboards".
    *   O dashboard ".NET GC Metrics" já estará provisionado e pronto para uso.

## Como Parar

Para parar e remover os contêineres, redes e volumes criados, execute:

```bash
docker-compose down
```
