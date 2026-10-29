# TLIP Main – AI Development Guidelines

## 1. Mục đích

Repository này chứa bộ quy tắc, tài liệu và AI Skills dùng chung cho dự án TLIP.

Mục tiêu chính:

- **Consistent Code:** Đảm bảo code được viết theo cùng một tiêu chuẩn trên toàn bộ các module.
- **Consistent Testing:** Thống nhất cách viết test case, test coverage và tiêu chí nghiệm thu.
- **Shared Knowledge:** Giúp tất cả thành viên và AI coding tools sử dụng cùng một nguồn thông tin.
- **Quality Control:** Hạn chế lỗi đã được phát hiện trong các đợt audit trước đó.
- **Safe AI-Assisted Development:** Đảm bảo việc sử dụng AI tuân thủ các quy định về bảo mật, quyền truy cập và quy trình phát triển.

Tất cả thành viên tham gia phát triển TLIP cần tuân thủ các hướng dẫn trong repository này.

## 2. Repository Structure

Các tài liệu và cấu hình chính bao gồm:

| File / Directory | Purpose |
|---|---|
| `AGENTS.md` | Quy tắc phát triển chung áp dụng cho tất cả AI coding tools. |
| `CLAUDE.md` | Hướng dẫn bổ sung dành riêng cho Claude Code, đồng thời tham chiếu `AGENTS.md`. |
| `tlip_approval/CLAUDE.md` | Hướng dẫn AI khi làm việc với module `tlip_approval`. |
| `tlip_access_rights/CLAUDE.md` | Hướng dẫn AI khi làm việc với module `tlip_access_rights`. |
| `pcv_minvoice/CLAUDE.md` | Hướng dẫn AI khi làm việc với module `pcv_minvoice`. |
| `tlip_account/CLAUDE.md` | Hướng dẫn AI khi làm việc với module `tlip_account`. |
| `docs/ai/AI_USAGE.md` | Chính sách sử dụng AI cho toàn team. |
| `.claude/skills/odoo-feature/` | Workflow phát triển feature từ tracker đến merge request. |
| `.claude/skills/odoo-test/` | Hướng dẫn viết và kiểm tra test cho Odoo 18. |
| `.claude/skills/fix-audit-finding/` | Hướng dẫn xử lý các lỗi được ghi nhận trong audit. |
| `.claude/skills/shared-module-review/` | Checklist review các module và model dùng chung. |
| `.claude/settings.json` | Cấu hình giới hạn quyền truy cập và các thao tác nguy hiểm trong Claude Code. |

Vui lòng kiểm tra cấu trúc thực tế của repository nếu có thay đổi về tên file hoặc vị trí thư mục.

## 3. Development Rules

### 3.1. Follow the shared instructions

Trước khi bắt đầu một task:

1. Đọc `AGENTS.md`.
2. Đọc `CLAUDE.md` nếu sử dụng Claude Code.
3. Kiểm tra `CLAUDE.md` riêng của module nếu task liên quan đến một trong bốn module có hướng dẫn riêng.
4. Đọc `docs/ai/AI_USAGE.md` để hiểu các quy định về bảo mật và sử dụng AI.
5. Sử dụng AI Skills phù hợp với loại công việc.

Không tự ý bỏ qua các quy tắc chung hoặc các giới hạn đã được xác định cho module.

### 3.2. Keep the code consistent

Mọi thay đổi cần tuân thủ:

- Coding conventions dành cho Odoo 18.
- Quy ước kiến trúc và nghiệp vụ hiện có.
- Các quy định về access rights và security.
- Quy ước bản dịch tiếng Việt `vi_VN`.
- Quy trình cập nhật version.
- Các yêu cầu kiểm thử tương ứng với thay đổi.

Không tự ý thay đổi logic nghiệp vụ cốt lõi, đặc biệt tại các module dùng chung, nếu chưa được người có trách nhiệm phê duyệt.

### 3.3. Testing is mandatory

Mỗi thay đổi cần có test phù hợp trước khi được đề xuất merge.

Tùy theo phạm vi ảnh hưởng, cần kiểm tra:

- Functional behavior.
- Positive và negative test cases.
- Access rights và security.
- Các trường hợp biên và dữ liệu không hợp lệ.
- Regression trên các luồng nghiệp vụ liên quan.
- Ảnh hưởng đến các module hoặc model dùng chung.

Sử dụng `.claude/skills/odoo-test/` để tham khảo mẫu và checklist kiểm thử.

Test case cần phản ánh đúng yêu cầu nghiệp vụ, có thể tái sử dụng và nhất quán giữa các thành viên.

