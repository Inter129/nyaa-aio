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

## 부팅 흐름

1. hekate 부팅 로고(nyaa 스플래시)가 3초 동안 표시됩니다.
   - 이때 **VOL-**를 누르고 있으면 hekate 메뉴로 들어갑니다.
   - 아무것도 누르지 않으면 **CFW (auto)**로 자동 부팅합니다. emuMMC가 켜져 있으면 emuMMC로, 없으면 sysMMC로 부팅합니다.
2. Atmosphère 스플래시가 뜬 뒤 홈 화면이 나옵니다.

hekate 메뉴에서는 **CFW (emuMMC)**, **CFW (sysMMC)**, **Stock (sysMMC)**을 직접 고를 수 있습니다. sysMMC로 CFW를 쓰면 밴 위험이 큽니다.

미패치 여부는 시리얼로 확인하세요 (ismyswitchpatched.com).

## 스위치에서 업데이트하기

팩에는 업데이터 앱 `switch/nyaa-aio/nyaa-aio.nro`가 들어 있습니다.

1. CFW로 부팅한 뒤 앨범(hbmenu)에서 **nyaa-aio**를 실행합니다.
   타이틀 오버라이드(게임을 R 버튼을 누른 채 실행)로 띄우는 것을 권장합니다. 앨범 애플릿 모드는 메모리가 부족할 수 있습니다.
2. 최신 팩을 받아 설치합니다. emuMMC, `Nintendo/` 폴더, 사용자 설정(`hekate_ipl.ini` 등)은 건드리지 않습니다.
3. **A**를 눌러 재부팅합니다.
   - 미패치 Erista: Atmosphère가 `reboot_payload.bin`(hekate)으로 재부팅합니다.
   - 모드칩 기기: 모드칩이 `payload.bin`(hekate)으로 부팅합니다.

## 부팅 스플래시 바꾸기

Atmosphère 부팅 화면은 기본으로 **nyaa dark**가 적용되어 있습니다.
nyaa-aio 앱에서 **X (Boot splash)**를 누르면 프리셋을 고를 수 있고, 다음 부팅부터 반영됩니다.

| 프리셋 | 설명 |
|---|---|
| nyaa dark | 어두운 배경 + 분홍 고양이 (기본값) |
| nyaa pink | 분홍 배경 + 흰 고양이 |
| nyaa mono | 검은 배경 + 회색 고양이 |
| Atmosphere (original) | Atmosphère 원래 로고 |

프리셋을 바꾸면 hekate 부팅 로고와 Atmosphère 스플래시가 함께 바뀝니다. Atmosphere (original)을 고르면 hekate 로고도 기본값으로 돌아갑니다.
고른 프리셋은 팩을 업데이트해도 유지됩니다. 설치가 끝나면 자동으로 다시 적용합니다.

## 업데이트할 때 파일 정리

팩에는 들어 있는 파일 목록(`nyaa-aio.files.txt`)이 함께 들어 있습니다. 업데이트하면 이전 팩에만 있던 파일, 예를 들어 빠진 sysmodule은 자동으로 지워집니다.
emuMMC, `Nintendo/` 폴더, 사용자 설정, 그리고 팩과 상관없이 직접 넣은 파일은 건드리지 않습니다.
`hekate_ipl.ini`는 사용자 설정으로 보존합니다. 다만 예전 nyaa-aio 기본값을 한 글자도 고치지 않았다면 새 기본값으로 바꿉니다.

닌텐도 서버는 DNS에서 차단되어 있지만, 업데이터가 쓰는 GitHub에는 정상적으로 접속됩니다.
