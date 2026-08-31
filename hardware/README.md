🇧🇷
# Tapejara 1

Primeiro [voo](https://youtu.be/oPYGQzMy-3I) do Tapejara. Veja a [documentação](./tapejaraBoard_v1.pdf) — Esquemático, layout da PCB e visualização 3D.

> Errata: A pinagem do conector da câmera OV2640 está espelhada: 1 <-> 24 | 24 <-> 1. Não tente conectar a câmera, pois isso causará um curto-circuito na PCB.
> Uma versão corrigida será disponibilizada em uma atualização futura (em breve).
> Todas as outras funcionalidades permanecem inalteradas. O protótipo foi testado em voo por linha de visada.

# Introdução ao projeto

O Tapejara tpj-01 é um micro-drone no estilo quadricóptero equipado com uma câmera OV2640 e sensores IMU, barômetro e magnetômetro. Ele utiliza um microprocessador ESP32 para coletar dados dos sensores, calcular as ações de controle e fornecer telemetria. O drone pode ser controlado remotamente por meio de um aplicativo móvel (atualmente em desenvolvimento).

O tpj-01 foi projetado para servir como uma plataforma de pesquisa educacional para experimentos com firmware de voo, sistemas de controle e coleta de dados. Por esse motivo, a placa de circuito impresso (PCB) permite expansão através de uma placa secundária (shield) onde sensores adicionais podem ser instalados.

A propósito, "Tapejara" é um gênero de pterossauro que viveu no Brasil durante o período Cretáceo.

# Componentes do projeto

* MCU: ESP32-S3 WROOM-1-N16R8
* Câmera OV2640
* IMU: MPU-6050
* Barômetro: BMP280
* Magnetômetro: QMC5883P
* Motores: coreless 8520 (2x CW + 2x CCW)
* Diâmetro das hélices: 55 / 65 mm (2x CW + 2x CCW)
* Bateria: 1S (3.7V) | 500 mAh
* PCB (X-Frame):
  * Material: FR-4
  * Cor: Verde
  * Espessura: 1.2 mm
* Controle remoto via aplicativo móvel e Wi-Fi

# Descrição do hardware

Este projeto consiste nas seguintes partes:

* O MCU para controle de voo (PID + PWM), coleta de dados dos sensores e telemetria;
* Gerenciamento de energia: a fonte de energia primária do sistema é uma bateria 1S que alimenta os motores diretamente. Um regulador Buck-Boost gera um valor estável de 3.3V para o MCU e os sensores. A câmera também precisa de reguladores LDO para 1.3V e 2.8V, ambos derivados do regulador de 3.3V. A bateria possui proteção contra inversão de polaridade.
* USB/OTG: uma porta micro USB tipo C é usada para upload de firmware e alimentação (durante a programação do drone). Ela possui proteção contra ESD (Descarga Eletrostática).
* PWM: os 4 motores são controlados via sinais PWM gerados no MCU que chaveiam 4 FETs NMOS de potência.
* Sinalização: 4 LEDs podem ser usados para fornecer feedback visual ao usuário. Durante o voo, eles são mantidos acesos para indicação de direção (2 LEDs vermelhos estão posicionados no lado esquerdo do frame e 2 LEDs verdes no lado direito).
* Expansão por Shield: é possível projetar uma placa secundária para expansão de sensores/processamento. A placa principal fornece a tensão da bateria, 3.3V, conexão de aterramento (GND) e 4 pinos de E/S do ESP32 (2 da conexão I²C dos sensores e 2 pinos adicionais).

A própria placa de circuito impresso (PCB) foi projetada em uma configuração em "X" para suportar os motores diretamente, eliminando assim a necessidade de suportes adicionais impressos em 3D. O design é autocontido. A bateria e a câmera devem ser fixadas à placa usando qualquer meio disponível. Para a câmera, existem dois furos na parte frontal do drone que podem ser úteis.

# Processos de montagem

A placa de circuito impresso (PCB) é autocontida. Basta encaixar os quatro motores sob pressão nos devidos lugares (seguindo as marcações impressas na placa) e montar a câmera e a bateria.

O firmware pode ser enviado através da porta USB usando a Arduino IDE. A taxa de transmissão serial (baud rate) é 115200. Para usar a Arduino IDE na programação, selecione esta placa: ESP32-S3-USB-OTG.

Após o upload do firmware, o drone deve ser configurado usando o aplicativo de controle remoto (RC).

# Exibição do produto final

Visualização 3D da PCB (superior e inferior).
<img width="2160" height="1709" alt="3D_Tapejara_brd_v1_Top" src="https://github.com/user-attachments/assets/421dc2c3-f4a4-4919-8600-31786bd22774" />
<img width="2160" height="1789" alt="3D_Tapejara_brd_v1_Bott" src="https://github.com/user-attachments/assets/33a80232-4820-4825-9d8d-95a0a3bbe5e2" />

Peso da PCB de apenas 12g.
<img width="844" height="1090" alt="drone32g" src="https://github.com/user-attachments/assets/2ab68ff3-4629-4a88-acba-85b6dc3b0c10" />

Peso do drone montado de apenas 32.36g.
<img width="899" height="956" alt="weightAssembl" src="https://github.com/user-attachments/assets/6ef2cb93-e24e-4ff2-85cd-5bc254b083ed" />

Imagem final.
<img width="1023" height="696" alt="tapejaraAssembled" src="https://github.com/user-attachments/assets/c155216f-b9ae-489a-8fc9-76faab441f1f" />

---

🇺🇸
# Tapejara 1
First [flight](https://youtu.be/oPYGQzMy-3I) of Tapejara.

See the [documentation](./tapejaraBoard_v1.pdf) -- Schematic, PCB layout and 3D view.

>Errata: The pinout of the OV2640 camera connector is mirrored: 1 &lt;-&gt; 24 | 24 &lt;-&gt; 1. Do not try to connect the camera or it will cause a short-circuit in the PCB.
>A corrected version will be provided in a future update (coming soon).
>All other functionalities remain unchanged. The prototype has been flight-tested via line-of-sight.

# Project introduction
The Tapejara tpj-01 is a quadcopter-style micro-drone equipped with an OV2640 camera and IMU, barometer, and magnetometer sensors. It utilizes an ESP32 microprocessor to collect sensor data, calculate control actions, and provide telemetry.
The drone can be controlled remotely via a mobile app (currently under development).
The tpj-01 was designed to serve as an educational research platform for experimenting with flight firmware, control systems, and data collection. For this reason, the printed circuit board (PCB) allows for expansion via a daughterboard (shield) where additional sensors can be installed.
By the way,  "Tapejara" is a genus of pterosaur that lived in Brazil during the Cretaceous period.

# Project Components
* MCU: ESP32-S3 WROOM-1-N16R8
* OV2640 camera
* IMU: MPU-6050
* Barometer: BMP280
* Magnetometer: QMC5883P
* Rotors: coreless 8520 (2x CW + 2x CCW)
* Propellers Diameter: 55 / 65 mm (2x CW + 2x CCW)
* Battery: 1S (3.7V) | 500 mAh
* PCB (X-Frame):
    * Material: FR-4
    * Color: Green
    * Thickness: 1.2 mm
* Remote control via Mobile App and Wi-Fi

# Hardware description
This project consists of the following parts:
* The MCU for flight control (PID + PWM), data sensor collection and telemetry;
* Power management: the primary energy source for the system is an 1S battery that supply the rotors directly. A Buck-Boost regulator generates a stable 3.3V for the MCU and the sensors. The camera also needs LDO regulators for 1.3V and 2.8V, both derived from the 3.3V regulator. The battery is protected against polarity inversion.
* USB/OTG: a type-C micro USB port is used for firmware upload and power supply (during the drone programming). It is protected against ESD (ElectroStatic Discharge).
* PWM: the 4 rotors are controlled via PWM signals generated at the MCU that switch 4 power NMOS FETs.
* Sinalization: 4 LEDs can be used to provide visual feedback to the user. During flight, they are kept on for direction indication (2 red LEDs are positioned at the left-side of the frame and 2 green LEDs at the right-side).
* Shield expansion: it is possible to design a daughterboard for sensor/processing expansion. The main board provides the battery voltage, 3.3V, ground (GND) connection, and 4 ESP32 I/O pins (2 from the I²C sensors connection and 2 additional pins).

The printed circuit board (PCB) itself was designed with an "X" configuration to support the rotors directly, thereby eliminating the need for additional 3D-printed mounts. The design is self-contained.
The battery and camera must be secured to the board using any available means. For the camera, there are two holes on the front of the drone that may be useful.

# Assembling processes
The printed circuit board (PCB) is self-contained. Simply press-fit the four rotors into place (following the markings printed on the board) and mount the camera and battery.
The firmware can be uploaded via the USB port using the Arduino IDE. The serial baud rate is 115200.
To use the Arduino IDE for programming, select this board: ESP32-S3-USB-OTG.
After uploading the firmware, the drone must be configured using the remote control (RC) app.

# Finished product display
3D view of the PCB (top and bottom).

<img width="2160" height="1709" alt="3D_Tapejara_brd_v1_Top" src="https://github.com/user-attachments/assets/421dc2c3-f4a4-4919-8600-31786bd22774" />

<img width="2160" height="1789" alt="3D_Tapejara_brd_v1_Bott" src="https://github.com/user-attachments/assets/33a80232-4820-4825-9d8d-95a0a3bbe5e2" />


PCB weight of only 12g.

<img width="844" height="1090" alt="drone32g" src="https://github.com/user-attachments/assets/2ab68ff3-4629-4a88-acba-85b6dc3b0c10" />


Assembled Drone weight of only 32.36g.

<img width="899" height="956" alt="weightAssembl" src="https://github.com/user-attachments/assets/6ef2cb93-e24e-4ff2-85cd-5bc254b083ed" />


Final image.

<img width="1023" height="696" alt="tapejaraAssembled" src="https://github.com/user-attachments/assets/c155216f-b9ae-489a-8fc9-76faab441f1f" />
