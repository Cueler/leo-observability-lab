# LEO Observability Lab: Infrastructure & Space Weather Research

## 📡 Visão Geral
Este repositório documenta o desenvolvimento de um laboratório de infraestrutura virtualizada dedicado à **observabilidade, telemetria e pesquisa aplicada em redes LEO (Low Earth Orbit)**. O projeto evoluiu de um ambiente de testes inicial para uma arquitetura robusta voltada ao monitoramento de métricas de rede em tempo real e sua correlação com eventos espaciais.

O laboratório serve como base técnica para estudos de viabilidade e performance de constelações de satélites, integrando dados de fontes orbitais com métricas de infraestrutura terrestre.

## 🏗️ Arquitetura e Stack Técnica
A infraestrutura foi projetada seguindo princípios de segmentação de rede e alta disponibilidade:

*   **Virtualização:** Proxmox VE gerenciando containers LXC para otimização de recursos.
*   **Networking & Segurança:** Segmentação de tráfego via MikroTik e pfSense, com conectividade segura através de túneis OpenVPN e WireGuard.
*   **Observabilidade:** Stack completa com Zabbix e Grafana para telemetria de rede e dashboards dinâmicos.
*   **Automação:** Scripts em Python para consumo de APIs astronômicas e de clima espacial, incluindo NASA, NOAA e N2YO.

## 🧪 Focos de Estudo e Aplicação
*   **Telemetria Espacial:** Monitoramento de clima espacial e seu impacto direto em métricas de latência e jitter em links de satélite.
*   **Pesquisa Aplicada:** Base técnica para o desenvolvimento de estudos sobre Edge AI, Federated Learning e Redes Privadas 4G/5G.
*   **Análise de Constelações:** Rastreio e comparação de performance entre diferentes provedores de serviços LEO, como Starlink e Amazon Project Kuiper.

## 📂 Organização do Repositório
*   `/architecture`: Diagramas de topologia e fluxos de rede.
*   `/dashboards`: Modelos JSON para visualização de dados no Grafana.
*   `/telemetry`: Motores de coleta e scripts de automação.
*   `/research`: Artigos técnicos e documentação de suporte à pesquisa.
*   `/docs`: Documentação geral do projeto.
*   `/screenshots`: Evidências visuais da infraestrutura e painéis de controle.

---
*Projeto desenvolvido por César (Cueler), especialista em infraestrutura de TI e pesquisador em redes de satélite.*
