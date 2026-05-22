<h1 align="center">Olá, eu sou o Dave! 👋 &nbsp;|&nbsp; Hi, I'm Dave!</h1>

<p align="center">
  🎓 Estudante de Sistemas Embarcados &nbsp;·&nbsp; Embedded Systems Student<br/>
  🤖 Apaixonado por automação, IoT e instrumentação &nbsp;·&nbsp; Passionate about automation, IoT & instrumentation<br/>
  🌱 Construindo soluções reais com hardware e software &nbsp;·&nbsp; Building real-world solutions with hardware & software<br/>
  📍 IFF Campus Bom Jesus do Itabapoana — RJ, Brasil
</p>

<p align="center">
  <a href="https://github.com/DaveK20">
    <img src="https://img.shields.io/badge/GitHub-DaveK20-181717?style=for-the-badge&logo=github"/>
  </a>
  <a href="https://linkedin.com/in/SEU_USUARIO_AQUI">
    <img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/>
  </a>
  <a href="mailto:davefr@outlook.com.br">
    <img src="https://img.shields.io/badge/Email-davefr@outlook.com.br-D14836?style=for-the-badge&logo=gmail&logoColor=white"/>
  </a>
</p>

---

## 🛠️ Tech Stack

<p align="left">
  <img src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white"/>
  <img src="https://img.shields.io/badge/Arduino-00979D?style=for-the-badge&logo=arduino&logoColor=white"/>
  <img src="https://img.shields.io/badge/ESP32-E7352C?style=for-the-badge&logo=espressif&logoColor=white"/>
  <img src="https://img.shields.io/badge/ESP8266-E7352C?style=for-the-badge&logo=espressif&logoColor=white"/>
  <img src="https://img.shields.io/badge/PlatformIO-F5822A?style=for-the-badge&logo=platformio&logoColor=white"/>
  <img src="https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black"/>
  <img src="https://img.shields.io/badge/ThingSpeak-IoT-brightgreen?style=for-the-badge"/>
</p>

**Protocolos & Interfaces:** OneWire · I2C · SPI · UART · ADC · PWM · Interrupts  
**Periféricos:** RTC DS3231/DS1307 · DHT22 · DS18B20 · LCD I2C · MicroSD · Relés · Servos · Válvulas Motorizadas  
**Técnicas:** Deep Sleep · Watchdog Timer · EEPROM/NVS · WebSocket · Captive Portal · HTTP REST · Calibração Analógica

---

## 🚀 Projetos em Destaque | Featured Projects

---

### 🥛 [Sistema CIP para Ordenhadeira Mecânica](https://github.com/DaveK20/SEU_REPO)
> Automação completa do ciclo de limpeza CIP (*Clean-In-Place*) para ordenhadeiras, aplicado no IFF Campus Bom Jesus do Itabapoana.

O sistema controla de forma autônoma **válvulas esféricas motorizadas**, **bombas peristálticas** de dosagem de produtos químicos e **resistência de aquecimento**, executando sequências de pré-enxague, lavagem alcalina, lavagem ácida e sanitização — tudo guiado por display LCD com painel de botões físicos.

- 🔧 Controle de 4 válvulas motorizadas + 3 bombas peristálticas + resistência elétrica via módulo relé
- 🧪 Dosagem automática de alcalino, ácido e sanitizante calculada por **fluxo calibrado da bomba**
- 🌡️ Controle de temperatura com histerese via sensor DS18B20
- 💾 Parâmetros (temperatura, volume, tempo de circulação) salvos em **EEPROM**
- 🛡️ **Watchdog Timer** + interrupção de emergência por hardware para operação segura
- 🎛️ Interface completa com **LCD 16x2 + 5 botões** — ciclo padrão e ciclos personalizáveis

`C++` `Arduino Mega` `EEPROM` `DS18B20` `Relay Control` `Industrial Automation`

---

### 🌦️ [Estação Meteorológica Agrícola](https://github.com/DaveK20/SEU_REPO)
> Monitoramento climático de campo com cálculo automático de Evapotranspiração de Referência (ETo) e datalogger em SD.

