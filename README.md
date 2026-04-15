[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574106&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** AI20K-2A202600323
**Student Email:** trhndan21@gmail.com
**Name:** Trinh Duc An

---

## Mo ta

Bài lab này xây dựng một pipeline ETL tự động để xử lý dữ liệu sản phẩm từ file JSON, bao gồm các bước extract, validate, transform và load. Tôi đã hoàn thành việc viết code ETL trong solution.py, thực hiện stress test với agent simulation trên dữ liệu sạch và rác, và ghi lại kết quả trong experiment_report.md để phân tích tác động của chất lượng dữ liệu đến hiệu suất AI agent.

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
python agent_simulation.py
```
Script sẽ chạy agent với dữ liệu sạch (processed_data.csv) và dữ liệu rác (garbage_data.csv), in ra kết quả để so sánh độ chính xác.

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

Pipeline đã xử lý thành công 3 records hợp lệ từ dữ liệu gốc, loại bỏ 2 records không hợp lệ (1 record có giá <= 0, 1 record thiếu category). Dữ liệu sạch được lưu vào processed_data.csv với các cột đã được transform: discounted_price (giảm 10%), category chuẩn hóa Title Case, và timestamp processed_at.
