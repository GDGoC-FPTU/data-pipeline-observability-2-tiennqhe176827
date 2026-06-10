[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112866&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** AI20K-0262
**Name:** Nguyen Quoc Tien

---

## Mo ta

Xay dung ETL pipeline doc du lieu tu raw_data.json, loai bo cac record khong hop le (gia <= 0, category rong), chuan hoa category sang Title Case, tinh discounted_price (giam 10%), va them timestamp processed_at. Sau do xuat ra file processed_data.csv. Thuc hien stress test voi agent_simulation.py de so sanh chat luong phan hoi giua du lieu sach va du lieu rac.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python generate_garbage.py
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

- 5 records doc tu raw_data.json
- 2 records bi loai (Mystery Box: price=-10, Phone: category="")
- 3 records hop le duoc xu ly (Laptop, Chair, Monitor)
- Clean data: Agent tra loi chinh xac (Laptop $1200)
- Garbage data: Agent bi danh lung boi outlier (Nuclear Reactor $999999)
