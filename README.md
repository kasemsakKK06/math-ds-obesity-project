# Final-Project: การวิเคราะห์ปัจจัยด้านวิถีชีวิตและสภาพร่างกายที่เกี่ยวข้องกับระดับน้ำหนักตัวและภาวะโรคอ้วน
### (Analysis of Lifestyle and Physical Factors Associated with Body Weight and Obesity Levels)

> **รายวิชา:** 1145 201 คณิตศาสตร์สำหรับวิทยาการข้อมูล (Mathematics for Data Science)  
> **ภาคการศึกษา:** 1/2569

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white)](https://jupyter.org/)

---

## 📌 ภาพรวมโครงงาน (Project Overview & Problem Statement)

โครงงานนี้มีเป้าหมายเพื่อจำแนกระดับภาวะน้ำหนักตัวและโรคอ้วนออกเป็น **7 ระดับ (Multi-class Classification)** โดยอาศัยข้อมูลพฤติกรรมการกิน การใช้ชีวิต สภาพร่างกาย และประวัติครอบครัว โดยประยุกต์ใช้แนวคิดทางคณิตศาสตร์ สถิติ และวิทยาการข้อมูลอย่างเป็นระบบ ตั้งแต่การวิเคราะห์ข้อมูลด้วย **Linear Algebra (PCA)**, การทดสอบสมมติฐานทางสถิติ (**ANOVA & Chi-Square**), การวิเคราะห์ **Bias-Variance Trade-off** ตลอดจนการประเมินและคัดเลือกโมเดลด้วย **5-Fold Stratified Cross-Validation**

---

## 👥 สมาชิกในกลุ่มและหน้าที่รับผิดชอบ (Team Members & Roles)

| ลำดับ | รหัสนักศึกษา | ชื่อ - นามสกุล | หน้าที่หลักและส่วนงานที่รับผิดชอบ |
| :---: | :----------- | :------------------- | :------------------------------------------------ |
| 1 | 68114540090 | นายเขษมศักดิ์ แก่นทน | Exploratory Data Analysis (EDA), Hypothesis Testing **(CLO2)**, Model Building & Cross-Validation **(CLO3, CLO4)** |
| 2 | 68114540184 | นายณัฐดนัย ทองสรรค์ | Data Preprocessing, Linear Algebra & PCA **(CLO1)**, Model Evaluation & Data Storytelling **(CLO4)** |

---

## 🎯 การครอบคลุมผลลัพธ์การเรียนรู้ (Course Learning Outcomes: CLO)

| สัปดาห์ | หมวดการเรียนรู้ (CLO) | หัวข้อเนื้อหา (Topics) | การประยุกต์ใช้จริงในโครงงาน | สถานะ |
| :---: | :--- | :--- | :--- | :---: |
| **Week 4** | **CLO1: Linear Algebra** | Covariance Matrix, Eigendecomposition & PCA | ประยุกต์ใช้ PCA เพื่อวิเคราะห์โครงสร้างของข้อมูลและความแปรปรวน พร้อมแสดง Explained Variance, Scree Plot และการแสดงผลข้อมูลใน 2 มิติด้วย PC1 และ PC2 | ✅ |
| **Week 6–7** | **CLO2: Statistical Learning & EDA** | Distribution, Hypothesis Testing, Bias-Variance | วิเคราะห์การกระจายตัวด้วย Histogram และ Boxplot ทดสอบ One-Way ANOVA (Age) และ Chi-Square Test (Family History) รวมถึงวิเคราะห์ Training/Test Error ของ Decision Tree | ✅ |
| **Week 11–13** | **CLO3: Model Building** | Classification Pipeline, Logistic Regression, KNN | สร้าง Pipeline ร่วมกับ `StandardScaler` พัฒนาโมเดล Multi-class Logistic Regression และ K-Nearest Neighbors (KNN) พร้อมประเมินด้วย Confusion Matrix, Accuracy และ Macro F1-score | ✅ |
| **Week 14** | **CLO4: Model Selection & CV** | 5-Fold Stratified CV, Model Comparison | เปรียบเทียบประสิทธิภาพของโมเดลจำแนกประเภท และคัดเลือก **Random Forest Classifier** จาก Mean CV Accuracy | ✅ |

---

## 📖 ข้อมูลชุดข้อมูล (Dataset Overview)

* **ชื่อชุดข้อมูล:** Estimation of Obesity Levels Based On Eating Habits and Physical Condition
* **แหล่งที่มา:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/544/estimation+of+obesity+levels+based+on+eating+habits+and+physical+condition)
* **ขนาดข้อมูลดิบ:** 2,111 แถว, 17 คอลัมน์
* **ขนาดข้อมูลหลังทำความสะอาด (Cleaned Data):** **2,087 แถว** (ตัดข้อมูลซ้ำซ้อนออก 24 แถว), **0 Missing Values**
* **ขนาดฟีเจอร์หลังทำ One-Hot Encoding:** **23 คอลัมน์** (ปรับสเกลด้วย `StandardScaler`)
* **ตัวแปรเป้าหมาย (Target):** `NObeyesdad` (จำแนกออกเป็น 7 ระดับ)

