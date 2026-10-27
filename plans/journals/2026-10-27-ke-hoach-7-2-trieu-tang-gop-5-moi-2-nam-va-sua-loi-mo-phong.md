---
title: "Kế hoạch 7,2 triệu: tăng góp 5% mỗi 2 năm và sửa lỗi mô phỏng"
date: 2026-10-27
summary: "Thêm hệ số tăng góp 5%/24 tháng, sửa 6 lỗi code trong ke-hoach-phan-bo-7-2-trieu.html"
---

# Kế hoạch 7,2 triệu: tăng góp 5% mỗi 2 năm và sửa lỗi mô phỏng

## What happened
- Rà soát ke-hoach-phan-bo-7-2-trieu.html: công thức lãi tháng, giá nhà, mục tiêu hưu đều đúng; số trong văn bản khớp code.
- Vấn đề chính của kế hoạch: góp cố định 7,2 triệu trong 34 năm, nhà chỉ đủ 05/2061 (sau tuổi 62), quỹ hưu thiếu 4,64 tỷ (10%).
- Người dùng chọn tăng tổng góp 5% mỗi 2 năm (tăng kép, chia theo tỷ lệ cũ, lần đầu 11/2028).

## Changes
- budgetScale(idx) = 1,05^floor(idx/24) áp cho dài hạn, trần dự phòng, nhà; ngân sách tháng, tổng phân bổ, cột Tổng hiển thị theo x.total.
- Sửa lỗi: lãi nhà âm sau khi rút quỹ (reset housePaid), nhãn giai đoạn "Dồn quỹ hưu" sau xây nhà, thẻ Nghỉ hưu tính mốc theo kịch bản 10%/8%, quỹ dài hạn dùng lãi riêng (không mượn biến lãi nhà), bỏ số gán cứng (tiền chưa chi, ngày mua, mục tiêu hưu viết 2 lần, đoạn ví dụ 05/2061 thay bằng houseNote tự tính), đổi "Sự cố" thành "Dự phòng".
- Cột Mục tiêu nhà hiện "Đã xây" sau mốc; tiến độ nhà giữ giá trị lúc rút.

## Result (lãi dự phòng 4%)
- Dự phòng đủ 03/2030; nhà đủ 07/2057 (~58,8 tuổi).
- Dài hạn ở 62: 15,66 tỷ (10%) thiếu 1,2 tỷ; 10,5 tỷ (8%) thiếu 6,3 tỷ so với 16,86 tỷ.

## Verification
- Node + DOM giả: tổng phân bổ = 7,2 × hệ số mọi tháng, không ô âm trong bảng năm, nhãn/goal đúng quanh mốc nhà, đổi lãi 0%/6% và kịch bản 8% chạy được.
- Chrome headless: trang render, không lỗi JS.

## Next steps
- Chốt mức chi thật (14,8 hay 18 triệu), giả định 2,5 tỷ có gồm đất, có tính lương hưu BHXH.

> Historical work record - not durable authority. Prefer docs/specs/ADRs for current decisions.
