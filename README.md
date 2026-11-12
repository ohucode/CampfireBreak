# Campfire Break

Campfire Break는 iPhone과 iPad에서 모닥불을 감상하는 앱입니다. Metal로 불꽃과 불씨를 실시간으로 그리며, 장작이 그을리고 숯과 재로 바뀌는 과정을 기본 1시간에 걸쳐 보여 줍니다.

[앱 지원](SUPPORT.md) · [개인정보 처리방침](PRIVACY.md)

## 사용 방법

- 장작을 두 번 탭하거나 불꽃 버튼을 눌러 불을 끄거나 다시 켤 수 있습니다. 처음부터 태우려면 **새 모닥불** 버튼을 누르세요.
- 모닥불 화면을 탭하면 조작 버튼이 숨겨집니다. 다시 탭하면 버튼이 나타납니다.
- **모닥불 설정**에서 화로대, 장작, 장작 배치, 불꽃 색상을 고를 수 있습니다.
- **모닥불 설정 → 배경**에서 일곱 가지 풍경을 미리 볼 수 있습니다. 기본 배경은 소나무 숲이며 나머지 여섯 가지 배경은 플러스 팩에서 제공됩니다.
- **장작 타는 시간**은 15분, 30분, 1시간, 2시간, 4시간 중에서 고를 수 있으며 기본값은 1시간입니다.
- 모닥불이 타는 동안 [myLoop의 Fireplace 녹음](https://freesound.org/people/myLoop/sounds/852107/)(CC0)을 반복 재생합니다. **모닥불 설정**의 **장작 타는 소리**에서 끌 수 있습니다.

기본 구성에는 참나무 장작, 스톤링 화로대, 기본 불꽃 색상, 장작 배치 4종이 포함됩니다. **플러스 팩**을 한 번 구매하면 배경 6종, 장작 5종, 화로대 8종이 추가되고 모든 불꽃 색상을 사용할 수 있습니다. 이전에 구매했다면 플러스 팩 화면에서 **구매 복원**을 누르세요.

앱은 한국어, 영어, 일본어를 지원합니다.

## 빌드 및 실행

Xcode 27.2 개발 환경을 기준으로 하며, 최소 실행 버전은 iOS 및 iPadOS 18.6입니다.

1. Xcode에서 [CampfireBreak.xcodeproj](../CampfireBreak.xcodeproj)를 엽니다.
2. `CampfireBreak` 스킴과 iPhone 또는 iPad 시뮬레이터를 선택합니다.
3. **Product → Run**(⌘R)으로 실행합니다. 실제 기기에서 실행하려면 **Signing & Capabilities**에서 사용할 개발 팀을 선택하세요.

플러스 팩 구매를 로컬에서 테스트하려면 **Product → Scheme → Edit Scheme → Run → Options**의 **StoreKit Configuration**에서 [CampfireBreak.storekit](../CampfireBreak.storekit)을 선택한 뒤 실행하세요.

## 프로젝트 구조

| 경로 | 역할 |
| --- | --- |
| [ContentView.swift](../CampfireBreak/ContentView.swift) | SwiftUI 모닥불 화면, 조작 버튼, 설정 |
| [CampfireRenderer.swift](../CampfireBreak/CampfireRenderer.swift), [CampfireShaders.metal.txt](../CampfireBreak/CampfireShaders.metal.txt) | Metal 렌더링과 연소 단계 표현 |
| [CampfireArtwork.bundle](../CampfireBreak/CampfireArtwork.bundle) | 장작과 화로대의 WebP 이미지 및 배치 정보 |
| [PlusStore.swift](../CampfireBreak/PlusStore.swift) | StoreKit 플러스 팩 구매 및 복원 |
| [Localizable.xcstrings](../CampfireBreak/Localizable.xcstrings) | 앱 화면의 번역 문자열 |
