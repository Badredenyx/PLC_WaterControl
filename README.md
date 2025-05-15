
# 💧 PLC Water Level Control with PID

**Contrôle de Niveau PLC avec PID** 
_TIA Portal V17 · WinCC · Factory I/O · S7-PLCSIM_

![License](https://img.shields.io/badge/License-MIT-blue) ![GitHub Actions](https://img.shields.io/github/actions/workflow/status/Badredenyx/PLC_WaterControl/ci.yml?branch=main) ![Version](https://img.shields.io/badge/Version-1.0.0-green)

Welcome to the **PLC Water Level Control** project! This repository contains a complete PID-based control system for automatic water level regulation in an industrial reservoir. It demonstrates seamless integration between Siemens TIA Portal, Factory I/O, and S7-PLCSIM for hardware-free simulation and an interactive HMI for real-time monitoring and tuning.

---

## 📖 Table of Contents

- [🏁 Getting Started](#-getting-started)
- [⚙️ Installation](#%EF%B8%8F-installation)
- [🚀 Usage](#-usage)
- [🔧 Configuration](#-configuration)
- [🛠️ Key Features](#%EF%B8%8F-key-features)
- [📐 Architecture](#-architecture)
- [💻 Examples](#-examples)
- [🤝 Contributing](#%EF%B8%8F-contributing)
- [📜 License](#-license)

---

## 🏁 Getting Started

Follow these steps to clone and explore the project on your local machine.

```bash
# Clone this repository
git clone https://github.com/Badredenyx/PLC_WaterControl.git
cd PLC_WaterControl
```

Make sure you have the required software installed before proceeding.

---

## ⚙️ Installation

1. **Siemens TIA Portal V17**
2. **S7-PLCSIM Advanced** (Version compatible with TIA Portal V17)
3. **Factory I/O** (for 3D simulation)
4. **WinCC Comfort/Advanced** (for HMI design and runtime)

> 💡 _Note:_ Ensure all software versions are compatible with each other. This project was developed and tested using the above tools.

---

## 🚀 Usage

1. **Open the TIA Portal Project**:
   - Launch TIA Portal V17 and open `Water Control_V17.zap17`.

2. **Load PLC Program in PLCSIM**:
   - Start **S7-PLCSIM** and load the PLC program from TIA Portal.

3. **Configure Factory I/O**:
   - Open `Water Control.factoryio` in Factory I/O.
   - Set the PLC address to match your PLCSIM instance.

4. **Run Simulation**:
   - Start the simulation in Factory I/O.
   - In TIA Portal, go online with the PLC and monitor the PID loop.

5. **Launch HMI**:
   - In WinCC, open the Comfort HMI project, download to HMI runtime, and start.
   - Adjust **Kp**, **Ki**, **Kd** parameters on-the-fly and observe water level response.

---

## 🔧 Configuration

| Parameter | Description                                       | Default   |
|-----------|---------------------------------------------------|-----------|
| `Kp`      | Proportional gain                                  | `2.0`     |
| `Ki`      | Integral gain                                      | `0.5`     |
| `Kd`      | Derivative gain                                    | `0.1`     |
| `Setpoint`| Desired water level (in mm)                       | `500 mm`  |

> 📌 _Tip:_ Fine-tuning PID parameters during live simulation helps achieve optimal stability and response time " i used a transfert function with matlab control toolbox to fine tune the parametres".

---

## ✨ Key Features

- 🔄 **PID Control Loop**: Robust algorithm for maintaining water level stability.
- 🛠️ **Hardware-Free Testing**: Integrate with **S7-PLCSIM** and **Factory I/O** for full-cycle simulation.
- 📊 **Real-Time HMI**: Dynamic monitoring and tuning of PID parameters via **WinCC Comfort**.
- 🎥 **Simulation Video**: A demo video showcasing the complete workflow is included (`Simulation Video.mp4`).

---

## 📐 Architecture

```mermaid
flowchart TD
    A[Factory I/O Tank] -->|Level Signal| B[PLC (PID Block)]
    B -->|Control Signal| C[Valve Actuator]
    B --> D[HMI Display]
    D -->|Kp, Ki, Kd Adjust| B
    D -->|Setpoint Adjust| B
    C --> A
```

---

## 💻 Examples

![Test](SimulationVideo.mp4)

<details>
<summary>Click to view Video</summary>


---

## 🤝 Contributing

Contributions are welcome! Feel free to:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -m 'Add my feature'`)
4. Push to the branch (`git push origin feature/my-feature`)
5. Open a Pull Request

Please ensure your code follows the existing style and includes relevant documentation.

---

## 📜 License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

---

*Happy controlling!* 🚀
