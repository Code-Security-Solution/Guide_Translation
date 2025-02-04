<br />

<p align="center">
  <a href="https://semgrep.dev">
    <picture>
      <source media="(prefers-color-scheme: light)" srcset="images/semgrep-logo-light.svg">
      <source media="(prefers-color-scheme: dark)" srcset="images/semgrep-logo-dark.svg">
      <img src="https://raw.githubusercontent.com/semgrep/semgrep/develop/images/semgrep-logo-light.svg" height="100" alt="Semgrep logo"/>
    </picture>
  </a>
</p>
<h2 align="center">
    믿을 수 없을 정도로 빠른 코드 스캐닝
</h2>
<p align="center">
  <a href="https://formulae.brew.sh/formula/semgrep">
    <img src="https://img.shields.io/homebrew/v/semgrep?style=flat-square" alt="Homebrew" />
  </a>
  <a href="https://pypi.org/project/semgrep/">
    <img alt="PyPI" src="https://img.shields.io/pypi/v/semgrep?style=flat-square&color=blue">
  </a>
  <a href="https://semgrep.dev/docs/">
      <img src="https://img.shields.io/badge/docs-semgrep.dev-purple?style=flat-square" alt="Documentation" />
  </a>
  <a href="https://go.semgrep.dev/slack">
    <img src="https://img.shields.io/badge/slack-3.5k%20members-green?style=flat-square" alt="Join Semgrep community Slack" />
  </a>
  <a href="https://github.com/semgrep/semgrep/issues/new/choose">
    <img src="https://img.shields.io/badge/issues-welcome-green?style=flat-square" alt="Issues welcome!" />
  </a>
  <a href="https://github.com/semgrep/semgrep#readme">
    <img src="https://img.shields.io/github/stars/semgrep/semgrep?label=GitHub%20Stars&style=flat-square" alt="Star Semgrep on GitHub" />
  </a>
  <a href="https://hub.docker.com/r/semgrep/semgrep">
    <img src="https://img.shields.io/docker/pulls/semgrep/semgrep.svg?style=flat-square" alt="Docker Pulls" />
  </a>
  <a href="https://hub.docker.com/r/semgrep/semgrep">
    <img src="https://img.shields.io/docker/pulls/semgrep/semgrep.svg?style=flat-square" alt="Docker Pulls (Old)" />
  </a>
  <a href="https://twitter.com/intent/follow?screen_name=semgrep">
    <img src="https://img.shields.io/twitter/follow/semgrep?label=Follow%20semgrep&style=social&color=blue" alt="Follow @semgrep on Twitter" />
  </a>
</p>
</br>


