# VNOC5 Stream Kit & Guide

## Những file cần thiết
- Streamer Kit: pinned message trong chat stream
- tosu và các file liên quan của overlay đã có trong stream kit

## Lưu ý hơi quan trọng
- osu! client size 1080P -> màn 1080p hoặc nhỏ hơn sẽ không hiển thị được. Streamer cần setting upscale màn để stream (với driver NVIDIA thì có DSR, AMD thì idk, chi tiết vui lòng hỏi trong chat streamer)
- Toàn bộ stream VNOC yêu cầu PHẢI có local record sau mỗi stream.
  - Streamer cần vào settings OBS -> General -> Automatically record when streaming
- tải file zip profile đã pin và giải nén vào `/Assets/OBS files`

## Setup overlay
- Giải nén stream kit vào đâu cũng được **TRỪ Ổ `C:`**
- tosu overlay: chạy thẳng instance trong `/Assets/_tosu`
- Copy các file cfg & skins cho client stream trong folder `osu files`
- Cài đặt font (nhớ chọn `Install for all user`)
- Cài đặt plugin Advanced Scene Switcher trong folder `OBS files`
- Trong OBS:
  - Scene Collection -> Import -> kéo thả file `VNOC5.json` trong `/Assets/OBS files` vào và chọn import
  - Profile -> Import -> chọn folder đã giải nén trong zip VNOC5_Streamer_PROFILE mới tải về
- Active profile VNOC5 Streamer và sửa stream key cũng như check lại 1 số setting cơ bản
  - Vào Settings -> Audio -> kéo xuống tìm Monitoring Device ->  
- Sửa lại setting audio device trong các scene AUDIO
  - caster only: chọn app Discord
  - gameplay: chọn Tournament Client 0
  - streamer mic _(chỉ những streamer có role caster)_: chọn lại đúng device mic và kiểm tra xem có filter chưa (chuột phải -> filters -> nếu thấy có filter noise reduction thì ok)
- Nếu báo lỗi missing files:
  - starting soon.png: kệ nó, xoá luôn
  - sponsor.png: ở trong `/Assets/_tosu/static/VNOC5/static`

## Stream procedure
- **thứ tự mở app vô cùng quan trọng!!!!** client -> tosu -> controller -> obs
- mở controller trong `/StreamKit/_controller/vcl_server.exe` (lần đầu mở thì windows sẽ có thông báo firewall gì đó, nhớ bấm allow)
- trong controller -> config thứ tự ban pick (check chat streamer để có số lượt protect ban pick cho mỗi round)
- khi tới lượt hành động của player nào thì chọn slot tương ứng
- nếu chọn sai map trong slot, click chuột phải vào slot đó để reset
- NẾU controller panik, nhấn nút Reset để làm lại từ đầu

## Lưu ý về chuyển scene OBS
- Trừ countdown, scene mở đầu trận đấu sẽ **luôn luôn** là mappool
- Chỉ chuyển qua scene Gameplay **khi cả 2 client player đã load map xong** - streamer cần dùng Studio Mode để theo dõi scene

## Nếu overlay lỗi
😂
