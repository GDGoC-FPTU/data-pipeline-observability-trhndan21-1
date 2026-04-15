# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600323
**Name:** Trinh Duc An
**Date:** 15-4-2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 10 | Agent trả lời chính xác dựa trên dữ liệu sạch, chọn sản phẩm điện tử đắt nhất hợp lý. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Agent chọn outlier không hợp lý do dữ liệu rác chứa giá trị ngoại lệ và lỗi. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi sử dụng dữ liệu rác (garbage_data.csv), agent trả lời sai vì dữ liệu chứa nhiều vấn đề chất lượng nghiêm trọng. Cụ thể, dữ liệu có duplicate IDs (hai record có id=1), wrong data types (price là string "ten dollars" thay vì số), outliers (Nuclear Reactor với giá 999999 không hợp lý), và null values (thiếu id và category ở một số record). Những lỗi này làm cho agent không thể xử lý đúng logic tìm sản phẩm điện tử đắt nhất, dẫn đến chọn Nuclear Reactor là "best choice" thay vì Laptop hợp lý. Điều này chứng minh rằng dữ liệu chất lượng kém có thể làm sai lệch kết quả của AI agent, gây ra quyết định sai lầm trong ứng dụng thực tế.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Đồng ý hoàn toàn. Dữ liệu chất lượng cao quan trọng hơn prompt chất lượng vì ngay cả prompt tốt nhất cũng không thể bù đắp cho dữ liệu sai lệch, thiếu hoặc lỗi. Trong thí nghiệm này, cùng một prompt nhưng dữ liệu rác dẫn đến kết quả sai, chứng minh rằng nền tảng dữ liệu vững chắc là yếu tố quyết định cho độ tin cậy của AI agent.
