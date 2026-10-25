# nyaa-aio

Nintendo Switch CFW AIO 팩입니다. 구형(Erista), 개선판(Mariko), OLED, Lite를 지원합니다.

## 설치

1. [최신 릴리스](../../releases/latest)에서 `nyaa-aio.zip`을 받습니다.
2. SD 카드(FAT32 권장) 루트에 압축을 풉니다.
3. 기종에 맞게 부팅합니다: [docs/models.md](docs/models.md)

PC 설치 프로그램을 쓰면 SD 카드를 고르고 버튼 하나로 최신 팩을 설치할 수 있습니다 (설정·emuMMC 보존).
릴리스에서 Windows `nyaa-aio-windows-x64.zip`, macOS `nyaa-aio-macos-universal.zip`, Linux `nyaa-aio-linux-x64.tar.gz` 를 받으세요.
macOS 는 서명되지 않은 앱이라 처음 한 번은 Finder 에서 우클릭 → 열기 를 눌러야 합니다.

## 구성

- CFW·부트로더: Atmosphère, hekate (VOL- 를 누른 채 부팅하면 hekate 메뉴)
- 시스모듈: sys-patch, sys-con(유선 서드파티 패드), MissionControl(블루투스로 PS/Xbox 등 패드)
- 오버레이 메뉴 Ultrahand(ZL+ZR+방향키 아래): EdiZon(치트), ovl-sysmodules(시스모듈 켜기/끄기), sys-patch
- 앱: nyaa-aio 업데이터, NXThemes Installer KO(홈 메뉴 테마, 한국어판), DBI(설치 관리자, 러시아어판), JKSV(세이브 백업), NX-Activity-Log

### 한국어

- 한국어: nyaa-aio 업데이터·PC 설치 프로그램, hekate 메뉴(Nyx, 메인 화면), 테마 설치기, Ultrahand 메뉴, EdiZon·ovl-sysmodules 오버레이(nyaa-aio 번역 포함),
  JKSV·NX-Activity-Log·홈브류 메뉴(스위치 언어가 한국어일 때)
- 영어만 지원: hekate 의 세부 도구 화면, sys-patch 오버레이, sys-con 앱 (DBI 는 러시아어)
- 예전에 Ultrahand 를 이미 실행했다면 언어가 영어로 저장돼 있을 수 있습니다. Ultrahand 설정 → Language 에서 한국어를 고르세요.

`config/` 아래 설정(sys-con, MissionControl 등)은 업데이트해도 보존됩니다.
MissionControl 은 Atmosphère 버전에 민감합니다. 업데이트 후 부팅이 멈추면 SD 의
`atmosphere/contents/010000000000bd00/flags/boot2.flag` 를 지우고 부팅한 뒤 MissionControl 업데이트를 기다리세요.

## 버전

릴리스는 `vYYYY.MM.DD`(같은 날 두 번째부터 `.2`) 형식이며, 구성요소나 팩 설정이 바뀐 날에만 나옵니다.
릴리스 노트에 직전 릴리스 대비 바뀐 구성요소가 적혀 있고, 전체 버전은 `nyaa-aio.lock.json`에 있습니다.

모든 구성요소는 원 저작자의 공식 GitHub 릴리스에서 받은 것이며, 키·펌웨어·게임 파일은 포함하지 않습니다.

이 저장소는 릴리스 배포 전용입니다.
