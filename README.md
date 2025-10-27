# OpenROAD Installation Guide

### This guide provides a clear step-by-step process for installing OpenROAD, along with common errors you may encounter during setup and how to fix them.
⚠️ Note: The installation process can take quite some time, so patience is key!

## 🔍 What is OpenROAD?
OpenROAD (Open Rapid Object-Oriented Design) is an open-source initiative aimed at automating the digital design flow for integrated circuits (ICs).
It enables a complete RTL-to-GDSII design flow with minimal manual effort.

The main objective of OpenROAD is to make chip design more accessible by reducing:<br>
<p><ul><li>Cost barriers</li>
 <li>The need for deep technical expertise</li>
 <li>Development risks</li></ul></p>
This tool provides a robust set of methodologies for system and hardware designers to efficiently build silicon chips, even at advanced technology nodes.

### ⚙️ Installation Steps
1. Clone the Repository

Use the following command to clone the OpenROAD Flow Scripts repository:
```bash
git clone https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts.git
```
2. Install Dependencies

Navigate to the cloned directory and run the setup script:

```bash
cd OpenROAD-flow-scripts
sudo ./setup.sh
```
This command installs all required dependencies for the OpenROAD build.

3. Build OpenROAD

Once the setup is complete, build OpenROAD using:
```bash
./build_openroad.sh --local --threads 1 --openroad-args "-DENABLE_TESTS=OFF"
```
🔧 This build command helps avoid common build errors by disabling unnecessary test modules and also ensures a smoother and more stable build.

4. Verify Installation

Once the installation finishes successfully, verify the setup with:
```bash
source ./env.sh
yosys -help
openroad -help
```
If both commands show help messages, it confirms that Yosys and OpenROAD are installed properly.

5. Run the OpenROAD Flow

Move into the flow directory and execute:
```bash
cd flow
make
```
This initiates the OpenROAD design flow.

6. Launch the GUI

To open the graphical interface:
```bash
make gui_final
```
When the GUI window launches successfully, it confirms that OpenROAD is fully functional.