Coleta temperatura, umidade e precipitação via pluviômetro de báscula (reed switch com interrupção de hardware), calcula a **ETo diária pelo método Hargreaves-Samani** e registra tudo em arquivos `.csv` no SD com timestamp, além de sincronizar com o ThingSpeak.

- 🌧️ Pluviômetro com **interrupção de hardware** — `0,24 mm/pulso`
- 📐 Cálculo diário de **ETo** publicado automaticamente às 23h58
- 💾 Datalogger em **cartão SD** organizado por `AAAA/MM/DD.csv` com cabeçalho automático
- ⏰ Timestamp preciso via **RTC DS1307** independente de internet

`C++` `ESP8266` `RTC` `MicroSD` `ThingSpeak` `Agro IoT`

---

### 🌱 [Estufa Inteligente](https://github.com/DaveK20/estufa-inteligente)
> Monitoramento e controle automático de ambiente para estufas agrícolas com ESP32 e IoT.

Dois sensores DHT22 monitoram temperatura e umidade interna e externa. O sistema aciona **ventilador** e **nebulizador** de forma autônoma por limiares configuráveis, com ciclos de operação inteligentes para evitar excesso de umidade.

- 💨 Ventilador ligado automaticamente acima de **35 °C**
- 💧 Nebulizador acionado acima de **38 °C** com ciclos de liga/desliga configuráveis
- ☁️ Status dos atuadores enviados em tempo real ao **ThingSpeak**
- ⏱️ **Watchdog** via timer de hardware com reinicialização automática

`C++` `ESP32` `DHT22` `PlatformIO` `ThingSpeak` `Relay Control`

---

### 🐟 [Alimentador Automático de Peixes](https://github.com/DaveK20/SEU_REPO)
> Sistema solar autônomo de alimentação agendada para o laboratório de piscicultura do IFF.

Energizado por **painel solar com bateria**, o dispositivo aciona o dispensador nos horários programados via **interface web no celular** sem instalar nenhum app. Após cada alimentação, o ESP32 entra em **deep sleep** acordando exatamente no próximo agendamento.

- 📱 **Captive portal** com WebSocket — interface web responsiva sem app instalado
- ⏰ Até **3 programas diários** salvos em **memória Flash (NVS)**
- 🔋 **Deep Sleep dinâmico** — acorda exatamente no próximo agendamento via RTC DS3231
- ☁️ Integração com **Firebase Realtime Database** para monitoramento remoto

`C++` `ESP32` `Deep Sleep` `RTC` `WebSocket` `Firebase` `Solar Energy`

---

### 🧪 [pHmetro com Calibração e IoT](https://github.com/DaveK20/SEU_REPO)
> Instrumento de medição de pH com calibração matemática por dois pontos, ADC calibrado e monitoramento em nuvem.

Utiliza a **API nativa de calibração do ADC do ESP32** (`esp_adc_cal`) para máxima precisão. A calibração por dois pontos resolve um sistema linear para obter os coeficientes da equação `pH = ax + b`, persistidos na **EEPROM**.

- 📏 Média de **10 amostras** + cálculo de **desvio padrão** exibido no LCD
- 🔧 **Calibração guiada** por botão físico com soluções tampão pH 4,01 e 6,86
- 💡 ADC com **calibração de Vref** para eliminar não-linearidade do conversor interno
- 📡 Wi-Fi **desligado entre envios** — ligado apenas nos ciclos de 15 min ao ThingSpeak

`C++` `ESP32` `ADC Calibration` `EEPROM` `DS18B20` `LCD I2C` `ThingSpeak`

---

## 📊 GitHub Stats

<p align="center">
  <img height="160em" src="https://github-readme-stats.vercel.app/api?username=DaveK20&show_icons=true&theme=dark&include_all_commits=true&count_private=true"/>
  <img height="160em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=DaveK20&layout=compact&langs_count=6&theme=dark"/>
</p>

---

<p align="center">
  <i>"Hardware sem software é sucata. Software sem hardware é só teoria."</i><br/>
  <i>"Hardware without software is junk. Software without hardware is just theory."</i>
</p>