### 3.4. Security and restricted operations

Tuân thủ nghiêm ngặt các giới hạn được quy định trong `AGENTS.md`, `docs/ai/AI_USAGE.md` và `.claude/settings.json`.

Đặc biệt:

- Không đọc `odoo.conf` hoặc ba file dữ liệu JSON thật được quy định trong hướng dẫn.
- Không gọi API M-invoice production thật.
- Không tự ý push code hoặc deploy.
- Không đưa dữ liệu nhạy cảm hoặc thông tin bí mật vào AI tools.
- Không tự ý thay đổi các cơ chế phân quyền hoặc logic nghiệp vụ được bảo vệ.

Các thao tác cần phê duyệt phải được thực hiện theo đúng quy trình của dự án.

## 4. AI Skills

AI Skills được cung cấp để chuẩn hóa workflow, tránh việc mỗi thành viên yêu cầu AI theo một cách khác nhau.

| Skill | When to use |
|---|---|
| `odoo-feature` | Phát triển feature theo tracker, từ phân tích yêu cầu đến kiểm thử và chuẩn bị merge request. |
| `odoo-test` | Viết mới, bổ sung hoặc review test case. |
| `fix-audit-finding` | Xử lý các vấn đề đã được xác định trong audit. |
| `shared-module-review` | Review thay đổi có ảnh hưởng đến module hoặc model dùng chung. |

Khi có Skill phù hợp, hãy sử dụng Skill đó thay vì tự xây dựng một workflow riêng.

AI-generated code vẫn phải được developer kiểm tra, test và chịu trách nhiệm trước khi merge.

## 5. Change Management – Keep Everyone Updated

**Mọi thay đổi đối với quy tắc, test conventions, AI Skills hoặc workflow dùng chung phải được cập nhật để cả team sử dụng cùng một phiên bản hướng dẫn.**

Khi phát hiện một quy tắc chưa rõ, một lỗi lặp lại hoặc một cách xử lý tốt hơn:

1. Xác định tài liệu hoặc Skill liên quan.
2. Cập nhật nội dung tại đúng vị trí, tránh tạo các hướng dẫn trùng lặp hoặc mâu thuẫn.
3. Kiểm tra ảnh hưởng đến các module và workflow liên quan.
4. Cập nhật test hoặc checklist nếu thay đổi ảnh hưởng đến tiêu chuẩn kiểm thử.
5. Thông báo cho team về thay đổi, lý do và phạm vi ảnh hưởng.
6. Đề xuất review và merge theo quy trình của repository.

Không chỉ sửa trong một cuộc hội thoại với AI hoặc trên máy cá nhân. Những quy tắc đã được thống nhất cần được lưu trong repository để các thành viên khác có thể sử dụng lại.

Nếu thay đổi ảnh hưởng đến nhiều module, hãy kiểm tra và cập nhật tất cả tài liệu liên quan.

## 6. Pull Request / Merge Request Checklist

Trước khi đề xuất merge, hãy xác nhận:

- [ ] Đã tuân thủ `AGENTS.md` và hướng dẫn riêng của module.
- [ ] Đã sử dụng AI Skill phù hợp nếu có.
- [ ] Đã bổ sung hoặc cập nhật test case cần thiết.
- [ ] Đã kiểm tra access rights và security.
- [ ] Đã cập nhật bản dịch `vi_VN` khi cần thiết.
- [ ] Đã tăng version theo quy định khi cần thiết.
- [ ] Đã kiểm tra regression và ảnh hưởng đến module dùng chung.
- [ ] Không chứa dữ liệu nhạy cảm hoặc thao tác bị cấm.
- [ ] Đã cập nhật tài liệu và AI Skills nếu thay đổi làm ảnh hưởng đến quy tắc chung.
- [ ] Đã hoàn thành các bước review và phê duyệt cần thiết.

## 7. Team Collaboration

Repository này là nguồn tham chiếu chung cho quy tắc phát triển và sử dụng AI trong dự án TLIP.

Mỗi thành viên có trách nhiệm:

- Đọc và tuân thủ các hướng dẫn hiện hành.
- Giữ code và test case nhất quán với tiêu chuẩn của team.
- Chủ động cập nhật tài liệu khi phát hiện vấn đề hoặc cải tiến cần được chia sẻ.
- Thông báo cho các thành viên liên quan khi thay đổi ảnh hưởng đến workflow chung.
- Không tự ý thay đổi các quy tắc đã được thống nhất mà chưa thực hiện review cần thiết.

**The goal is simple: one shared set of rules, one consistent coding standard, and one consistent testing approach across the entire TLIP project.**
