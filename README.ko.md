# 디지털 생애 저장소 표준 (DLRS) v0.8-asset-architecture

<div align="center">

**DLRS는 실행 가능한 `.life`⁠⁠ 디지털 생애 아카이브 표준을 정의합니다 — 이중 표준(dual standard):**

1. **`.life` 아카이브 파일 포맷** — 당사자(또는 권한을 위임받은 대리인)의 동의 하에 생성되는, 이식 가능하고 서명되며 기한이 정해진 디지털 생애 아카이브 패키지입니다.
2. **`.life` 런타임 프로토콜** — 호환되는 런타임이 `.life`⁠⁠를 로드하여 채팅 / 가상 세계 / 3D / 기타 디지털 환경에서 *AI 디지털 생애 인스턴스*를 생성하는 방법입니다.

프라이버시 최우선, 동의 기반, 구조화, 철회 가능, 감사 가능, 스키마 검증 및 템플릿 제출 방식을 따릅니다.
**`.life` 는 죽은 사람을 살려내는 "부활(resurrection)" 기술이 아닙니다** — 런타임이 `.life`⁠를 마운트하여 생성하는 것은 항상 식별 가능한 *AI 디지털 생애 인스턴스*이며, 이는 반드시 철회 및 감사 가능해야 합니다.