---

## 🗂️ พจนานุกรมข้อมูล (Data Dictionary)

| ชื่อตัวแปร (Feature) | ประเภทข้อมูล | ค่าที่เป็นไปได้ / ช่วงสเกล | คำอธิบายความหมาย |
| :--- | :---: | :--- | :--- |
| `Gender` | Categorical | `Male`, `Female` | เพศ |
| `Age` | Numerical | 14.00 – 61.00 ปี | อายุของผู้ตอบแบบสอบถาม |
| `Height` | Numerical | 1.45 – 1.98 เมตร | ส่วนสูง |
| `Weight` | Numerical | 39.00 – 173.00 กก. | น้ำหนักตัว |
| `family_history_with_overweight` | Categorical | `yes`, `no` | มีคนในครอบครัวมีประวัติน้ำหนักเกินหรือโรคอ้วน |
| `FAVC` | Categorical | `yes`, `no` | รับประทานอาหารแคลอรีสูงเป็นประจำ |
| `FCVC` | Numerical | 1.00 – 3.00 | ความถี่ในการกินผักในแต่ละมื้อ (1 = ไม่กิน, 3 = ประจำ) |
| `NCP` | Numerical | 1.00 – 4.00 | จำนวนมื้ออาหารหลักในแต่ละวัน |
| `CAEC` | Categorical | `no`, `Sometimes`, `Frequently`, `Always` | การกินขนม/ของจุกจิกระหว่างมื้ออาหาร |
| `CH2O` | Numerical | 1.00 – 3.00 | ปริมาณน้ำดื่มต่อวัน (1 = <1 ลิตร, 3 = >2 ลิตร) |
| `CALC` | Categorical | `no`, `Sometimes`, `Frequently`, `Always` | ความถี่ในการดื่มเครื่องดื่มแอลกอฮอล์ |
| `SCC` | Categorical | `yes`, `no` | มีการนับหรือควบคุมปริมาณแคลอรีที่บริโภค |
| `FAF` | Numerical | 0.00 – 3.00 | ความถี่ในการออกกำลังกายต่อสัปดาห์ |
| `TUE` | Numerical | 0.00 – 2.00 | ระยะเวลาใช้งานหน้าจอหรืออุปกรณ์ไอทีต่อวัน |
| `SMOKE` | Categorical | `yes`, `no` | พฤติกรรมการสูบบุหรี่ |
| `MTRANS` | Categorical | `Automobile`, `Bike`, `Motorbike`, `Public_Transportation`, `Walking` | ยานพาหนะหลักที่ใช้ในการเดินทาง |
| `NObeyesdad` | Categorical | 7 กลุ่ม (เป้าหมาย) | ระดับภาวะน้ำหนักตัวและโรคอ้วน |

