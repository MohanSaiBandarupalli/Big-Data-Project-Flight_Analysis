# ✈️ Flight Data Analysis using Hadoop & AWS

**Author:** Mohan Sai Bandarupalli  
🎓 *MS in Data Science, New Jersey Institute of Technology*  
📧 mb2279@njit.edu  
📘 *Course:* CS 644 – Introduction to Big Data  
👩‍🏫 *Professor:* Ravneet Kaur  

---

## 🧭 Project Summary
This project analyzes the **Airline On-Time Performance Dataset (1987–2008)** using **Hadoop MapReduce**, **Oozie workflows**, and **AWS virtual machines**.  
The goal was to extract operational insights such as **airline punctuality**, **airport taxi times**, and **cancellation trends**, while benchmarking **cluster scalability** across increasing data and VM sizes.

---

## ⚙️ Tools & Technologies
| Category | Tools Used |
|-----------|-------------|
| Big Data Framework | Hadoop, MapReduce, Oozie |
| Cloud Infrastructure | AWS EC2 Virtual Machines |
| Language | Java / Python (MapReduce Jobs) |
| Dataset | [Harvard Dataverse – Airline On-Time Performance](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/HG7NV7) |
| Visualization | Performance & scalability graphs via AWS logs |

---

## 🚀 Key Objectives & Jobs
### **1. Airline On-Time Performance**
- **Goal:** Identify top 3 airlines with highest and lowest on-time probabilities.  
- **Method:** Two-step MapReduce job computing on-schedule probabilities per airline.  
- **Output:** Ranked list of best and worst performing carriers.

### **2. Airport Taxi Time Analysis**
- **Goal:** Find airports with longest and shortest average taxi times.  
- **Method:** MapReduce job calculating average `TaxiIn` + `TaxiOut` per airport.  
- **Output:** Top and bottom 3 airports ranked by taxi time efficiency.

### **3. Flight Cancellation Analysis**
- **Goal:** Determine the most common causes of cancellations.  
- **Method:** Aggregation of cancellation codes and counts through MapReduce.  
- **Output:** Most frequent cancellation reason (e.g., Weather, NAS, Carrier, Security).

---

## 📈 Performance Evaluation
### **Cluster Scalability (VMs vs Execution Time)**
| VM Count | Execution Time |
|-----------|----------------|
| 3 | 10m 06s |
| 5 | 8m 30s |
| 7 | 7m 10s |
| 9 | 6m 05s |
| 12 | **5m 07s** |

> ⏩ Increasing VM nodes improved execution speed up to 12 nodes, after which returns diminished — indicating near-optimal cluster performance.

### **Data Scalability (Years vs Execution Time)**
| Data Span (Years) | Execution Time |
|-------------------|----------------|
| 1 | 2m 50s |
| 12 | 4m 19s |
| 22 | **5m 07s** |

> 📊 Execution time grew linearly with dataset size, confirming **Hadoop scalability** and **performance stability**.

---

## 💡 Insights
- Hadoop + AWS achieved **efficient distributed computation** over 20+ years of airline data.  
- Scaling from 3 → 12 nodes yielded **~50% faster performance**.  
- MapReduce accurately identified **operational inefficiencies** in airlines and airports.  
- Demonstrated **linear scalability** and **balanced resource utilization** under heavy data loads.

---

## 🧩 Workflow Overview
```text
Data Input → Mapper (Flight Logs) → Reducer (Aggregated Metrics)
→ Sorted Output (Top 3 Airlines, Airports, Cancellations)
→ Oozie Workflow → AWS Cluster (3–12 Nodes)