> **📢 RFC 단계**  
> 본 문서는 초기 단계의 오픈 표준 초안입니다. 피드백, 번역, 스키마 개선 및 윤리적 검토를 환영합니다.

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/Digital-Life-Repository-Standard/DLRS/blob/master/LICENSE)
[![Version](https://img.shields.io/badge/version-v0.8--asset--architecture-orange.svg)](https://github.com/Digital-Life-Repository-Standard/DLRS/releases/tag/v0.8-asset-architecture)
[![i18n](https://img.shields.io/badge/i18n-2%20languages-blue.svg)](https://github.com/Digital-Life-Repository-Standard/DLRS/tree/master/docs/i18n)
[![RFC](https://img.shields.io/badge/RFC-Open%20for%20Comment-green.svg)](https://github.com/Digital-Life-Repository-Standard/DLRS/blob/master/docs/community/RFC-DLRS-v0.2.md)

**Languages:** English | [简体中文](https://github.com/Digital-Life-Repository-Standard/DLRS/blob/master/README.md)

</div>

---

## 🎯DLRS란 무엇인가요?

**DLRS (Digital Life Repository Standard, 디지털 생애 저장소 표준)** 는 짝을 이루는 두 가지 표준을 비교하는 **오픈 표준 초안**입니다:

### 📦 `.life` 아카이브 파일 포맷

`.life` 파일은 당사자(또는 위임된 대리인)의 동의 하에 생성되는 **이식 가능하고 서명되며 기한이 정해진 디지털 생애 아카이브 패키지**입니다. 다음 내용이 포함될 수 있습니다:

- 신원 설명, 동의 증빙 자료, 검증 수준
- 기억 구조 (기억 원자, 지식 그래프)
- 성향 프리퍼런스, `forbidden_uses[]` (금지된 사용) 목록
- 멀티모달 자산 포인터 (포인터 모드) 또는 암호화된 데이터 (암호화 모드)
- 모델 참조, `withdrawal_endpoint` (철회 엔드포인트)
- 원본 기록의 감사 로그 중 해시 체인으로 연결된 일부 데이터

사양: [`docs/LIFE_FILE_STANDARD.md`](docs/LIFE_FILE_STANDARD.md) ·
스키마: [`schemas/life-package.schema.json`](schemas/life-package.schema.json).

### 🚀 `.life` 런타임 프로토콜

호환되는 런타임은 `.life` 파일을 로드하고 프로토콜에 따라 채팅 앱, 가상 세계, 3D 환경 등에서 **상호작용 가능하고 철회 및 감사 가능한 AI 디지털 생애 인스턴스**를 생성합니다. 런타임은 다음을 준수해야 합니다:
- 모든 결과물에 *AI 디지털 생애 인스턴스*라는 태그를 붙일 것 (결코 실제 사람과 동일하다고 주장하지 말 것)
- `forbidden_uses[]` (금지된 사용 목록)를 강제할 것
- 세션 시작 시, 그리고 최소 24시간마다 `withdrawal_endpoint`를 다시 폴링(확인)할 것
- `expires_at` (만료일) 이후에는 마운트를 거부할 것
- 두 개의 서로 다른 `.life` 파일의 기억을 하나의 인스턴스로 결합하지 말 것

사양: [`docs/LIFE_RUNTIME_STANDARD.md`](docs/LIFE_RUNTIME_STANDARD.md).

### 🧩 지원 인프라

DLRS는 `.life` 표준의 기반이 되는 기본 구조도 함께 정의합니다:

- 📋 DLRS 저장소 / 아카이브 디렉토리 구조 및 JSON 스키마 (v0.6 기준 안정화; v0.8에서는 4계층 자산 아키텍처와 티어 시스템 추가)
- ✅ 동의 및 철회 모델
- 🔒 프라이버시 경계 및 민감도 수준
- 🏛️ 거버넌스 규칙 및 검토 프로세스
- 🛠️ 검증 도구 및 아카이브 템플릿
- ⚖️ 법적 고지 및 윤리 가이드라인

---

## ❌ DLRS가 '아닌' 것

**중요한 명확화**:

- ❌ **NOT** 인간을 "부활"시키거나 "복제"하는 기술이 **아닙니다** — 런타임이 ⁠⁠`.life`를 마운트하여 생성하는 것은 *AI 디지털 생애 인스턴스*이며, 실제 대상 인물과 절대 동일할 수 **없습니다**.
- ❌ **NOT** 동의나 철회 없이 사후에 마음대로 되살리는 도구가 **아닙니다** — 모든 ⁠`.life`는 작동하는 `withdrawal_endpoint`⁠를 반드시 선언해야 하며, 모든 런타임은 실시간으로 철회 요청을 존중해야 합니다.
- ❌ **NOT** AI 아바타가 실제 사람과 같다는 보장이 **아닙니다**.
- ❌ **NOT** 법적 준수를 완벽하게 보장하는 도구가 **아닙니다**.
- ❌ **NOT** 영구적인 저장 솔루션이 **아닙니다** — 모든 `.life`⁠는 반드시 `expires_at`(만료일)을 선언해야 하며, 런타임은 그 이후 마운트를 거부해야 합니다.
- ❌ **NOT** 성숙한 프로덕션(상용) 시스템이 **아닙니다** — 이 저장소는 현재 사양 + 스키마 + 예제 빌더만 제공합니다. **공식적인 런타임 구현체는 아직 제공되지 않습니다** (v0.9+로 연기됨).
- ❌ **NOT** 법률 자문을 대체할 수 **없습니다**.

---

## ✅ DLRS가 '맞는' 것

- ✅ **`.life` 이중 표준**: 파일 포맷과 런타임 프로토콜로 나뉘며, 각각 별도의 버전 관리(semver)를 따릅니다.
- ✅ **오픈 표준 초안**: 열린 토론과 개선을 지향합니다.
- ✅ **프라이버시 최우선**: 민감한 데이터는 Git에 직접 저장되지 않습니다. 포인터 모드의 ⁠⁠`.life` 파일은 기본적으로 원본 자산을 포함하지 않습니다.
- ✅ **동의 기반**: 모든 아카이브에는 명확한 동의 증거가 있어야 합니다. 모든 ⁠`.life`는 `issued_by`⁠(발급자) + ⁠`consent_evidence_ref`⁠(동의 증빙 참조) + ⁠`verification_level`⁠(검증 수준)을 반드시 선언해야 합니다.
- ✅ **철회 가능**: 사용자는 언제든지 동의를 철회할 수 있습니다. `.life`는 `withdrawal_endpoint`를 필수화하며, 런타임은 이를 지속적으로 확인해야 합니다.
- ✅ **감사 가능**: 모든 작업은 해시 체인에 기록됩니다. `.life`는 감사 기록의 일부를 포함합니다.
- ✅ **항상 식별 가능**: `.life`를 마운트하는 런타임은 반드시 결과물을 *AI 디지털 생애 인스턴스*로 명확히 식별해야 합니다. (최소 `ai_disclosure` 요구 사항은 ⁠`visible_label_required⁠` 입니다.)
- ✅ **기한 제한**: 모든 `.life`는 `expires_at`을 반드시 선언해야 하며, 런타임은 이 시점 이후 마운트해서는 안 됩니다.
- ✅ **실험적 단계**: 구속력 없는 참조용 구현체입니다.
- ✅ **커뮤니티 주도**: 모든 기여와 피드백을 환영합니다.

---

## 🚀 왜 DLRS가 필요한가요?

AI 기술이 발전함에 따라 디지털 생애 아카이브의 중요성이 커지고 있습니다. 하지만 현재 다음과 같은 요소들이 부족한 상황입니다:

1. **표준화된 아카이브 구조** - 모든 프로젝트가 밑바닥부터 새로 구조를 만들고 있습니다.
2. **명확한 동의 모델** - 사용자의 동의를 어떻게 증명할 것인가? 어떻게 철회할 것인가?
3. **개인정보 보호 프레임워크** - 절대 저장해서는 안 되는 데이터는 무엇인가? 어떻게 안전하게 참조할 것인가?
4. **거버넌스 및 검토 규칙** - 분쟁을 어떻게 처리할 것인가? 진위 여부는 어떻게 확인할 것인가?
5. **윤리적 경계 정의** - 동의가 있더라도 금지되어야 할 사항은 무엇인가?

DLRS는 오픈 표준 접근 방식을 통해 이러한 문제들을 해결하고자 합니다.

---

## 📖 핵심 개념

### 3계층 아키텍처

```
Git 저장소 (공개/비공개)
├── manifest.json          # Metadata and configuration
├── consent/               # Consent evidence (may use pointers)
├── artifacts/raw_pointers/ # Pointer files (no raw data)
└── audit/                 # Audit logs

외부 스토리지 (암호화, 접근 제어 적용)
├── s3://bucket/voice/master.wav
├── s3://bucket/video/training.mp4
└── s3://bucket/images/headshot.jpg
```

### 민감도 수준 (Sensitivity Levels)

- `S0_PUBLIC` - 공개 정보 (예: 공개 프로필)
- `S1_INTERNAL` - 내부 정보 (예: 개인 성향)
- `S2_CONFIDENTIAL` - 기밀 정보 (예: 채팅 로그)
- `S3_BIOMETRIC` - 생체 정보 (예: 얼굴, 음성)
- `S4_IDENTITY` - 신원 증명 문서 (예: 여권, 신분증)

### 공개 수준 (Visibility Levels)

- `private` - 완전 비공개
- `public_unlisted` - 직접 링크를 통해서만 접근 가능 (일부 공개)
- `public_indexed` - 검색 및 노출 가능 (전체 공개)

---

## 🏁 빠른 시작

### 1. 저장소 복제(Clone)하기

```bash
git clone https://github.com/Digital-Life-Repository-Standard/DLRS.git
cd DLRS
```

### 2. 필수 패키지 설치

```bash
pip install -r tools/requirements.txt
```

### 3. 예제 아카이브 확인

```bash
cd examples/minimal-private
cat manifest.json
```

### 4. 첫 번째 아카이브 생성하기

```bash
python tools/new_human_record.py \
  --record-id dlrs_12345678 \
  --display-name "John Doe" \
  --region americas \
  --country us
```

### 5. 아카이브 검증하기

```bash
python tools/validate_repo.py
```

---

## 📚 문서 (Documentation)

- 📖 [시작하기 가이드(영문)](docs/getting-started.en.md)
- 🤔 [자주 묻는 질문 (FAQ)](docs/FAQ.en.md)
- 🏗️ [아키텍처](docs/architecture.md)
- 🗺️ [시각화 다이어그램](docs/diagrams/)
- 🗺️ [시각화 다이어그램](docs/diagrams/)
- 📋 [RFC: DLRS v0.2](docs/community/RFC-DLRS-v0.2.md)
- 💬 [동의 모델 피드백](docs/community/consent-model-feedback.md)
- 🎯 [초보자가 기여하기 좋은 이슈 (Good First Issues)](docs/community/good-first-issues.md)
- 📢 [커뮤니티 홍보 가이드](docs/community/community-promotion-guide.md)

---

## 🤝 기여하는 방법 (How to Contribute)

다음과 같은 다양한 형태의 기여를 환영합니다:

1. **피드백 및 제안** - 이슈(Issue)를 등록하거나 토론(Discussion)에 참여해 주세요.
2. **문서 개선** - 오타 수정, 예제 추가, 문서 번역 등.
3. **스키마 개선** - JSON 스키마 설계 최적화.
4. **도구 개발** - 검증 도구 개선, 새로운 기능 추가.
5. **예제 아카이브** - 더 많은 템플릿과 예제 제공.
6. **윤리적 검토** - 잠재적인 윤리적, 법적 위험성 지적.

자세한 내용은 [CONTRIBUTING.md](CONTRIBUTING.md)를 확인해 주세요.

---

## 🌍 다국어 지원 (Internationalization)

현재 지원되는 언어:
- 🇺🇸 English
- 🇨🇳 简体中文
- 🇰🇷 한국어

다국어 번역 기여를 환영합니다. 다국어 번역 가이드 [i18n guide](docs/i18n/)를 참조

---

## 📊 현재 진행 상태

**버전**: v0.8-asset-architecture  
**상태**: RFC (Request for Comments, 의견 수렴) 단계
**완성도**: 약 82% (v0.8 자산 아키텍처 릴리스; v0.7의 약 80%에 4계층 자산 아키텍처 + 티어 시스템 + 5단계 조립 파이프라인 추가. ULTIMATE가 `.life` 이중 표준으로 재배치되면서 기준이 확장됨)

### v0.8 주요 업데이트

v0.8-asset-architecture ([epic #106](https://github.com/Digital-Life-Repository-Standard/DLRS/issues/106)) 는 자산 관점 및 `.life`⁠ 런타임 조립 프로토콜을 완성했습니다:

- **4계층 자산 아키텍처**: 생성(출처 추적) / 수명 주기(대체, 기념, 철회 단계) / 바인딩(기능 선언 + 오케스트레이션 + 강력한 제약) / 티어(6차원 가중치 신용 등급)
- **스키마 D 우주적 진화 모델(Cosmic Evolution)**: 12단계 티어 레벨 (Quark → Singularity); 기계적 필드는 고정됨; 이름/기호는 진화 가능한 부록으로 분리
- **5단계 조립 파이프라인**: 검증(Verify) / 해석(Resolve) / 조립(Assemble) / 실행(Run) / 보호(Guard); 프로바이더 레지스트리 + `LifeCapabilityProvider` 인터페이스 + 등급별 샌드박스 + 호스팅 API 기반 AND-게이트 검증
- **빌더 v0.2**: `tools/build_life_package.py` 가 콘텐츠를 기반으로 티어 블록을 자동 파생합니다. 수동으로 작성된 티어 블록은 `computed_by` 패턴을 통해 스키마 계층에서 거부됩니다.

자세한 내용은 `docs/LIFE_ASSET_ARCHITECTURE.md` + `docs/LIFE_TIER_SPEC.md` + `docs/LIFE_RUNTIME_STANDARD.md`의 Part B를 참조하세요.

### ✅ 완료됨
- 기본 디렉토리 구조
- `.life` 파일 포맷 사양 + JSON 스키마 (v0.7 비전 변경 반영)
- `.life` 런타임 프로토콜 사양 (v0.7 + v0.8 Part B 5단계 조립)
- 동의, 철회, 기념, 금지된 사용(forbidden_uses)
- 4계층 자산 아키텍처 + 티어 시스템 + 스키마 D 네이밍 (v0.8)
- 빌드 파이프라인 (v0.5 오프라인 우선 + v0.6 기억 원자 / 지식 그래프)
- 검증 도구 + 예제 아카이브
- 이중 언어 문서

### 🚧 진행중
- 커뮤니티 피드백 수집
- 스키마 최적화
- 다국어 번역

### 📋 계획중
- `dlrs-runtime` 참조용 구현체 (v0.9+; 사양에 따라 5단계 조립을 실제로 실행하는 첫 번째 버전)
- 암호화 모드 + 서명 (life-format v0.2)
- 권한 모델 (RBAC / ReBAC / ABAC)

[ROADMAP.md](ROADMAP.md) 및 구현 상태 [Implementation Status](docs/IMPLEMENTATION_STATUS.md)를 확인하세요.

---

## ⚖️ 법적 및 윤리적 고려사항

**중요 안내사항**:

이 프로젝트는 다음 사항들을 다룹니다:
- 초상권 및 음성권
- 생체 정보
- 개인정보 보호
- 사망자의 권리
- 국경 간 데이터 전송
- AI 생성 콘텐츠 라벨링
- 딥페이크 악용 위험

**면책 조항:**
- 이 저장소에서 제공되는 템플릿과 도구는 참조용일 뿐이며 법적 조언을 구성하지 않습니다.
- 규정 준수에 대한 책임은 전적으로 사용자 본인에게 있습니다.
- 공식적으로 사용하기 전에 반드시 법률 전문가와 상담해야 합니다.

자새한 내용은 [LEGAL_DISCLAIMER.md](LEGAL_DISCLAIMER.md)를 확인하세요.

---

## 📞 문의하기 (Contact)

- 💬 [GitHub 토론(Discussions)](https://github.com/Digital-Life-Repository-Standard/DLRS/discussions)
- 🐛 [이슈(Issues)](https://github.com/Digital-Life-Repository-Standard/DLRS/issues)
- 📧 보안 관련 문제: See [SECURITY.md](SECURITY.md)

---

## 📄 라이선스

해당 프로젝트는 [MIT License](LICENSE)에 따라 배포됩니다.

---

## 🙏 감사말

지원해 주신 모든 기여자분들과 커뮤니티 멤버들께 감사드립니다!

---

## 🔗 관련 자료

- [전체 표준 초안](DLRS_ULTIMATE.md)
- [격차 분석(Gap Analysis)](docs/GAP_ANALYSIS.md)
- [구현 상태](docs/IMPLEMENTATION_STATUS.md)
- [프로젝트 로드맵](ROADMAP.md)
- [거버넌스 모델](GOVERNANCE.md)
- [행동 강령(Code of Conduct)](CODE_OF_CONDUCT.md)

---

<div align="center">

**디지털 생애 아카이브를 더 안전하고, 더 투명하며, 더 통제 가능하게 만듭니다.**

DLRS 커뮤니티가 ❤️를 담아 만들었습니다.

</div>
