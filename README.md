# 📊 Mathematics for Data Science - Final Project
> **วิชา:** 1145 201 คณิตศาสตร์สำหรับวิทยาการข้อมูล (Mathematics for Data Science)  
> **ภาคการศึกษา:** 1/2568

---

## 📌 ชื่อโครงงาน: การจำแนกระดับภาวะน้ำหนักตัวและโรคอ้วนจากพฤติกรรมการใช้ชีวิตและสุขภาพ
*(Estimation of Obesity Levels Based On Eating Habits and Physical Condition)*

### 👥 สมาชิกในกลุ่มและหน้าที่รับผิดชอบ (Team Members & Roles)

| ลำดับ | รหัสนักศึกษา | ชื่อ - นามสกุล | บทบาทและหน้าที่รับผิดชอบ (Responsibilities) |
| :---: | :---: | :---: | :--- |
| 1 | 68114540090 | นายเขษมศักดิ์ แก่นทน | • **Data Understanding & Preprocessing:** สำรวจโครงสร้างข้อมูล, จัดการ Categorical Encoding และทำ Feature Standardization<br>• **Linear Algebra Analysis (CLO1):** คำนวณ Covariance Matrix และวิเคราะห์ PCA / SVD เพื่อลดมิติข้อมูล<br>• **Model Evaluation (CLO3–4):** คำนวณ Confusion Matrix, Macro F1 และสรุปผล Best Model จาก Cross-Validation |
| 2 | 6xxxxxxxx-x | [ชื่อ - นามสกุล คู่ทำโปรเจกต์] | • **Exploratory Data Analysis (CLO2):** วิเคราะห์สถิติเชิงพรรณนา, สร้าง Data Visualization และอธิบาย Insight<br>• **Hypothesis Testing (CLO2):** ทดสอบสมมติฐานทางสถิติ (Chi-Square & ANOVA / Mann-Whitney U)<br>• **Model Building & CV (CLO3–4):** สร้างแบบจำลอง Multi-class Classification และทดสอบ k-Fold Cross-Validation |

---

### 🎯 การครอบคลุมเกณฑ์การเรียนรู้ (CLO Coverage)

| หมวด | วัตถุประสงค์เชิงการเรียนรู้ (CLO) | รายละเอียดที่นำมาประยุกต์ใช้ | สถานะ |
| :---: | :--- | :--- | :---: |
| **CLO1** | **Linear Algebra Analysis** | • คำนวณ Covariance Matrix $C = \frac{1}{n-1} X^T X$<br>• Eigendecomposition และทำ PCA ลดมิติข้อมูลเหลือ 2D พร้อมพล็อต Scree Plot | ⬜ กำลังดำเนินการ |
| **CLO2** | **Statistical Learning & EDA** | • ตรวจสอบการกระจายตัว (Normality, Skewness, Outliers)<br>• ทดสอบสมมติฐานทางสถิติเพื่อคัดเลือกตัวแปรสำคัญ<br>• อภิปรายความซับซ้อนของแบบจำลอง (Bias-Variance Trade-off) | ⬜ กำลังดำเนินการ |
| **CLO3** | **Classification Models** | • สร้างแบบจำลอง Multi-class Classification อย่างน้อย 2 ชนิด (Multinomial Logistic Regression, KNN, LDA)<br>• วัดผลด้วย Multi-class Accuracy และ Confusion Matrix | ⬜ กำลังดำเนินการ |
| **CLO4** | **Model Selection & CV** | • เปรียบเทียบโมเดลด้วย 5-Fold Stratified Cross-Validation<br>• สรุปผลคัดเลือก Best Model อย่างมีหลักการทางคณิตศาสตร์ | ⬜ กำลังดำเนินการ |

---

### 📖 ข้อมูลชุดข้อมูล (Dataset Overview)

| คุณสมบัติ (Property) | รายละเอียด (Detail) |
| :--- | :--- |
| **ชื่อชุดข้อมูล** | Estimation of Obesity Levels Based On Eating Habits and Physical Condition[cite: 5] |
| **แหล่งที่มา** | UCI Machine Learning Repository / Kaggle[cite: 5] |
| **ขนาดข้อมูล** | 2,111 แถว (Observations), 17 คอลัมน์ (Features) — *ผ่านเกณฑ์ขั้นต่ำ $\ge 500$ แถว, $\ge 5$ ตัวแปร*[cite: 5] |
| **ประเภทโจทย์** | Multi-class Classification (จำแนกกลุ่ม 7 ระดับ)[cite: 5, 6] |
| **ตัวแปรเป้าหมาย (Target)** | `NObeyesdad` (ระดับภาวะน้ำหนักตัวและโรคอ้วน)[cite: 6] |
| **สัดส่วนข้อมูลสูญหาย** | 0 ค่า (ไม่มี Missing Values)[cite: 7] |

