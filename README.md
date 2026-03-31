# ⚡ Hydra Node 3: Obsidian Sled (GPU Expansion)

Node 3 is a "Stateless Compute" unit designed to scale the VRAM capacity of the Hydra Cluster without the overhead of a full PC build. It is physically controlled by the **Sentinel Phase 2** interface.

## 🧠 System Concept
Traditional clusters waste budget on multiple CPUs and RAM sticks. Node 3 focuses 75% of its budget on the **GPU (RTX 3060 12GB)**. It connects directly to the Master Node's PCIe bus via an M.2 bridge, appearing as a native second GPU for AI models.

## 🛠️ Hardware Specifications
- **GPU:** NVIDIA RTX 3060 (12GB GDDR6 version for LLM context depth).
- **Interface:** ADT-Link R43SG (M.2 NVMe to PCIe x16 Gen3 Bridge).
- **Power Unit:** 1200W Platinum Server PSU + 12-Port Breakout Board.
- **Cooling:** Open-frame chassis with dual 120mm high-static pressure fans.

## 🔌 Connection & Logic
- **Data:** M.2 Slot (Master Node) <---> R43SG Bridge <---> RTX 3060 (Node 3).
- **Power Control:** RPi Pico (Sentinel) <---> 5V Relay <---> Server PSU (Node 3).
- **Authorization:** Node 3 only powers up when Dual-RFID keys are validated at the Sentinel Terminal.

## 💰 Budget Breakdown ($400 Target)

| Component | Model | Est. Price |
| :--- | :--- | :--- |
| **GPU** |ASUS NVIDIA GeForce RTX 3060 TUF Gaming OC 12GB | £208.70 |[ebay](https://www.ebay.co.uk/itm/137180841263?_skw=3060+12+gb+TUF&itmmeta=01KN0EGY7N66PHMG95DNC010YX&hash=item1ff09d852f%3Ag%3AgRQAAeSwERVpypWb&itmprp=enc%3AAQALAAAA0GfYFPkwiKCW4ZNSs2u11xB6IISiCrmYDIsu6tOCWt58%2FAKfNATxP4pREMmpzvTf57umhQ9pZyUX7JxMHzc0DAsL6p2na20VgOiPoXdeaZStsyuoms00EbQk7EKqI0%2F9c3%2Fk6gAXG%2FG495%2BPYj3eRfUPPoKdLIP2tYvNcBMcqKSJUTmKbNCUwop4z%2FrxZ5cAFXc%2FC%2FnNiqR7NAf65nmAgyqSWB04xOyfpkQAB94iYgvZtfSFfHa5K| **Power** | CORSAIR CX650 80 PLUS Bronze Non Modular Low-Noise ATX 650 Watt Power Supply - UK - Black| £47.99 |[amazon](https://www.amazon.co.uk/CORSAIR-Bronze-Modular-Low-Noise-Supply/dp/B0CJRXX5WT/ref=sr_1_2?crid=3BDYV2HEOIKI6&dib=eyJ2IjoiMSJ9.Y9QzK2TzeOv-uLxPTPiWHCsDGf3WmfSzQoXtYWy0tgvywi8sPu_46vFTiBdxsD2JoEsqr-X5FMyGNj-QCSxddFpi9lOTQjJIjsWnDM12WIBEZveYMv9VV5LQX8pXKstyVhjivfMw_e_DMIRjlBj-LMqmkPi1Ujb6KmTK0kDzbq1dmJCNBgChEgaEpk1jN1HRPcDkVNrHT-6kcTSUhmTL8hpQN_82XVzCr9ZCf_iaqq0.FjkD4lb_snaJb70-xgWlex3qcZsWKSBDZPHDI8d4h3I&dib_tag=se&keywords=EVGA%2FCorsair%2B600W%2BPSU&qid=1774910846&sprefix=%2Caps%2C312&sr=8-2&th=1)
| **Bridge** | ADT-Link R43SG M.2 Adapter | $45 |
| **Fans/Frame** | Arctic P12 + DIY Chassis | $25 |
| **TOTAL** | | **$400** |
