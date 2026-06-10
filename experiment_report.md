# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-0262
**Name:** Nguyen Quoc Tien
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | "Based on my data, the best choice is Laptop at $1200." | 10 | Agent chon dung san pham electronics co gia cao nhat |
| Garbage Data (`garbage_data.csv`) | "Based on my data, the best choice is Nuclear Reactor at $999999." | 2 | Agent bi danh lung boi outlier (Nuclear Reactor gia 999999) |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi su dung Garbage Data, Agent tra loi sai vi du lieu dau vao chua nhieu van de ve chat luong. Dau tien, outlier voi gia tri 999999 (Nuclear Reactor) lam cho Agent nham tuong day la san pham electronics tot nhat, trong khi thuc te do la gia tri bat thuong. Thu hai, duplicate ID (id=1 xuat hien hai lan) gay nhieu cho viec truy van du lieu, co the dan den ket qua khong nhat quan. Thu ba, wrong data type (price la "ten dollars" thay vi so) khien xu ly du lieu gap loi va mat thong tin. Cuoi cung, null values (id=None, category=None) co the gay ra loi RuntimeError trong qua trinh doc file. Tat ca nhung van de nay lam cho Agent khong the dua ra cau tra loi chinh xac, chung minh rang du lieu sach co vai tro quyet dinh den hieu qua cua AI Agent.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Mot prompt tot khong the bu dap cho du lieu dau vao kem chat luong. Neu du lieu bi outlier, null, sai kieu hoa cau truc, Agent se dua ra cau tra loi sai bat ke prompt co duoc viet tinh te den dau. Do do, dam bao chat luong du lieu la uu tien hang dau de co ket qua AI tin cay.
