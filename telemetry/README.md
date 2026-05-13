Telemetry collection and data correlation workflows.
# 📡 Telemetry Engines (Python)

Este diretório contém os motores de integração responsáveis pela camada de inteligência do laboratório. 

## 🛠️ Status do Código: [🔒 CLOSED ACCESS]
Os scripts estão passando por um processo de **Hardening** e **Refatoração para Produção**. O acesso ao código-fonte está restrito para proteger a propriedade intelectual relacionada ao artigo submetido ao SBrT 2026.

## 🧠 Módulos Desenvolvidos:
1. **Engine NOAA/NASA:** Coletor multithread que processa índices de radiação X e densidade de prótons em tempo real.
2. **Engine LEO Tracker (Starlink/Kuiper):** Integração via APIs espaciais para monitoramento de handover e posicionamento orbital.
3. **Zabbix Integration:** Middleware em Python que realiza o tratamento estatístico (limpeza de outliers) antes da ingestão na base de dados.

> **Nota:** Os módulos serão liberados em versões "Community" de forma gradual após a publicação dos resultados oficiais da pesquisa.
