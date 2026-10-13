# VansonMod

<p align="center">
  <img src="https://repository-images.githubusercontent.com/1109090336/135167c3-e943-48a9-aa0d-67b3c21e844d" alt="VansonMod Social Preview" width="100%"/>
</p>

**Trình chỉnh sửa bộ nhớ iOS, phân tích con trỏ, vá RVA và quản lý tiến trình cho TrollStore (jailbreak là tùy chọn). Hỗ trợ chỉnh Hex, quét giá trị và sao lưu/khôi phục**

[English](../README.md) | [简体中文](./README_CN.md) | [繁體中文](./README_TW.md) | [العربية](./README_AR.md) | [Deutsch](./README_DE.md) | [Español](./README_ES.md) | [Français](./README_FR.md) | [日本語](./README_JA.md) | [한국어](./README_KO.md) | [Português](./README_PT.md) | [Русский](./README_RU.md) | [ไทย](./README_TH.md) | **Tiếng Việt**

![Platform](https://img.shields.io/badge/Platform-iOS%2014.0%2B-black)
![Support](https://img.shields.io/badge/Support-TrollStore-blue)
![License](https://img.shields.io/badge/License-GPL--3.0-green)

> [![Join Telegram](https://img.shields.io/badge/Join-Telegram%20Channel-blue?logo=telegram&logoWidth=20&labelColor=26A5E4&color=white)](https://t.me/VansonMod)

---

## Giới thiệu

**VansonMod** là công cụ debug iOS độc lập dành cho môi trường **TrollStore**. Nó hoạt động từ bên ngoài thay vì phụ thuộc vào tweak injection truyền thống, vì vậy nhiều quy trình quen thuộc vẫn dùng được trên thiết bị không jailbreak, như chọn tiến trình, tìm kiếm bộ nhớ, duyệt bộ nhớ, phân tích và xác minh con trỏ, phân tích signature, script và quản lý sao lưu ứng dụng.

Trên thiết bị đã jailbreak, VansonMod còn mở rộng sang các quy trình mức mã nguồn sâu hơn như **RVA Patch** và **giám sát hardware watchpoint**. Ở phiên bản hiện tại, VansonMod không còn chỉ là công cụ quét bộ nhớ mà đã trở thành một workspace debug iOS hoàn chỉnh hơn.

## Tương thích

- **Dùng được trên TrollStore / không jailbreak**: chọn tiến trình, tìm kiếm bộ nhớ, nearby search, lọc kết quả, memory browser, Hex editor, phân tích và xác minh con trỏ, phân tích signature, script tools, quản lý backup và cài đặt giao diện/ngôn ngữ/icon.
- **Tính năng phụ thuộc task port của tiến trình mục tiêu**: một số tính năng runtime cần truy cập được task port của tiến trình mục tiêu; hành vi thực tế có thể thay đổi tùy theo môi trường và trạng thái app.
- **Khuyến nghị hoặc giới hạn cho môi trường jailbreak**: `RVA Patch`, `quản lý bản ghi RVA`, và `hardware watchpoint` phù hợp hơn với môi trường như **Dopamine / palera1n**.
- **Lý do**: trên thiết bị không jailbreak, **AMFI** kiểm tra chữ ký mã rất chặt. Việc sửa trực tiếp phân đoạn thực thi (`__TEXT`) thường sẽ khiến app mục tiêu crash ngay lập tức.

## Ngôn ngữ hỗ trợ

- Ngôn ngữ tích hợp: 简体中文, 繁體中文, English, العربية, Deutsch, Español, Français, 日本語, 한국어, Português, Русский, ไทย, Tiếng Việt.

## Điều hướng

- **App Selection**: xem tiến trình đang chạy, tất cả app đã cài hoặc tiến trình hệ thống; tìm theo tên / Bundle ID / PID; nhanh chóng attach, mở app, kill, backup hoặc xem thay đổi mã.
- **Memory Debug**: tìm kiếm exact, fuzzy, group, range và nearby, lọc kết quả, timeline tìm kiếm để khôi phục snapshot kết quả, hoàn tác lần ghi thủ công gần nhất, chỉnh sửa hàng loạt và chuyển sang dạng xem giá trị hoặc Hex.
- **RVA Debug**: áp dụng patch theo module và offset, đồng thời quản lý các bản ghi RVA.
- **Toolbox**: quản lý memory lock, favorites, pointer, RVA, signature, file verifier và script trong cùng một nơi.
- **Settings**: cấu hình giao diện, ngôn ngữ, icon, thứ tự tab, phạm vi tìm kiếm, float tolerance, giới hạn kết quả và kiểm tra cập nhật; cũng có thể sắp xếp lại tab nhanh bằng cách nhấn giữ menu dưới cùng.

## Điểm nổi bật

- **Quản lý tiến trình và ứng dụng**: hỗ trợ chế độ xem `Running / All / System`, tên app bản địa hóa, hiển thị phiên bản, gắn sao, sao chép PID / Bundle ID, mở app nhanh và kết thúc tiến trình.
- **Tìm kiếm bộ nhớ và chỉnh sửa hàng loạt**: exact, fuzzy, group, range, nearby search; snapshot timeline kèm khôi phục; hoàn tác ghi thủ công; bộ lọc lớn hơn / nhỏ hơn / trong khoảng; ghi giá trị cố định, sửa tăng dần, khóa hàng loạt và đánh dấu yêu thích hàng loạt.
- **Memory browser và Hex editor**: nhảy tới địa chỉ, tự động làm mới, xem chuỗi, sao chép hàng loạt địa chỉ; Hex editor hỗ trợ bố cục `Hex / Split / Text`, chỉnh theo dòng và nhảy theo offset.
- **Phân tích và xác minh con trỏ**: chuỗi con trỏ thủ công hoặc tự động, chế độ static / dynamic / all / backtrack, xác minh thời gian thực, so sánh snapshot và nhập/xuất file verifier.
- **Signature và script**: phân tích signature từ bất kỳ địa chỉ nào, chọn phạm vi module, tìm kiếm toàn cục và smart mask; runtime JavaScript tích hợp với hướng dẫn và ví dụ xem trực tiếp trong VM.
- **RVA, watchpoint và process audit**: chọn module, patch theo offset, preset ARM64 và quản lý RVA; trên máy jailbreak còn có hardware watchpoint. Process audit giúp xem vị trí mã hoặc giá trị RVA nào đã thay đổi trước và sau khi app mục tiêu chạy.
- **Trải nghiệm và cài đặt**: chuyển đổi theme, ngôn ngữ, icon, sắp xếp tab, phạm vi fuzzy search, tần suất lock, chống ngủ và hỗ trợ iPad split view, chế độ ngang và Stage Manager.

## Ảnh chụp màn hình

Xem trước giao diện v3.5. Các ứng dụng và dữ liệu được hiển thị đều là ví dụ minh họa.

| <div align="center"><img src="../Screenshots/APP_SELECT.PNG" width="100%" alt="Chọn tiến trình"/></div> | <div align="center"><img src="../Screenshots/MEM_DEBUG.PNG" width="100%" alt="Gỡ lỗi bộ nhớ"/></div> | <div align="center"><img src="../Screenshots/MEM_BROWSER.PNG" width="100%" alt="Trình duyệt bộ nhớ"/></div> | <div align="center"><img src="../Screenshots/MEM_HEX_MIX.PNG" width="100%" alt="Chế độ xem Hex hỗn hợp"/></div> |
| :---: | :---: | :---: | :---: |
| <div align="center"><img src="../Screenshots/POINTER_ANALYSIS.PNG" width="100%" alt="Phân tích con trỏ"/></div> | <div align="center"><img src="../Screenshots/POINTER_VERIFY.PNG" width="100%" alt="Xác minh con trỏ"/></div> | <div align="center"><img src="../Screenshots/POINTER_LOCKER.PNG" width="100%" alt="Khóa con trỏ"/></div> | <div align="center"><img src="../Screenshots/RVA_MANAGER.PNG" width="100%" alt="Trình quản lý RVA"/></div> |
| <div align="center"><img src="../Screenshots/SCRIPT_EDITOR.PNG" width="100%" alt="Trình chỉnh sửa tập lệnh"/></div> | <div align="center"><img src="../Screenshots/SCRIPT_CREATE.PNG" width="100%" alt="Tạo tập lệnh"/></div> | <div align="center"><img src="../Screenshots/SETTINGS.PNG" width="100%" alt="Cài đặt"/></div> | <div align="center"><img src="../Screenshots/SETTINGS_DARK.PNG" width="100%" alt="Cài đặt ở chế độ tối"/></div> |

---

## Dự Án Liên Quan

Đối với phiên bản dylib cho workflow runtime được inject, xem [VansonLoader](https://github.com/vaenshine/vansonloader), bản phái sinh companion dylib của VansonMod.

---

## Changelog

Xem tại [Releases](https://github.com/vaenshine/VansonMod/releases).

---

## Cài đặt

1. Tải tệp `.tipa` mới nhất từ [Releases](https://github.com/vaenshine/VansonMod/releases).
2. Cài bằng **TrollStore**.
3. Mở app, chọn tiến trình mục tiêu và bắt đầu debug.

---

## Build Tu Ma Nguon

Yeu cau: Theos, Xcode Command Line Tools, Python 3, `ar`, `tar`, `zip`, va `unzip`.

```sh
make clean package FINALPACKAGE=1 DEBUG=0
./scripts/release.sh
```

Xem quy tac dong gop tai [CONTRIBUTING](./CONTRIBUTING.md) va bao cao bao mat rieng tu tai [SECURITY](./SECURITY.md).

---

## Ghi nhận

*   Developer: **Vaenshine**
*   Special Thanks: **Gey1ist**, **Xiczee**, **Zoomin**
*   Community Support: [iOSGods.com](https://iosgods.com/)

---

## Miễn trừ trách nhiệm

Công cụ này dành cho **nghiên cứu bảo mật, học reverse engineering và kiểm thử kỹ thuật được cấp phép**. GPL-3.0 cho phép phân phối có thu phí khi bên phân phối tuân thủ đầy đủ giấy phép. Hãy sử dụng trong môi trường hợp pháp, được cấp phép và tuân thủ quy tắc áp dụng của app và hệ thống mục tiêu. Người dùng chịu trách nhiệm về thao tác, rủi ro và hậu quả pháp lý liên quan.

---

## Tuyên bố quan trọng

Dự án này là mã nguồn mở theo GPL-3.0. Việc phát triển dựa trên nghiên cứu kỹ thuật và trao đổi cộng đồng.

---

## License

GPL-3.0. See [LICENSE](./LICENSE).

## Phân phối và nhận diện dự án

Các bản phát hành VansonMod chính thức được cung cấp miễn phí trên trang [Releases](https://github.com/vaenshine/VansonMod/releases) của kho mã này.

Dự án khuyến khích truy cập miễn phí và chia sẻ miễn phí qua các nguồn chính thức. Việc bên thứ ba bán lại có thu phí các gói chính thức chưa sửa đổi không nhận được sự chứng thực, ủng hộ hoặc ủy quyền của người duy trì. Các quyền phân phối lại do GPL-3.0 cấp vẫn giữ nguyên.

GPL-3.0 cho phép bên thứ ba phân phối bản gốc hoặc bản sửa đổi có thu phí. Bên phân phối phải thực hiện đầy đủ các nghĩa vụ GPL-3.0 áp dụng, bao gồm giữ nguyên các thông báo bắt buộc, cung cấp giấy phép, cung cấp quyền truy cập vào toàn bộ mã nguồn tương ứng và ghi rõ các phiên bản đã sửa đổi.

Tên VansonMod, logo, biểu tượng app và nhận diện dự án chính thức là các dấu hiệu nhận diện dự án được bảo vệ. Bên phân phối thứ ba phải nêu rõ trạng thái độc lập, không chính thức và tránh mọi cách trình bày gợi ý sự ủy quyền, tài trợ, chứng thực hoặc liên kết với dự án hay người duy trì.

Xem [Chính sách nhãn hiệu và phân phối](../TRADEMARKS.md) để biết chi tiết.

---

## Star History

[![Star History Chart](https://api.star-history.com/chart?repos=vaenshine/VansonMod&type=date&legend=bottom-right&sealed_token=7GKlgSNa_RYfyFti6u-PKeTxObIt1P6yp9ExhaBjWXgxI78k9FV3xLprlOPWX_Rx4DkQRZ_ub-lWHoqPsTekAaDxkiZKMUhSqDuSCrqhTDn9cR8jQAE_pQ)](https://www.star-history.com/?repos=vaenshine%2FVansonMod&type=date&legend=bottom-right)
