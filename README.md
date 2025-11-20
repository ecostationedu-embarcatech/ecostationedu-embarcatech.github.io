# 🌱 EcoStationEdu  
### Rede Escolar de Monitoramento Ambiental com IoT e RTOS  

[![EmbarcaTech](https://img.shields.io/badge/EmbarcaTech-TIC_37-004d40?logo=github)](https://embarcatech.softex.br)
[![Licença](https://img.shields.io/badge/Licença-MIT-green)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Desenvolvimento_ativo-2E7D32)](https://ecostationedu-embarcatech.github.io/)
[![Tecnologia](https://img.shields.io/badge/RP2040-FreeRTOS-00BFA5)]()

> **Portal Oficial**: [https://ecostationedu-embarcatech.github.io/](https://ecostationedu-embarcatech.github.io/)

---

## 💡 Missão  
Fortalecer a **educação ambiental** nas escolas públicas da Amazônia com tecnologia cidadã.  
O EcoStationEdu transforma estudantes em protagonistas da ciência de dados, enquanto monitora em tempo real **temperatura, umidade e qualidade do ar** — especialmente durante eventos críticos como **queimadas**.

---

## 🎯 Objetivos Educacionais

- **Monitoramento Hiperlocal**: Coleta de dados ambientais em escolas de Manaus.
- **Educação 4.0**: Atividades práticas alinhadas à **BNCC** (Cultura Digital, Pensamento Computacional).
- **Escalabilidade**: Arquitetura pronta para integrar as **137 escolas estaduais** (base SEDUC/AM).
- **Dados Abertos**: Informações acessíveis para comunidades, professores e defesa civil.

---

## 🛠️ Arquitetura Técnica

### 📡 Hardware (Nó Sensor)
- **Placa**: BitDogLab (RP2040 / Raspberry Pi Pico W)  
- **Sensores**:  
  - ADC Ch 0: Joystick (simula índice de qualidade do ar)  
  - ADC Ch 4: Sensor interno de temperatura do RP2040  
- **Atuadores**:  
  - LED RGB (status de rede)  
  - Display OLED (feedback local)

### 💻 Firmware (C/C++ + FreeRTOS)
- **vTaskSensor**: Leitura periódica de sensores via ADC.  
- **vTaskNetwork**: Gerenciamento Wi-Fi e envio de telemetria.  
- **RTOS Features**:  
  - `Queues` para comunicação entre tarefas  
  - `Mutex` para acesso seguro a hardware (Serial, Display)

### ☁️ Nuvem & Visualização
- **Backend**: Google Sheets + Google Apps Script (API simulada)  
- **Dashboard**: Google Looker Studio (dados em tempo real)  
- **Georreferenciamento**: Mapa dinâmico com localização das escolas de Manaus
---

## 🚀 Como Executar

### Pré-requisitos
- VS Code + extensão Raspberry Pi Pico  
- Pico SDK configurado  
- Compilador ARM GCC

### Instalação
```bash
git clone https://github.com/ecostationedu-embarcatech/eco_station_edu.git
cd eco_station_edu
# Siga o guia de compilação no diretório /firmware

🏛️ Enquadramento Institucional
Este projeto foi desenvolvido no âmbito do Programa EmbarcaTech
(Residência Tecnológica em Sistemas Embarcados – TIC 37),
apoiado pelo Ministério da Ciência, Tecnologia e Inovações (MCTI)
com recursos da Lei nº 8.248/91 (Lei de Informática),
coordenado pela Softex e executado pelo IFCE.

Desenvolvido por Erick Mattos
📍 Manaus, Amazonas – Brasil
