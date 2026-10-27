# Goals

Trang kế hoạch tài chính cá nhân bằng HTML/CSS/JavaScript thuần.

- [Mở ứng dụng](ke-hoach-phan-bo-7-2-trieu.html) trong trình duyệt để chạy tại máy.
- [Deploy Goals lên VPS](docs/goals-prod-deploy-runbook.html): chuẩn bị, triển khai, kiểm tra, cập nhật và rollback.

Repo: `https://github.com/congvu99/Goals.git`, nhánh `main`. Không cần dependencies, build, backend hoặc database. Các lựa chọn trên giao diện hiện không được lưu bền vững.

Môi trường dự kiến: `/srv/apps/goals`, domain `goals.congvu.duckdns.org`, Caddy dùng chung trên VPS. Kiểm tra IP, domain và mount Caddy trước khi triển khai theo runbook. Push GitHub không tự deploy lên VPS.
