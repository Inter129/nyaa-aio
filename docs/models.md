# 기종별 부팅 가이드

SD 구성은 모든 기종이 같습니다. `nyaa-aio.zip`을 FAT32(또는 exFAT) SD 루트에 풀면 됩니다.

| 기종 | 모델 번호 | 부팅 방식 |
|---|---|---|
| 구형 Erista (미패치) | HAC-001, 시리얼 XAW1/XAJ1 등 초기 | RCM 지그 → `payload.bin` 주입 (TegraRcmGUI, Rekado) |
| 구형 Erista (패치됨) | HAC-001 후기 | 모드칩 필요 |
| 개선판 Mariko | HAC-001(-01) | 모드칩 필요 |
| OLED | HEG-001 | 모드칩 필요 |
| Lite | HDH-001 | 모드칩 필요 |

모드칩(Picofly/HWFLY 등)은 SD 루트의 `payload.bin`(hekate)을 자동으로 부팅합니다.
hekate가 뜨면 **Launch → CFW (emuMMC)** 를 고르세요. sysMMC CFW 사용은 밴 위험이 큽니다.

미패치 여부는 시리얼로 확인하세요 (ismyswitchpatched.com).
