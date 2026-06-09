<div align="center" style="text-align:center">
  <p>
    <img alt="BAMT icon" src=https://github.com/Agent-0808/BA-Modding-Toolkit/blob/99332127fc5478e227a37d60bad12074c9472992/docs/title.png?raw=true/>
  </p>
  <p>
    <img alt="GitHub License" src="https://img.shields.io/github/license/Agent-0808/BA-Modding-Toolkit">
    <img alt="GitHub Release" src="https://img.shields.io/github/v/release/Agent-0808/BA-Modding-Toolkit">
    <img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/Agent-0808/BA-Modding-Toolkit?style=flat">
    <img alt="GitHub Downloads (all assets, all releases)" src="https://img.shields.io/github/downloads/Agent-0808/BA-Modding-Toolkit/total">
  </p>
</div>

# BA Modding Toolkit

[简体中文](README_zh-CN.md) | English | **한국어**

UnityPy 기반의 Blue Archive(블루 아카이브) 게임 모드(Mod) 제작 및 업데이트를 자동화하기 위한 툴킷입니다.

Steam 버전(PC) 및 기타 버전(글로벌/일본 서버, PC/Android/iOS)을 지원합니다.

## 소개

![Abnormal Client](docs/help/abnormal-ko.png)

- 인터넷에서 다운로드한 모드를 게임 디렉토리의 해당 파일에 교체했는데, 게임에서 "비정상 클라이언트" 오류가 발생하고 로그인이 안 되나요?
- 오래전에 배포된 모드를 다운로드했는데 파일명이 최신 버전과 다르나요? 교체 후 캐릭터 이미지가 변경되지 않거나 전혀 표시되지 않거나 게임이 멈추나요?
- 캐릭터 일러스트를 교체하는 자신만의 모드를 제작하고 싶지만 Unity 관련 지식이 없으신가요?
- 게임 리소스를 추출하여 캐릭터 일러스트나 기타 리소스를 얻고 싶으신가요?

BA Modding Toolkit은 위의 문제들을 해결할 수 있게 도와드리며, 완전히 초보자 친화적인 조작법으로 번들 파일을 수동으로 조작할 필요가 없습니다.

## 시작하기

