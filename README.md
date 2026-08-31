# Tapejara
## Open-source quadcopter drone for research and teaching

<img width="1147" height="737" alt="tapejaraProject03" src="https://github.com/user-attachments/assets/19f743a0-99f4-43ad-9910-c50aed2a4c60" />

[Primeiro Voo](https://youtu.be/oPYGQzMy-3I) do Tapejara 1.

🇧🇷
Projeto de um drone quadricóptero como plataforma de ensino e pesquisa.
O projeto da PCB foi realizado com a ferramenta EasyEDA Pro [https://easyeda.com/] e os primeiros protótipos foram fabricados na JLCPCB [https://jlcpcb.com/].
O Tapejara é um minidrone do tipo quadricóptero equipado com uma câmera OV2640 e sensores de IMU, barômetro e magnetômetro. Ele utiliza um microprocessador ESP32 para coletar dados dos sensores, calcular ações de controle e fornecer telemetria.
O drone pode ser controlado remotamente por meio de um aplicativo móvel.
O Tapejara foi projetado para servir como uma plataforma de pesquisa educacional para experimentação com firmware de voo, sistemas de controle e coleta de dados. Por esse motivo, a placa de circuito impresso (PCB) permite expansão via placa filha (*shield*), onde sensores adicionais podem ser instalados.
Vale mencionar que "Tapejara" é um gênero de pterossauro que viveu no Brasil durante o período Cretáceo.


🇺🇸
Design of a quadcopter drone as a teaching and research platform.
The PCB design was created using the EasyEDA Pro tool [https://easyeda.com/], and the initial prototypes were manufactured by JLCPCB [https://jlcpcb.com/].
The Tapejara is a quadcopter-style minidrone equipped with an OV2640 camera and IMU, barometer, and magnetometer sensors. It utilizes an ESP32 microprocessor to collect sensor data, calculate control actions, and provide telemetry.
The drone can be controlled remotely via a mobile app.
The Tapejara was designed to serve as an educational research platform for experimenting with flight firmware, control systems, and data collection. For this reason, the printed circuit board (PCB) allows for expansion via a daughterboard (shield) where additional sensors can be installed.
By the way, "Tapejara" is a genus of pterosaur that lived in Brazil during the Cretaceous period.

## ⚖️ Licença / License

Este é um projeto acadêmico híbrido (Hardware + Software) desenvolvido sob a organização `[Universidade Federal do ABC - UFABC]`. Para incentivar a inovação e facilitar parcerias com a indústria, o projeto utiliza um modelo de licenciamento amigável para uso comercial:

### 🇧🇷 Versão em Português

*   **Hardware (Esquemas, PCBs e Arquivos CAD):** Licenciado sob a [CERN Open Hardware Licence Version 2 – Weak Reciprocal](LICENSE-HARDWARE.md) (**CERN-OHL-W v2**).
    *   *O que isso significa:* Você pode integrar este hardware em produtos comerciais e sistemas proprietários fechados. No entanto, qualquer modificação, melhoria ou correção feita **diretamente nos arquivos de design da nossa placa** deve ser compartilhada publicamente sob a mesma licença.
*   **Software e Firmware:** Licenciado sob a [Apache License 2.0](LICENSE).
    *   *O que isso significa:* O código pode ser usado, modificado e distribuído livremente (inclusive comercialmente), oferecendo proteção explícita de patentes para os desenvolvedores e usuários.

---

### 🇺🇸 English Version

*   **Hardware (Schematics, PCBs, and CAD files):** Licensed under the [CERN Open Hardware Licence Version 2 – Weak Reciprocal](LICENSE-HARDWARE.md) (**CERN-OHL-W v2**).
    *   *What this means:* You are free to integrate this hardware into commercial products and proprietary closed systems. However, any modifications, improvements, or fixes made **directly to our board's design files** must be shared publicly under the same license.
*   **Software and Firmware:** Licensed under the [Apache License 2.0](LICENSE).
    *   *What this means:* The code can be freely used, modified, and distributed (including commercially), providing explicit patent protection for both developers and users.
