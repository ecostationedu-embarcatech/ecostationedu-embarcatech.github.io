# 🌱 Eco Station Edu
> **Rede Escolar de Monitoramento Ambiental Inteligente (IoT + RTOS)**

![EmbarcaTech Badge](https://img.shields.io/badge/EmbarcaTech-Residência_TIC_37-2e7d32)
![Status](https://img.shields.io/badge/Status-MVP_Funcional-success)
![License](https://img.shields.io/badge/License-MIT-blue)
![Language](https://img.shields.io/badge/C%2F_C%2B%2B-RP2040-00599C)

A **Eco Station Edu** é uma solução de IoT de baixo custo desenvolvida para monitorar a qualidade do ar e condições climáticas em escolas públicas de Manaus. O projeto integra hardware embarcado, sistema operacional de tempo real (FreeRTOS) e análise de dados em nuvem para combater os efeitos das queimadas na educação.

🌐 **[Acesse o Portal Oficial do Projeto](https://ecostationedu-embarcatech.github.io/)**

---

## 🎯 Objetivos
- **Monitoramento Hiperlocal:** Coleta de dados de temperatura, umidade e qualidade do ar em tempo real.
- **Escalabilidade:** Arquitetura pronta para conectar as **137 escolas estaduais** de Manaus (Base de dados SEDUC/AM integrada).
- **Educação 4.0:** Ferramenta pedagógica para ensino de programação e ciências (BNCC).

---

## 🛠️ Arquitetura Técnica

### 📡 Hardware (Nó Sensor)
- **Placa:** BitDogLab (Baseada no Raspberry Pi Pico W / RP2040).
- **Sensores:** - Joystick (Simulação de Qualidade do Ar - ADC Ch 0).
  - Sensor Interno RP2040 (Temperatura - ADC Ch 4).
- **Atuadores:** LED RGB (Status de rede) e Display OLED (Feedback local).

### 💻 Firmware
Desenvolvido em **C/C++** utilizando o **Pico SDK** e **FreeRTOS** para gerenciamento de tarefas concorrentes:
- `vTaskSensor`: Leitura periódica dos sensores (ADC) e conversão de grandezas.
- `vTaskNetwork`: Gerenciamento da conectividade Wi-Fi e envio de dados (Simulação de Telemetria).
- **Recursos RTOS:** Uso de *Queues* para comunicação segura entre tarefas e *Mutex* para controle de acesso ao hardware (Serial/Display).

### ☁️ Cloud & Dados
- **Backend:** Google Sheets (Banco de Dados) + Google Apps Script (API Simulada).
- **Visualização:** Dashboard interativo no **Google Looker Studio**.
- **Georreferenciamento:** Mapa dinâmico com coordenadas reais das escolas de Manaus.

---

## 🚀 Como Executar o Projeto

### Pré-requisitos
- VS Code com extensão **Raspberry Pi Pico**.
- SDK do RP2040 configurado.
- Compilador C/C++ (Arm GCC).

### Instalação
1. Clone o repositório:
   ```bash
   git clone [https://github.com/ecostationedu-embarcatech/eco_station_edu.git](https://github.com/ecostationedu-embarcatech/eco_station_edu.git)
