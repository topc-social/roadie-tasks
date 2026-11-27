# Which dashcams let you pull clips without the brand's app

Research for Roadie (dashcam footage straight to your own cloud), done 14 Nov 2026. For each dashcam brand sold in India: can a script or your own app download the raw clips without the brand's app, and can the camera join an outside Wi-Fi network (station mode), so a phone or small box can collect clips on its own?

- **open**: an open-source tool or a documented way exists
- **likely**: works only with workarounds or on some firmware
- **unknown**: no evidence either way; only the brand's own app is documented

| Brand | Rating | Joins outside Wi-Fi | How |
|---|---|---|---|
| VIOFO | open | yes (A329, A229 series, A139/Pro, A119 Mini 2, A119M Pro, A129 Duo) | Files served over HTTP at 192.168.1.254, or at its home-network address in station mode. Maintained tools: [RobXYZ/viofosync](https://github.com/RobXYZ/viofosync), [steve192/dashcam-transporter](https://github.com/steve192/dashcam-transporter). VIOFO documents browser download itself. |
| BlackVue | open | yes (via its Cloud hotspot settings) | Joins your Wi-Fi; file list at `blackvue_vod.cgi` (older firmware) or `/vodList` (newer). Maintained tool: [acolomba/blackvuesync](https://github.com/acolomba/blackvuesync). |
| DDPAI | open | not found | Local API on the camera's own Wi-Fi: session token, playback list, file download. Tools: [hansaya/ddpai_downloader](https://github.com/hansaya/ddpai_downloader) (Mini 5), [awexandrr/ddpai-api](https://github.com/awexandrr/ddpai-api). |
| 70mai | likely | no, on stock firmware | A reverse-engineering write-up on the A500S found plain HTTP at 192.168.0.1 and FTP; auto-sync tools need custom firmware. |
| Thinkware | likely (F800, F800 Pro, Q800 Pro on older firmware) | yes, to its own cloud | Telnet + FTP with the default Wi-Fi password on older firmware; newer U1000 firmware reportedly removed FTP. |
| REDTIGER | likely (F7N only) | not found | Uses a Novatek chip, which usually exposes the 192.168.1.254 file server; nobody has reported trying it. |
| Vantrue, Garmin, Nextbase | unknown | Garmin joins Wi-Fi only for its own Vault cloud | Only the brand apps are documented. |
| Botslab, Qubo, Dylect, NEXDIGITRON, CP PLUS, Blaupunkt, boAt | unknown | not found | Only their own apps are documented (Qubo Pro, GaadiCAM, CarKam, boAt HiveCam and others). |
| BLEAT, CrossBeats | unknown | not found | Nothing found at all. |

## What it means for Roadie

- Only **VIOFO** and **BlackVue** are proven to join a home or phone Wi-Fi and have maintained sync tools, so a phone or a small box can push clips to Google Drive without anyone touching the camera.
- **DDPAI** is open too, but the downloading device has to join the camera's own Wi-Fi, which can clash with wireless Android Auto on the same phone (task #2).
- In India in Nov 2026 every VIOFO model was sold out (dashcameras.in, the only seller found) and BlackVue wasn't stocked by any Indian store checked, so no proven-open camera could be bought here at the time.
- Many Indian brands are likely rebadged Chinese cameras and may expose the same Novatek file server. Scanning one real camera's ports would settle it.

Not checked: Reddit r/Dashcam threads and one ipcamtalk thread (blocked). Brands marked unknown are not proven closed.
