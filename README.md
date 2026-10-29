# Hanoi Roadster Rocket (bản MOD)

Bản sao của [teslaroadstertest](https://github.com/toilalode/teslaroadstertest) có kèm thêm `mod.js`.

Game lái Tesla Roadster (gói SpaceX) qua Hà Nội: 10 km, 15 phút, ngã tư, trạm Supercharger, bay, lộn né, bám tường.

Chạy tại: https://toilalode.github.io/teslaroadstertestmod/

## Bản MOD

`mod.js` được nạp sau `js/main.js` trong `index.html`. Trên màn hình có nút **MOD** (kéo thả được, vị trí được nhớ), bấm vào để mở bảng:

| Tùy chọn | Tác dụng |
| --- | --- |
| Bất tử | Không va chạm, không bị CSGT |
| No clip | Xuyên tường, rào, xe cộ, ra ngoài đường |
| Năng lượng vô hạn | Q / E / R / F luôn đầy |
| Không bị hết giờ | Đồng hồ không chạy quá hạn |
| Tự thắng khi vào game | Vào game là thắng ngay |
| 🚀 CHẠY SIÊU TỐC (BOOST x2) | Nút bật/tắt. Chỉ tăng tốc khi người chơi đang di chuyển (giữ W / ga / joystick tiến), đứng yên thì xe không tự chạy. Tốc độ thường tối đa ~324 km/h; Rocket Boost (Q) gấp đôi bản gốc: gia tốc 45 → 90, trần 70 → 140 m/s (~504 km/h) |

Trạng thái MOD lưu trong `localStorage` (`hrr3d_mod`, `hrr3d_modpos`). Muốn chơi bản gốc, xóa dòng `<script src="mod.js"></script>` trong `index.html`.

## Cấu trúc

| Tệp | Vai trò |
| --- | --- |
| `index.html` | Khung trang, nạp Three.js r128 từ cdnjs, các module trong `js/` rồi `mod.js` |
| `mod.js` | Bản MOD: vá `update()`, `hitCheck()`, `viol()` và thêm giao diện MOD |
| `style.css` | Giao diện HUD, popup, nút cảm ứng |
| `js/config.js` | Hằng số tuyến đường, hàm tiện ích, cài đặt mặc định |
| `js/scene.js` | Renderer, cảnh, ánh sáng, hàm dựng khối |
| `js/vehicles.js` | Xe giao thông và mô hình Tesla Roadster SpaceX |
| `js/city.js` | Đường, nhà, ngã tư, trạm sạc, công trường, công ty |
| `js/state.js` | Trạng thái, sinh xe, va chạm, cảnh sát, kỹ năng |
| `js/autopilot.js` | Tự lái (bật/tắt, phím T): giữ làn, né xe, dừng đèn đỏ, tự sạc mỗi 2000 m, tự rẽ vào công ty |
| `js/physics.js` | Vật lý, va chạm, giao thông |
| `js/hud.js` | Camera, HUD, bản đồ nhỏ |
| `js/screens.js` | Menu, Settings, màn kết thúc |
| `js/input.js` | Bàn phím, cảm ứng, chuột |
| `js/main.js` | Vòng lặp chính |
| `sw.js`, `manifest.json`, `icon.svg` | PWA, chạy offline |
| `.github/workflows/pages.yml` | Triển khai GitHub Pages |

## Bật GitHub Pages

Settings > Pages > Build and deployment > Source: **GitHub Actions**, rồi chạy lại workflow.