### 🎯 รายละเอียดตัวแปรเป้าหมาย (`NObeyesdad`)

| ลำดับ | Class Label | ความหมายทางการแพทย์ | จำนวนข้อมูล (Cleaned) |
| :---: | :--- | :--- | :---: |
| 1 | `Insufficient_Weight` | น้ำหนักต่ำกว่าเกณฑ์มาตรฐาน | 267 |
| 2 | `Normal_Weight` | น้ำหนักตัวอยู่ในเกณฑ์ปกติ | 282 |
| 3 | `Overweight_Level_I` | ภาวะน้ำหนักเกิน ระดับที่ 1 | 276 |
| 4 | `Overweight_Level_II` | ภาวะน้ำหนักเกิน ระดับที่ 2 | 290 |
| 5 | `Obesity_Type_I` | โรคอ้วน ระดับที่ 1 | 351 |
| 6 | `Obesity_Type_II` | โรคอ้วน ระดับที่ 2 | 297 |
| 7 | `Obesity_Type_III` | โรคอ้วน ระดับที่ 3 | 324 |

---

## 🏆 ผลการทดลองและเปรียบเทียบแบบจำลอง (Key Findings & Results)

จากการประเมินประสิทธิภาพด้วยกระบวนการ **5-Fold Stratified Cross-Validation** และการใช้ Scikit-learn Pipeline สำหรับขั้นตอนที่ต้องปรับสเกลข้อมูล สามารถสรุปผลได้ดังนี้:

| โมเดล (Classification Model) | Mean CV Accuracy | Standard Deviation (±) | Test Accuracy | Macro F1-Score |
| :--- | :---: | :---: | :---: | :---: |
| 🌲 **Random Forest Classifier (Best Model)** | **94.59%** | **±1.54%** | **-** | **-** |
| 📈 Logistic Regression (Multi-class) | 87.11% | ±1.08% | 89.23% | 0.89 |
| 📍 K-Nearest Neighbors (k=5) | 79.78% | ±1.60% | 80.86% | 0.80 |

> **สรุปผลการทดลอง:**  
> Random Forest Classifier ให้ **Mean 5-Fold CV Accuracy สูงที่สุดในการทดลองนี้** ที่ 94.59% (±1.54%) จากโมเดลที่นำมาเปรียบเทียบ โดยความสามารถของ Ensemble Learning ช่วยลดความแปรปรวนของการทำนาย และรองรับความสัมพันธ์แบบไม่เป็นเชิงเส้นระหว่าง Features ได้

---

## 📁 โครงสร้างโปรเจกต์ (Repository Structure)

```text
math-ds-obesity-project/
├── data/
│   └── obesity_lifestyle_health.csv       # ชุดข้อมูลที่ใช้ในโครงงาน
├── notebooks/
│   └── obesity_lifestyle_final_project.ipynb  # Jupyter Notebook ฉบับสมบูรณ์ (Part 1 - 6)
├── requirements.txt                       # ไลบรารีและเวอร์ชันที่ใช้ในโครงงาน
└── README.md                              # รายละเอียดโครงงาน
```

---

## ⚙️ วิธีการติดตั้งและรันโค้ด (Getting Started)

### 1. Clone Repository
```bash
git clone https://github.com/kasemsakKK06/math-ds-obesity-project.git
cd math-ds-obesity-project
```

### 2. สร้างและเปิดใช้งาน Virtual Environment
```bash
python -m venv venv

# สำหรับ Windows PowerShell:
.\venv\Scripts\Activate.ps1

# สำหรับ macOS / Linux:
source venv/bin/activate
```

### 3. ติดตั้งไลบรารีที่จำเป็น
```bash
pip install notebook numpy pandas scipy matplotlib seaborn scikit-learn statsmodels
```

หรือ 

```bash
pip install -r requirements.txt
```

> กรณีมีไฟล์ `requirements.txt`


### 4. เปิดใช้งาน Jupyter Notebook
```bash
jupyter notebook
```

---