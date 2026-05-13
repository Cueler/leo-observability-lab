Infrastructure architecture and network topology.
# 🏗️ Arquitetura de Rede e Topologia do Lab

Este documento detalha a implementação técnica da infraestrutura de rede, focada na segmentação de tráfego para experimentos de observabilidade e telemetria satelital.

## 💻 Especificações do Host (Hospedeiro)
A fundação do laboratório utiliza hardware otimizado para operação com alta eficiência em virtualização:
*   **Equipamento:** Notebook HP ProBook 6455b.
*   **Processador:** Dual-Core (2 Cores).
*   **Memória RAM:** 6 GB.
*   **Armazenamento:** SSD 240 GB.
*   **Hypervisor:** Proxmox VE.

## 🌐 Fluxo de Dados e Topologia Lógica
A arquitetura foi desenhada para garantir o isolamento entre a rede residencial e o ambiente de testes de dados sensíveis.

![Diagrama de Rede](infra-lab.png)

### Detalhamento das Camadas:

1.  **Borda (Edge):** 
    *   O tráfego de internet chega via roteador da operadora.
    *   Um **MikroTik (192.168.1.200)** atua como roteador de borda do laboratório, separando a rede Wi-Fi doméstica do tráfego técnico.

2.  **Firewall & Gateway:**
    *   O **pfSense (192.168.1.250)** recebe o tráfego WAN através da interface virtual `vtnet0` do Proxmox.
    *   Ele atua como o principal gateway de segurança e gerenciador das rotas do laboratório.

3.  **LAN Segmento (Isolado):**
    *   Através da interface `vtnet1`, o pfSense entrega conectividade para a sub-rede **10.0.0.x/24**.
    *   Este segmento é totalmente isolado para garantir a integridade dos dados coletados.

## 📊 Estratégia de Observabilidade Híbrida
Para garantir 100% de visibilidade do ambiente, a observabilidade foi dividida em dois escopos:

*   **Observabilidade Local (Dados de Pesquisa):**
    *   **CT 102 (Zabbix Server):** IP `10.0.0.163` — Coleta métricas de rede e clima espacial via scripts Python integrados a APIs.
    *   **CT 103 (Grafana):** Localizado no segmento `10.0.0.x` para visualização e análise de dados de telemetria LEO.
*   **Observabilidade Cloud (Saúde da Infraestrutura):**
    *   O **Grafana Cloud** é utilizado para monitorar externamente a saúde do host Proxmox, MikroTik e dos containers na rede principal, garantindo que a infraestrutura permaneça operacional.

---
*Status do Lab: WAN Ativa | Latência Média (Ping Google): 10ms.*
