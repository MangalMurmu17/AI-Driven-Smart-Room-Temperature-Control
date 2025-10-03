# 🌡️ AI-Driven Smart Room Temperature Control for Energy Optimization  

## 📌 Project Overview  
This project develops an **AI-powered smart room temperature control system** that dynamically adjusts HVAC actions to ensure **energy efficiency** and **occupant comfort**.  

Traditional systems are static and often waste energy, but this project applies **Reinforcement Learning (RL)** to learn **when to increase, decrease, or maintain room temperature** based on real-time input data such as:  
- Temperature 🌡️  
- Humidity 💧  
- Occupancy 👥  
- Time of day ⏰  
- External weather conditions 🌤️  

The model achieved a **34.67% reduction in energy consumption** compared to traditional methods.  

---

## 🤖 Machine Learning Models Used  

### 1. **Reinforcement Learning (Q-Learning)**  
- The system is modeled as an **agent-environment interaction**:  
  - **Agent** → HVAC controller (AI model)  
  - **Environment** → Room (temperature, humidity, occupancy, etc.)  
  - **State** → Combination of room conditions (Temp, Humidity, Occupancy, Time)  
  - **Actions** → HVAC control (Increase, Decrease, Maintain)  
  - **Reward** → +1 if action leads to desired comfort & energy efficiency, -1 otherwise  

- **Q-learning Algorithm**:  
  - Maintains a **Q-table** mapping state-action pairs to expected rewards  
  - Uses an **ε-greedy policy** to balance exploration vs exploitation  
  - Continuously updates Q-values with each episode using:  

  ```
  Q(s, a) ← Q(s, a) + α [ R + γ max(Q(s’, a’)) – Q(s, a) ]
  ```
  where:  
  - `s` = current state  
  - `a` = chosen action  
  - `R` = reward  
  - `γ` = discount factor  
  - `α` = learning rate  

- Over multiple training episodes, the agent **learns the best policy** for minimizing energy use while maintaining comfort.  

---

### 2. **Simulation-Based Testing**  
Instead of direct IoT deployment, the system was tested in a **simulated environment** using the dataset:  
- `smart_room_data_balanced.csv` → contains historical temperature, humidity, occupancy patterns.  
- The simulation mimics real-world room conditions to validate the RL model before hardware integration.  

---

## 🔬 How It Works (Step-by-Step)  

1. **Input Data Collection**  
   - Features: `Room Temperature`, `External Temperature`, `Humidity`, `Time of Day`, `Occupancy`  

2. **Preprocessing**  
   - Convert categorical features (time of day, HVAC actions) into numeric values  
   - Normalize continuous features (temperature, humidity)  
   - Map unique feature combinations into **states**  

3. **Training the RL Agent**  
   - Initialize Q-table with all state-action pairs = 0  
   - For each training episode:  
     - Select an action using ε-greedy policy  
     - Calculate reward based on efficiency & comfort  
     - Update Q-values using RL update rule  

4. **Testing & Simulation**  
   - Run the trained Q-table on unseen room conditions  
   - Measure performance in terms of energy savings and comfort balance  

5. **Result**  
   - Smarter distribution of actions:  
     - **Decrease (D), Maintain (M), Increase (I)** → balanced mix instead of overusing cooling/heating  
   - **34.67% energy reduction** achieved in simulation  
---

## 🖼️ System Architecture

---

## 📊 Results Summary  

- ✅ **Q-Value Convergence** → The agent learned optimal policies steadily  
- 📉 **Energy usage reduced by 34.67%** compared to traditional systems  
- 🌡️ **Balanced action distribution** → no over-cooling/heating  
- 🧠 **RL agent adapted dynamically** to occupancy and environmental changes  

---

## 📌 Applications  
- 🏠 Smart Homes – Automated comfort & reduced electricity bills  
- 🏢 Offices/Buildings – Large-scale energy optimization  
- 🏭 Industries – Maintain process-specific temperatures efficiently  
- 🏥 Hospitals/Labs – Ensure stability in sensitive environments  
- 🏫 Schools/Institutions – Improve learning environment with sustainable energy use  

---

## 🔮 Future Scope  
- Hardware deployment with IoT sensors for real-world testing  
- Integration with **Deep Reinforcement Learning (DRL)** for complex environments  
- Mobile/Voice assistant support for user interaction  
- Expansion to multi-room & building-wide energy management  
- Incorporating additional parameters like **CO₂ levels, air quality, and room size**  

---
