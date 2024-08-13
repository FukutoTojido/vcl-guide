# VNOC5 Stream Kit & Guide

## Những file cần thiết
- Streamer Kit: trong mục [Releases](https://github.com/FukutoTojido/vcl-guide/releases)
- Snaz (dùng để countdown) cái này tương lai sẽ không cần
- [tosu](https://github.com/KotRikD/tosu)

## Setup overlay
- Giải nén stream kit vào đâu cũng được **TRỪ Ổ `C:`**
- tosu overlay: copy folder `VNOC5` trong `/StreamKit/tosu_overlay` vào `/tosu/static/`
- Cài đặt font (nhớ chọn `Install for all user`)
- Mở OBS -> Scene Collection -> Import -> kéo thả file `VNOC5.json` trong `/StreamKit/OBS` vào và chọn import
- Sửa lại setting audio device trong các scene AUDIO
  - caster only: chọn app Discord
  - gameplay: chọn Tournament Client 0
  - streamer mic _(chỉ những streamer có role caster)_: chọn lại đúng device mic và kiểm tra xem có filter chưa (chuột phải -> filters -> nếu thấy có filter noise reduction thì ok)

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
- 

## Nếu overlay lỗi
😂