[Releases](https://github.com/Agent-0808/BA-Modding-Toolkit/releases) 페이지에서 최신 버전의 실행 파일(exe)을 다운로드한 후 더블클릭하여 프로그램을 실행하세요.

## 프로그램 기능 설명

> [!TIP]
> 자세한 사용법은 [사용법](https://github.com/Agent-0808/BA-Modding-Toolkit/wiki/Usage) 페이지를 참고해주세요.

프로그램에는 다양한 기능이 포함되어 있습니다:

- **Mod 업데이트**: 서로 다른 플랫폼 간 모드 업데이트 또는 포트
- **일괄 업데이트**: 여러 모드 파일을 일괄 처리
- **CRC 도구**: CRC 체크섬 계산 및 보정 기능
- **리소스 패킹**: 폴더 내의 자산 파일을 번들 파일에 패킹하여 번들 내의 해당 이름 자원 교체
- **리소스 추출**: 번들 파일에서 지정된 유형의 리소스를 로컬 파일로 추출
- **구버전/신버전 변환**: 구 버전 형식(글로벌 구버전)과 신 버전 형식(일본/글로벌 신버전) 간 상호 변환
- **일괄 구버전 변환**: 구버전→신버전 변환 작업을 일괄 처리

- **파일 목록**: 현재 지정된 디렉토리의 모든 번들 파일 정보 확인 및 관리

![How to update a mod with BAMT GUI](docs/help/gui-help-mod-update-ko.png)

## 확장 기능

여기서 소개하는 확장 기능들은 모두 선택 사항이며, 필요에 따라 활성화 여부를 선택할 수 있습니다.

> [!WARNING]
> 하단의 확장 기능들은 독립적인 서드파티 프로그램이므로 다운로드 및 사용 시 각 프로그램의 라이선스를 준수해 주세요.
> BA-Modding-Toolkit은 `subprocess` 방식으로 명령줄을 통해 해당 프로그램들을 호출할 뿐이며, 이러한 프로그램들의 코드나 파일을 포함하거나 배포하지 않으며, 사용 중 발생할 수 있는 어떤 문제에도 책임지지 않습니다.

### Spine 스케레톤 데이터 컨버터

**[wang606/SpineSkeletonDataConverter](https://github.com/wang606/SpineSkeletonDataConverter)**

이 도구는 오래된 모드에서 사용된 Spine 3 형식 `.skel` 파일을 현재 게임 버전이 지원하는 Spine 4 형식으로 변환할 수 있습니다. 또한 "리소스 추출" 기능에서 Spine 4 형식 파일을 Spine 3 형식으로 다운그레이드할 수 있습니다.

설정 페이지에서 `SpineSkeletonDataConverter.exe` 프로그램 경로를 설정하고 "Spine 변환 활성화" 옵션을 체크하세요.

- 변환 전후 표현이 완전히 일치하지 않을 수 있습니다.
- `SpineSkeletonDataConverter.exe`를 설정하지 않아도 현재 버전(4.2.xx)과 호환되는 Spine 파일을 사용하는 모드는 정상적으로 업데이트할 수 있습니다.
- 2025년 이후에 제작된 모드는 이미 Spine 4 형식을 사용하므로 이 옵션을 설정하지 않아도 정상적으로 업데이트할 수 있습니다.

### Spine 뷰어

**[ww-rm/SpineViewer](https://github.com/ww-rm/SpineViewer)**

이 도구는 Spine 스케레톤 애니메이션 파일을 미리보기 및 렌더링할 수 있습니다. 설정 페이지에서 `SpineViewerCLI.exe` 프로그램 경로를 설정하고 "파일 목록" 창에서 Spine 애니메이션을 미리볼 수 있습니다.

## 명령줄 인터페이스 (CLI)

그래픽 인터페이스 외에도, 이 프로젝트는 명령줄 인터페이스(CLI) 버전 프로그램 `cli/main.py`도 제공합니다.

[Releases](https://github.com/Agent-0808/BA-Modding-Toolkit/releases) 페이지에서 컴파일된 실행 파일 `BAMT-CLI.exe`를 다운로드하거나, `uv run bamt-cli` 명령어로 소스 코드를 실행할 수 있습니다.

### CLI 사용법

모든 작업은 `bamt-cli` 명령으로 실행할 수 있습니다. `--help`를 사용하여 사용 가능한 모든 명령과 파라미터를 확인할 수 있습니다.

```bash
# 사용 가능한 모든 명령 확인
bamt-cli -h

# 특정 명령의 상세 도움말 및 예제 확인
bamt-cli update -h
bamt-cli batch-update -h
bamt-cli merge -h
bamt-cli split -h
bamt-cli batch-legacy -h
bamt-cli pack -h
bamt-cli extract -h
bamt-cli crc -h

# 환경 정보 확인
bamt-cli env
```

> [!NOTE]
> `Tap` 라이브러리의 기술적 제한으로 인해, 컴파일된 바이너리 파일은 파라미터 변수 주석을 표시할 수 없습니다. 소스 코드로 실행할 경우 도움말 정보에 파라미터 변수 주석이 표시됩니다.

자세한 사용법은 [CLI Usage](https://github.com/Agent-0808/BA-Modding-Toolkit/wiki/CLI-Usage-&-Arguments) 페이지를 참고해주세요.

## 기술적 세부사항

### 테스트 환경

아래 표는 테스트된 환경 구성 목록입니다. 참고용으로 활용해주세요.

| 운영체제 (OS)           | Python 버전 | UnityPy 버전 | Pillow 버전 | 상태  | 비고       |
|:------------------- |:--------- |:---------- |:--------- |:--- | -------- |
| Windows 10          | 3.12.4    | 1.23.0     | 12.0.0    | ✅   | 개발 환경   |
| Windows 10          | 3.11.x    | 1.23.0     | 12.0.0    | ✅   |          |
| Windows 10          | 3.12.4    | 1.23.0     | 10.4.0    | ✅   |          |
| Windows 10          | 3.13.7    | 1.23.0     | 11.3.0    | ✅   |          |
| Windows 10          | 3.12.4    | 1.24.0     | 10.4.0    | ❌   |          |
| Ubuntu 22.04 (WSL2) | 3.13.10   | 1.23.0     | 12.0.0    | ✅   |          |

## 개발

Python 3.11 이상 버전이 설치되어 있어야 합니다.

```bash
git clone https://github.com/Agent-0808/BA-Modding-Toolkit.git
cd BA-Modding-Toolkit

# uv로 의존성 관리
python -m pip install uv
uv sync
uv run bamt
# 또는 기존 방식으로 의존성 설치
python -m pip install .
python -m ba_modding_toolkit
```

저의 프로그래밍 실력이 부족하여 제안이나 이슈 제보를 환영하며, 프로젝트 개선을 위한 코드 기여도 환영합니다.

프로젝트에 `BA-Modding-Toolkit` 코드를 추가하거나 기존 코드를 수정하여 사용자 정의 모드 제작 및 업데이트 기능을 구현할 수 있습니다.

`cli/main.py`는 메인 프로그램의 명령줄 인터페이스(CLI) 버전으로, 처리 함수 호출 방식을 참고할 수 있습니다.

### 파일 구조

```
BA-Modding-Toolkit/
│ 
│ # ============= 프로그램 =============
│ 
├── src/ba_modding_toolkit/
│ ├── __init__.py
│ ├── __main__.py    # 프로그램 진입점
│ ├── core.py        # 핵심 처리 로직
│ ├── searching.py   # 검색 기능 로직
│ ├── bundle.py      # 번들 클래스
│ ├── naming.py      # 파일명 처리 로직
│ ├── models.py      # 데이터 모델 클래스
│ ├── i18n.py        # 국제화 기능 관련
│ ├── utils.py       # 유틸리티 클래스 및 보조 함수
│ ├── cli/           # 명령줄 인터페이스 서브프로그램
│ │ ├── __main__.py     # CLI 주 진입점
│ │ ├── main.py         # 명령줄 프로그램 주 프로세스
│ │ ├── taps.py         # 명령줄 파라미터 해석
│ │ └── handlers.py     # 명령줄 파라미터 처리
│ ├── gui/           # 그래픽 인터페이스 패키지
│ │ ├── __init__.py
│ │ ├── main.py         # GUI 프로그램 주 진입점
│ │ ├── app.py          # 메인 앱 App 클래스
│ │ ├── base_tab.py     # TabFrame 베이스 클래스
│ │ ├── components.py   # UI 컴포넌트, 테마, 로그
│ │ ├── configs.py      # 설정 항목 정의
│ │ ├── utils.py        # UI 관련 유틸리티 함수
│ │ ├── windows/        # 독립 창
│ │ │ ├── __init__.py
│ │ │ ├── dialogs.py            # 설정 페이지
│ │ │ └── file_list_window.py   # 파일 목록 창
│ │ └── tabs/           # 기능 탭
│ │   ├── __init__.py
│ │   ├── mod_update_tab.py        # Mod 업데이트 탭
│ │   ├── batch_update_tab.py      # 일괄 업데이트 탭
│ │   ├── crc_tool_tab.py          # CRC 도구 탭
│ │   ├── asset_packer_tab.py      # 리소스 패킹 탭
│ │   ├── asset_extractor_tab.py   # 리소스 추출 탭
│ │   ├── legacy_conversion_tab.py # 구버전/신버전 형식 변환 탭
│ │   └── batch_legacy_tab.py      # 일괄 구버전 변환 탭
│ ├── assets/         # 자원 파일
│ └── locales/        # 언어 파일
├── tests/            # Pytest 테스트 케이스 폴더
│ ├── assets/         # 테스트 자원
│ └── test_*.py       # 테스트 케이스 파일
├── config.toml       # 로컬 설정 파일 (자동 생성)
│
│ # ============= 기타 =============
│
├── requirements.txt # Python 의존성 목록 (기존 설치 방식용)
├── pyproject.toml   # Python 프로젝트 설정 파일
├── LICENSE          # 프로젝트 라이선스 파일
├── docs/            # 프로젝트 문서 폴더
│ └── help/              # 도움말 문서 내 이미지
├── README_zh-CN.md  # 프로젝트 문서 (중국어)
└── README.md        # 프로젝트 문서 (영어)
```

## 감사의 말

본 프로젝트에 코드와 기여를 해주신 모든 분들께 감사드립니다.

특별 감사:

- [Deathemonic](https://github.com/Deathemonic): [BA-CY](https://github.com/Deathemonic/BA-CY) 프로젝트 기반 CRC 보정 기능 구현.
- [kalina](https://github.com/kalinaowo): `CRCUtils` 클래스의 프로토타입 제작.

### 서드파티 라이브러리

이 프로젝트는 다음과 같은 우수한 서드파티 라이브러리를 사용합니다:

- [UnityPy](https://github.com/K0lb3/UnityPy) (MIT License): Unity Bundle 파일 해석 및 조작을 위한 핵심 라이브러리
- [Pillow](https://python-pillow.github.io/) (MIT License): 이미지 처리 라이브러리
- [tkinterdnd2](https://github.com/pmgagne/tkinterdnd2) (MIT License): Tkinter에 드래그 앤 드롭 기능 지원 추가
- [ttkbootstrap](https://github.com/israel-dryer/ttkbootstrap) (MIT License): 모던 Tkinter 테마 라이브러리
- [toml](https://github.com/uiri/toml) (MIT License): TOML 설정 파일 해석 및 저장 라이브러리
- [SpineAtlas](https://github.com/Rin-Wood/SpineAtlas) (MIT License): Spine 애니메이션 파일의 .atlas 파일 해석 및 편집
- [Tap](https://github.com/swansonk14/typed-argument-parser) (MIT License): 명령줄 파라미터 해석
- [pytest](https://pytest.org/) (MIT License): 테스트 프레임워크

### 관련 저장소

다음과 같은 유용한 관련 저장소들이 있습니다:

- [BA-characters-internal-id](https://github.com/Agent-0808/BA-characters-internal-id) : 캐릭터 이름과 내부 파일 ID 간 대응 관계 확인
- [BA-AD](https://github.com/Deathemonic/BA-AD): 원본 게임 리소스 다운로드

### 면책 조항

<sub>
BA Modding Toolkit은 개인 프로젝트이며, NEXON Games Co., Ltd., NEXON Korea Corp., Yostar, Inc. 또는 이들의 자회사와 어떠한 관련도, 승인도, 연결고리도 없습니다. 모든 게임 자산, 캐릭터, 음악 및 관련 지적재산권은 각각의 소유자의 상표 또는 등록 상표입니다. 이 도구에서는 교육 및 상호운용성 목적(공정 이용)로만 사용됩니다. 공식 게임의 이용약관을 존중해 주세요. 이 도구를 치팅이나 악의적인 행위에 사용하지 마세요.
</sub>