Semgrep은 빠르고 오픈소스인 정적 분석 도구로, 코드 검색, 버그 탐색 및 보안 가이드라인과 코딩 표준을 준수하도록 지원합니다. Semgrep은 [30개 이상의 언어](#언어-지원)를 지원하며, IDE, 사전 커밋 검사 및 CI/CD 워크플로우에서 실행할 수 있습니다.

Semgrep은 코드용 의미론적 grep입니다. 예를 들어 `grep "2"`를 실행하면 정확한 문자열 _2_ 만 찾을 수 있지만, Semgrep을 사용하면 [`x = 1; y = x + 1`을 검색할 때 _2_를 매칭할 수 있습니다](https://semgrep.dev/playground/s/5rKgj). Semgrep 규칙은 기존 코드와 유사하게 작성되며, 추상 구문 트리(AST), 복잡한 정규 표현식 또는 번거로운 DSL이 필요하지 않습니다.

보안 측면에서 Semgrep 커뮤니티 에디션은 단일 함수 또는 파일 내 코드만 분석할 수 있으므로 많은 실제 보안 이슈(true positive)를 놓칠 수 있습니다. Semgrep을 보안 목적으로 사용하려면 (**SAST**, **SCA**, 또는 **비밀 탐색**) 다음과 같은 주요 기능을 제공하는 Semgrep AppSec 플랫폼을 사용하는 것이 강력히 권장됩니다:

1. 향상된 핵심 분석 기능(파일 간, 함수 간, 데이터 흐름 분석 지원)으로 오탐(false positive)을 25% 줄이고 실제 보안 이슈 탐지율을 250% 증가시킴
2. Semgrep Assistant(AI)의 컨텍스트 기반 후처리를 통해 탐지된 문제의 잡음을 약 [20% 감소](https://a.storyblok.com/f/151984/x/2d12dc0223/whitepaper_-ai-powered-appsec-engineer-automate.pdf?cv=1728584410408). 추가적으로, Assistant는 사람이 이해할 수 있는 단계별 해결 방법을 제공하여 80% 이상의 확률로 유용하다고 평가됨.
3. 개발자 워크플로우에 원활하게 통합되는 맞춤형 정책 설정 기능을 제공하여 보안 팀이 개발자가 어떤 방식으로 보안 이슈를 확인할지(IDE, PR 코멘트 등) 세부적으로 제어 가능.

Semgrep AppSec 플랫폼은 20,000개 이상의 SAST, SCA 및 비밀 탐색 관련 규칙을 제공하며, Semgrep 보안 연구팀이 작성 및 유지 관리하는 높은 정확도의 프로 규칙을 포함합니다. 이를 통해 보안 팀이 탐지된 내용을 개발자에게 직접 제공할 수 있어 개발 속도를 늦추지 않으면서도 보안성을 강화할 수 있습니다.

Semgrep은 사용자의 로컬 컴퓨터 또는 빌드 환경에서 코드를 분석하며, **기본적으로 코드가 업로드되지 않습니다**. [시작하기 →.](#시작하기-🚀)

<a href="#option-1-getting-started-from-the-cli">
<img src="https://raw.githubusercontent.com/semgrep/semgrep/develop/images/semgrep-scan-cli.jpg" alt="Semgrep CLI 이미지"/></a>

### 언어 지원

**Semgrep Code**는 다음을 포함한 30개 이상의 언어를 지원합니다:

Apex · Bash · C · C++ · C# · Clojure · Dart · Dockerfile · Elixir · HTML · Go · Java · JavaScript · JSX · JSON · Julia · Jsonnet · Kotlin · Lisp · Lua · OCaml · PHP · Python · R · Ruby · Rust · Scala · Scheme · Solidity · Swift · Terraform · TypeScript · TSX · YAML · XML · 기타(ERB, Jinja 등)

**Semgrep Supply Chain**은 12개 언어 및 15개 패키지 관리자를 지원합니다:

C# (NuGet) · Dart (Pub) · Go (Go 모듈, `go mod`) · Java (Gradle, Maven) · Javascript/Typescript (npm, Yarn, Yarn 2, Yarn 3, pnpm) · Kotlin (Gradle, Maven) · PHP (Composer) · Python (pip, pip-tool, Pipenv, Poetry) · Ruby (RubyGems) · Rust (Cargo) · Scala (Maven) · Swift (SwiftPM)

자세한 내용은 [지원되는 언어](https://semgrep.dev/docs/supported-languages/)에서 확인할 수 있습니다.

### 시작하기 🚀

1. [Semgrep AppSec 플랫폼에서 시작하기](#옵션-1-semgrep-appsec-플랫폼에서-시작하기-권장)
2. [CLI에서 시작하기](#옵션-2-cli에서-시작하기)

새로운 사용자의 경우, [Semgrep AppSec 플랫폼에서 시작하기](#옵션-1-semgrep-appsec-플랫폼에서-시작하기-권장)를 권장합니다. 이 플랫폼은 시각적 인터페이스, 데모 프로젝트, 결과 분류 및 탐색 워크플로우를 제공하며, CI/CD 설정을 빠르게 진행할 수 있도록 도와줍니다. 스캔은 로컬에서 실행되며 코드가 업로드되지 않습니다. 또는 CLI에서 시작하여 터미널 출력을 탐색하며 단발성 검색을 실행할 수도 있습니다.

---

### 옵션 1: Semgrep AppSec 플랫폼에서 시작하기 (권장)

<a href="https://go.semgrep.dev/login-ghrmgo" target="_blank">
    <img src="https://raw.githubusercontent.com/semgrep/semgrep/develop/images/semgrep-main-image.jpg" alt="Semgrep 플랫폼 이미지"/>
</a>

1. <a href="https://go.semgrep.dev/login-ghrmgo" target="_blank">semgrep.dev</a>에 등록하세요.

2. 데모 결과를 탐색하여 Semgrep의 작동 방식을 익히세요.

3. 프로젝트를 스캔하려면 `Projects > Scan New Project > Run scan in CI`로 이동하세요.

4. 버전 관리 시스템을 선택한 후, 프로젝트를 추가하는 온보딩 단계를 따르세요. 설정이 완료되면, Semgrep은 모든 풀 리퀘스트 이후 프로젝트를 자동으로 스캔합니다.

5. [선택 사항] Semgrep을 로컬에서 실행하려면 CLI 섹션의 단계를 따르세요.

---

### 참고 사항:

문제가 발생하면 <a href="https://go.semgrep.dev/slack" target="_blank">Semgrep Slack</a>에서 도움을 요청하세요.

---

### 옵션 2: CLI에서 시작하기

1. **Semgrep CLI 설치하기**

```bash
# macOS에서 설치
$ brew install semgrep

# Ubuntu/WSL/Linux/macOS에서 설치
$ python3 -m pip install semgrep

# 설치 없이 Docker를 이용하여 실행
$ docker run -it -v "${PWD}:/src" semgrep/semgrep semgrep login
$ docker run -e SEMGREP_APP_TOKEN=<TOKEN> --rm -v "${PWD}:/src" semgrep/semgrep semgrep ci
```

2.  ```semgrep login``` 을 실행하여 계정을 만들고 로그인하세요.

Semgrep에 로그인하면 다음 기능을 사용할 수 있습니다:

- [Semgrep Supply Chain](https://semgrep.dev/products/semgrep-supply-chain?utm_medium=readme&utm_source=github&utm_content=ssc-product): 타사 라이브러리에서 도달 가능한 취약점을 감지하는 종속성 스캐너
- [Semgrep Code의 Pro 규칙](https://semgrep.dev/products/semgrep-code?utm_medium=readme&utm_source=github&utm_content=code-pro-rules): Semgrep 보안 연구팀이 작성한 600개 이상의 높은 신뢰도의 보안 규칙
- [Semgrep Code의 Pro 엔진](https://semgrep.dev/products/pro-engine?utm_medium=readme&utm_source=github&utm_content=pro-engine): 복잡한 취약점을 탐지하고 오탐을 줄이도록 설계된 고급 코드 분석 엔진

3. 앱의 루트 디렉터리로 이동한 후 `semgrep ci`를 실행하세요. 프로젝트를 스캔하여 소스 코드 및 종속성의 취약점을 검사할 수 있습니다.

4. `-e` 옵션을 사용하여 직접 쿼리를 작성해보세요. 예를 들어, Python 코드에서 좌변과 우변이 동일한 비교(잠재적 버그)를 찾으려면 다음 명령을 실행할 수 있습니다:

```bash
$ semgrep -e '$X == $X' --lang=py path/to/src
```

### Semgrep 에코시스템

Semgrep 에코시스템은 다음을 포함합니다:

- [Semgrep Community Edition](https://semgrep.dev/docs/cli-reference/) - 모든 기능의 핵심이 되는 오픈소스 프로그램 분석 엔진입니다. 오탐(False Positive)이 많이 나도 무방한 단발성 작업(일회성, 즉흥적 작업)에 적합해요. 예를 들어, 컨설턴트, 보안 감사관, 침투 테스터처럼 빠르게 결과가 필요할 때 유용합니다.

- [Semgrep AppSec 플랫폼](https://semgrep.dev/login?utm_medium=readme&utm_source=github&utm_content=appsec-platform) - 조직 전체에서 SAST, SCA, 및 비밀 검사(Secrets scanning)를 손쉽게 조정하고 확장할 수 있도록 지원합니다. 개발자를 방해하지 않으며, 개발자가 볼 수 있는 결과를 사용자 지정하고, GitHub, GitLab, CircleCI 등 다양한 CI 공급자와 통합할 수 있습니다. 무료 및 유료 버전이 포함되어 있습니다.
- [Semgrep Code (SAST)](https://semgrep.dev/products/semgrep-code?utm_medium=readme&utm_source=github&utm_content=semgrep-code) - 개발자가 보안 지식 없이도 문제를 신속하게 해결할 수 있도록 도와주는 SAST 도구입니다. 개발자가 방해받지 않도록 맞춤형 보안 가이드와 단계별 해결책을 제공합니다.
  
- [Semgrep Supply Chain (SSC)](https://semgrep.dev/products/semgrep-supply-chain?utm_medium=readme&utm_source=github&utm_content=ssc) - 오픈 소스 서드파티 라이브러리 및 함수에서 도달 가능한 취약점을 감지하는 고신뢰 종속성 스캐너입니다.
  
- [Semgrep Secrets (비밀 검사)](https://semgrep.dev/blog/2023/introducing-semgrep-secrets/) - 의미론적 분석, 개선된 엔트로피 분석, 검증을 사용하여 개발자의 워크플로에서 민감한 자격 증명을 정확하게 식별합니다.
  
- [Semgrep Assistant (AI)](https://semgrep.dev/products/semgrep-code/assistant?utm_medium=readme&utm_source=github&utm_content=assistant) - AI 기반의 AppSec 엔지니어로서, Semgrep 결과를 우선 순위화하고, 분류하며, 해결하는 데 도움을 줍니다. 인간 사용자의 97%가 Assistant의 자동 분류 결정을 수락하며, 80%가 제공된 해결 가이드를 유용하다고 평가했습니다. 자세한 내용은 [이 개요](https://a.storyblok.com/f/151984/x/2d12dc0223/whitepaper_-ai-powered-appsec-engineer-automate.pdf?cv=1728584410408)를 참조하세요.

추가 리소스:

- [Semgrep Playground](https://semgrep.dev/editor) - 규칙을 작성하고 공유할 수 있는 온라인 인터랙티브 도구.
- [Semgrep Registry](https://semgrep.dev/explore) - 보안, 정확성, 종속성 취약성을 다루는 2,000개 이상의 커뮤니티 기반 규칙 제공.

GitLab, Dropbox, Slack, Figma, Shopify, HashiCorp, Snowflake, Trail of Bits를 포함한 수많은 기업에서 이미 Semgrep을 사용하고 있습니다.

Semgrep은 [Semgrep, Inc.](https://semgrep.dev)에서 개발 및 상업적으로 지원하는 보안 소프트웨어입니다.

### Semgrep 규칙

Semgrep 규칙은 기존 코드와 유사한 방식으로 작성됩니다. 추상 구문 트리(AST), 정규식 처리, 복잡한 DSL 없이 직관적으로 사용할 수 있습니다. 아래는 Python의 `print()` 문을 찾는 간단한 규칙 예제입니다.

Semgrep의 Playground에서 실행하려면 [여기를 클릭하세요](https://semgrep.dev/playground/r/3qUzQD/ievans.print-to-logger).

<p align="center">
    <a href="https://semgrep.dev/playground/r/3qUzQD/ievans.print-to-logger" target="_blank">
        <img src="https://raw.githubusercontent.com/semgrep/semgrep/develop/images/semgrep-example-rules-editor.jpg" width="582" alt="Python print() 문을 찾는 Semgrep 규칙 예제" />
    </a>
</p>

<p align="center">
    <a href="https://semgrep.dev/playground/r/3qUzQD/ievans.print-to-logger"  target="_blank"><img src="https://raw.githubusercontent.com/semgrep/semgrep/develop/images/semgrep-example-rules-editor.jpg" width="582" alt="Semgrep rule example for finding Python print() statements" /></a>
</p>

#### 예제

[문서 > 규칙 예제](https://semgrep.dev/docs/writing-rules/rule-ideas/)에서 사용 사례 및 아이디어를 확인하세요.

| 사용 사례                         | Semgrep 규칙                                                 |
| :-------------------------------- | :----------------------------------------------------------- |
| 위험한 API 금지                   | [exec 사용 방지](https://semgrep.dev/playground/s/lglB)       |
| 라우트 및 인증 검색               | [Spring 라우트 추출](https://semgrep.dev/playground/s/Y6wD)   |
| 보안 기본값 강제 적용             | [Flask 쿠키 보안 설정](https://semgrep.dev/playground/s/6KwW) |
| 오염된 데이터가 sink로 흐르는 경우 | [ExpressJS 데이터 흐름 분석](https://semgrep.dev/playground/s/qEpR) |
| 프로젝트 모범 사례 적용           | [== 체크 시 assertEqual 사용](https://semgrep.dev/playground/s/oEox), [subprocess 호출 검사](https://semgrep.dev/playground/s/zENk) |
| 프로젝트별 지식 코드화            | [트랜잭션 확인 후 실행](https://semgrep.dev/playground/s/p8zk) |
| 보안 핫스팟 감사                  | [Apache Airflow에서 XSS 찾기](https://semgrep.dev/playground/s/KPwj), [하드코딩된 자격 증명](https://semgrep.dev/playground/s/2Br8) |
| 설정 파일 감사                    | [S3 ARN 사용 찾기](https://semgrep.dev/playground/s/jEKD)    |
| 지원 중단된 API 마이그레이션      | [DES 사용 중단됨](https://semgrep.dev/playground/r/java.lang.security.audit.crypto.des-is-deprecated.des-is-deprecated), [Flask 지원 중단 API](https://semgrep.dev/playground/r/python.flask.maintainability.deprecated.deprecated-apis.flask-deprecated-apis), [Bokeh 지원 중단 API](https://semgrep.dev/playground/r/python.bokeh.maintainability.deprecated.deprecated_apis.bokeh-deprecated-apis) |
| 자동 수정 적용                     | [listenAndServeTLS 사용](https://semgrep.dev/playground/s/1Ayk) |

### 확장 기능

[문서 > 확장 기능](https://semgrep.dev/docs/extensions/)을 방문하여 편집기 또는 pre-commit에서 Semgrep을 사용하는 방법을 확인하세요. CI에 통합하고 풀 리퀘스트를 스캔하도록 설정하면, Semgrep은 해당 풀 리퀘스트에서 발생한 새로운 문제만 보고합니다. 이를 통해 기존 문제를 수정하거나 무시하지 않고도 Semgrep을 바로 사용할 수 있습니다!

### 문서

Semgrep의 전체 [문서](https://semgrep.dev/docs)를 탐색하세요. Semgrep이 처음이라면, [문서 > 시작하기](https://semgrep.dev/docs/getting-started/) 또는 [인터랙티브 튜토리얼](https://semgrep.dev/learn)을 확인하세요.

### 사용 데이터 수집  

[Registry](https://semgrep.dev/r)의 원격 구성을 사용할 경우(예: `--config=p/ci`), Semgrep은 특정 규칙이 실행될 때 발생하는 **사용 통계 및 분석 데이터를** semgrep.dev에 익명으로 전송합니다.  

반면, 로컬 파일(`--config=xyz.yml`)을 직접 사용하면, 이러한 데이터 수집이 **활성화되지 않습니다**.  

데이터 수집을 원하지 않는다면 `--metrics=off` 옵션을 사용하여 비활성화할 수 있습니다.  

Semgrep의 [개인정보 보호 정책](https://semgrep.dev/docs/metrics)에서는 데이터 수집의 원칙과, 활성화된 경우 어떤 데이터가 수집되며 어떤 데이터가 수집되지 않는지를 설명합니다.

### 추가 정보

- [자주 묻는 질문(FAQ)](https://semgrep.dev/docs/faq/)
- [기여 가이드](https://semgrep.dev/docs/contributing/contributing/)
- [개발자를 위한 빌드 지침](INSTALL.md)
- [Semgrep 커뮤니티 Slack에서 질문하기](https://go.semgrep.dev/slack)
- [CLI 참조 및 종료 코드](https://semgrep.dev/docs/cli-usage)
- [Semgrep YouTube 채널](https://www.youtube.com/c/semgrep)
- [라이선스(LGPL-2.1)](LICENSE)
- [Semgrep 라이선스](https://semgrep.dev/docs/licensing/)

### 업그레이드

Semgrep을 업그레이드하려면 아래 명령 중 설치 방법에 해당하는 것을 실행하세요:

```sh
# Homebrew 사용 시
$ brew upgrade semgrep

# pip 사용 시
$ python3 -m pip install --upgrade semgrep

# Docker 사용 시
$ docker pull semgrep/semgrep:latest
```