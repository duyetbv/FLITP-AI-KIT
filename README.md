Quy tắc chung
AGENTS.md: quy tắc cho mọi công cụ AI (Claude Code, Cursor, Copilot, Codex). Nội dung gồm:
Bản đồ 22 module và thuật ngữ nghiệp vụ (RFP, F1/F2/F3, 3387, EPE).
Danh sách việc cấm: đọc odoo.conf và 3 file dữ liệu thật *.json, gọi API M-invoice thật, push, deploy.
Quy ước code Odoo 18, rút từ chính các lỗi trong báo cáo audit.
Mỗi thay đổi bắt buộc có test, quyền truy cập, bản dịch vi_VN và tăng version.
Mức dùng AI theo tracker, và quy định với module dùng chung.
CLAUDE.md: nạp AGENTS.md, cộng thêm vài lưu ý riêng cho Claude Code.
CLAUDE.md riêng trong 4 module tlip_approval, tlip_access_rights, pcv_minvoice, tlip_account. Mỗi file ghi phạm vi ảnh hưởng, các lỗi audit liên quan, và hạng mục nào AI không được viết logic lõi.
docs/ai/AI_USAGE.md: quy định cho cả team. Gồm checklist xin TLIP đồng ý, danh sách dữ liệu cấm đưa vào AI, các cổng kiểm soát, và bảng đo thí điểm Đợt 1.
thư mục .claude. Gồm:
odoo-feature: làm một hạng mục từ tracker đến merge request. Skill tự đọc dòng tương ứng trong tracker.
odoo-test: mẫu test Odoo 18 và các loại test bắt buộc.
fix-audit-finding: bảng đủ 25 lỗi audit, kèm vị trí và cách sửa nhỏ nhất.
shared-module-review: checklist cho pod Core, có danh sách 20 model đang dùng chung luồng duyệt.
settings.json: chặn đọc file bí mật và chặn push/deploy.