---

### 🗂️ พจนานุกรมข้อมูล (Data Dictionary)

| ชื่อตัวแปร (Feature) | ชนิดข้อมูล | ค่าที่เป็นไปได้ / สเกล | คำอธิบายความหมาย |
| :--- | :---: | :---: | :--- |
| `Gender` | Categorical | `Male`, `Female` | เพศสภาพ |
| `Age` | Numerical | 14.00 – 61.00 | อายุ (ปี) |
| `Height` | Numerical | 1.45 – 1.98 | ส่วนสูง (เมตร) |
| `Weight` | Numerical | 39.00 – 173.00 | น้ำหนักตัว (กิโลกรัม) |
| `family_history_with_overweight` | Categorical | `yes`, `no` | มีคนในครอบครัวมีประวัติน้ำหนักเกินหรืออ้วน |
| `FAVC` | Categorical | `yes`, `no` | รับประทานอาหารที่มีแคลอรีสูงเป็นประจำ |
| `FCVC` | Numerical | 1.00 – 3.00 | ความถี่ในการกินผักในแต่ละมื้อ (1 = ไม่กิน, 3 = ประจำ) |
| `NCP` | Numerical | 1.00 – 4.00 | จำนวนมื้ออาหารหลักในแต่ละวัน |
| `CAEC` | Categorical | `no`, `Sometimes`, `Frequently`, `Always` | การกินขนมหรืออาหารจุบจิกระหว่างมื้อหลัก |
| `CH2O` | Numerical | 1.00 – 3.00 | ปริมาณน้ำเปล่าที่ดื่มต่อวัน (1 = <1 ลิตร, 3 = >2 ลิตร) |
| `CALC` | Categorical | `no`, `Sometimes`, `Frequently`, `Always` | ความถี่ในการดื่มเครื่องดื่มแอลกอฮอล์ |
| `SCC` | Categorical | `yes`, `no` | มีการเฝ้าระวังหรือคำนวณแคลอรีที่บริโภค |
| `FAF` | Numerical | 0.00 – 3.00 | ความถี่ในการออกกำลังกายต่อสัปดาห์ (0 = ไม่ออก, 3 = ประจำ) |
| `TUE` | Numerical | 0.00 – 2.00 | ระยะเวลาใช้งานหน้าจอหรืออุปกรณ์อิเล็กทรอนิกส์ต่อวัน |
| `SMOKE` | Categorical | `yes`, `no` | พฤติกรรมการสูบบุหรี่ |
| `MTRANS` | Categorical | `Public_Transportation`, `Automobile`, `Walking`, `Motorbike`, `Bike` | รูปแบบการเดินทางหลักที่ใช้ในชีวิตประจำวัน |
| `NObeyesdad` | Categorical | 7 ระดับ (เป้าหมาย) | ระดับภาวะน้ำหนักตัวและโรคอ้วน[cite: 6] |

---

### 🎯 รายละเอียดของตัวแปรเป้าหมาย (`NObeyesdad`)

| ระดับ | ชื่อกลุ่ม (Class Label) | จำนวน (คน) | สัดส่วน (%) | ความหมายทางการแพทย์ |
| :---: | :--- | :---: | :---: | :--- |
| 1 | `Insufficient_Weight` | 272 | 12.89% | น้ำหนักต่ำกว่าเกณฑ์มาตรฐาน (ผอม) |
| 2 | `Normal_Weight` | 287 | 13.60% | น้ำหนักตัวอยู่ในเกณฑ์มาตรฐานปกติ |
| 3 | `Overweight_Level_I` | 290 | 13.74% | เริ่มมีภาวะน้ำหนักเกิน ระดับที่ 1 |
| 4 | `Overweight_Level_II` | 290 | 13.74% | ภาวะน้ำหนักเกิน ระดับที่ 2 (เตรียมเข้าสู่โรคอ้วน) |
| 5 | `Obesity_Type_I` | 351 | 16.63% | โรคอ้วน ระดับที่ 1 |
| 6 | `Obesity_Type_II` | 297 | 14.07% | โรคอ้วน ระดับที่ 2 |
| 7 | `Obesity_Type_III` | 324 | 15.35% | โรคอ้วนขั้นรุนแรง ระดับที่ 3 (Morbid Obesity) |

---

### ⚙️ วิธีการติดตั้งและรันโค้ด (Getting Started)

1. **Clone repository:**
   ```bash
   git clone https://github.com/kasemsakKK06/math-ds-obesity-project.git
   cd math-ds-obesity-project
   ```