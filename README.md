# 🏡 การพยากรณ์ราคาบ้านด้วย Machine Learning

โปรเจกต์นี้เป็นการสร้างโมเดล Machine Learning เพื่อ **พยากรณ์ราคาบ้าน** จากคุณลักษณะต่าง ๆ ของบ้าน โดยใช้ชุดข้อมูลจากการแข่งขัน  
📍 [Housing Prices Competition for Kaggle Learn Users](https://www.kaggle.com/competitions/home-data-for-ml-course/overview)

🎓 โปรเจกต์นี้เป็นส่วนหนึ่งของคอร์สเรียนฟรี จาก kaggle: [Learn](https://www.kaggle.com/learn)

**เครื่องมือที่ใช้:** Python, Pandas, Scikit-learn, Matplotlib

---

## 📦 ข้อมูลที่ใช้

- `train.csv` – มีราคาบ้าน (`SalePrice`) สำหรับการฝึกโมเดล
- `test.csv` – ไม่มี `SalePrice` ใช้สำหรับทดสอบโมเดล
- ชุดข้อมูลนี้ประกอบด้วยฟีเจอร์ต่าง ๆ เช่น: `OverallQual`, `YearBuilt`, `GrLivArea`, `GarageArea`, ฯลฯ

---

## 🎯 เป้าหมาย

เข้าใจการสร้างโมเดลที่สามารถทำนายราคาบ้านได้
โดยวัดผลด้วย **Root Mean Squared Error (RMSE)**  
`เป้าหมายเชิงการเรียนรู้คือ` **ฝึกการเตรียมข้อมูล เลือกฟีเจอร์ และฝึกโมเดลเบื้องต้น**

---

## ✅ ขั้นตอนที่ดำเนินการ

1. โหลดข้อมูล
2. ตรวจสอบค่าว่าง (Missing Values)
3. วิเคราะห์ความสัมพันธ์กับราคาบ้าน
4. เลือกเฉพาะฟีเจอร์ที่สำคัญและไม่มี missing
5. สร้างโมเดล Random Forest
6. ประเมินด้วย MAE (Mean Absolute Error) บน validation set
7. ทำนายราคาบ้านและสร้าง submission.csv สำหรับ Kaggle

---

## 🧠 โมเดลที่ใช้

- **Random Forest Regressor**
- ฟีเจอร์ที่เลือกใช้:

```python
['OverallQual', 'GrLivArea', 'GarageCars', 'GarageArea',
 'TotalBsmtSF', '1stFlrSF', 'FullBath', 'TotRmsAbvGrd',
 'YearBuilt', 'YearRemodAdd']
```

## 📊 การประเมินผล

| รายการ                | ค่าที่ได้                      |
| --------------------- | ------------------------------ |
| MAE บน validation set | 18,582.44                      |
| Public Score (Kaggle) | 18,619.90 RMSE                 |
| โมเดล                 | Random Forest                  |
| Cross-validation      | train_test_split (holdout set) |

## 📁 โครงสร้างไฟล์

```
├── train.csv
├── test.csv
├── notebook.ipynb
├── submission.csv
├── requirements.txt
├── .gitignore
└── README.md
```

## 🧪 วิธีใช้งาน

1. ติดตั้ง dependencies

```bash
pip install -r requirements.txt
```

2. เปิด notebook

```
jupyter notebook
```

3.เปิดไฟล์ `notebook.ipynb` และรันทุกเซลล์
เพื่อฝึกโมเดล, ประเมินผล และสร้างไฟล์ `submission.csv` สำหรับ Kaggle

##

📝 หมายเหตุ: ไฟล์ `train.csv` และ `test.csv` ไม่ได้รวมใน repo นี้ กรุณาโหลดจาก

> 📍 [Housing Prices Competition for Kaggle Learn Users](https://www.kaggle.com/competitions/home-data-for-ml-course/overview)

## ผู้จัดทำ

ชื่อ: Watcharapong Rodpong
