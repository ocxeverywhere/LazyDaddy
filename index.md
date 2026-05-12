# 개인정보처리방침 (Privacy Policy)

**앱 이름:** LazyDaddy (게으른 아빠의 동화책 리더)
**패키지명:** `io.ocxeverywhere.easyreader`
**시행일:** 2026년 5월 12일
**최종 수정일:** 2026년 5월 12일

본 개인정보처리방침은 LazyDaddy(이하 "본 앱")가 사용자의 어떤 정보를 어떻게 처리하는지를 설명합니다. 본 앱은 부모가 자녀에게 동화책을 읽어 주는 것을 돕기 위해 제작되었으며, 어린이 직접 사용을 주된 대상으로 하지 않습니다.

---

## 1. 수집·처리하는 정보

본 앱은 사용자를 식별할 수 있는 계정 정보(이름, 이메일, 전화번호 등)를 **수집하지 않습니다**. 다만 기능 제공을 위해 아래의 정보를 처리합니다.

| 항목 | 처리 방식 | 외부 전송 여부 |
|---|---|---|
| 카메라로 촬영한 책 페이지 이미지 | 기기 내 임시 저장 → 텍스트 추출 후 즉시 사용 | **전송하지 않음** |
| OCR로 추출한 텍스트(동화책 본문) | 기기 내 로컬 데이터베이스(Room)에 저장 | TTS 사용 시 Google에 전송(아래 4항 참조) |
| 갤러리에서 선택한 이미지 | OCR 처리에만 사용, 별도 저장하지 않음 | **전송하지 않음** |
| 광고 식별자(Google Advertising ID) | Google AdMob SDK가 처리 | Google에 전송(아래 4항 참조) |
| 네트워크 연결 상태 | 광고/TTS 요청 시 캐시 vs 실시간 판단 | **전송하지 않음** |

본 앱은 위치 정보, 연락처, 통화 기록, SMS, 마이크, 캘린더, 사진/동영상 라이브러리 전체 접근, 신체 활동 등 어떤 민감 정보도 수집하지 않습니다.

---

## 2. 카메라(CAMERA) 권한 사용 목적

본 앱은 안드로이드의 `android.permission.CAMERA` 권한을 다음 한 가지 용도로만 사용합니다.

> **사용자가 동화책의 한 페이지를 직접 촬영하여, 그 페이지의 글자를 자동으로 텍스트로 추출(OCR)하기 위함.**

세부 동작은 다음과 같습니다.

- 카메라 권한은 사용자가 "사진 찍기" 버튼을 누른 시점에만 런타임에 요청됩니다.
- 촬영된 이미지는 앱 내부의 비공개 저장 영역(`filesDir/photos`)에 임시로만 저장됩니다.
- 이미지에 대한 문자 인식(OCR)은 **Google ML Kit의 온디바이스(on-device) 한국어 텍스트 인식 모델**을 사용하여 사용자의 기기 안에서만 처리되며, 이미지가 외부 서버로 전송되지 않습니다.
- OCR 처리 후 사용자는 추출된 텍스트만 저장할지 결정할 수 있으며, 이미지 자체는 책으로 저장되는 시점에 더 이상 보관되지 않습니다.
- 카메라가 없는 기기에서도 본 앱은 설치 가능합니다(`uses-feature android:required="false"`).

---

## 3. 데이터 보관 위치 및 기간

본 앱이 생성한 모든 사용자 데이터(저장한 동화책 텍스트, 책 제목, 책 표지 이미지 등)는 **사용자의 기기 내부에만** 보관됩니다.

- 저장소: 앱 전용 내부 저장 영역의 로컬 데이터베이스(Room) 및 앱 비공개 파일 디렉터리
- 클라우드 동기화·계정 백업·서버 업로드 기능을 제공하지 않습니다.
- 보관 기간: 사용자가 책을 직접 삭제하거나 앱을 제거할 때까지

음성 합성(TTS)으로 만들어진 오디오 캐시 또한 기기 내부에만 저장되며, 동일 텍스트 재생 시 네트워크 요청을 줄이기 위한 용도로만 사용됩니다.

---

## 4. 제3자 서비스 및 외부 전송

본 앱은 다음 Google 서비스를 사용하며, 해당 기능을 사용할 때에 한해 일부 데이터가 Google로 전송됩니다.

### 4.1 Google Cloud Text-to-Speech / Google Gemini API (음성 읽어 주기)
- **전송 데이터:** 사용자가 저장한 동화책의 텍스트(읽어 주기를 요청한 부분)
- **목적:** 텍스트를 음성으로 변환하여 재생
- **수신자:** Google LLC
- **참고:** Google의 [Cloud TTS 데이터 사용 정책](https://cloud.google.com/text-to-speech/docs/data-logging) 및 [Gemini API 약관](https://ai.google.dev/terms)을 따릅니다. 본 앱은 어떤 개인 식별 정보도 함께 전송하지 않습니다.

### 4.2 Google AdMob (광고)
- **전송 데이터:** 광고 식별자(Google AdID), 대략적인 IP 주소, 기기/OS 정보, 앱 사용 이벤트(광고 표시·클릭)
- **목적:** 앱 내 광고 노출 및 광고 성과 측정
- **수신자:** Google LLC
- **개인 맞춤 광고:** 본 앱은 만 13세 미만의 어린이를 직접 대상으로 하지 않으므로 표준 AdMob 설정을 사용합니다. 사용자는 안드로이드 설정에서 "광고 ID 초기화" 또는 "맞춤 광고 사용 안 함"을 통해 언제든 추적을 제한할 수 있습니다.
- **참고:** [Google 광고 정책](https://policies.google.com/technologies/ads) 및 [AdMob 개인정보처리방침](https://support.google.com/admob/answer/6128543).

### 4.3 Google ML Kit 텍스트 인식(한국어)
- 온디바이스(on-device) 모델을 사용하므로 **이미지·텍스트가 외부로 전송되지 않습니다**.

---

## 5. 데이터 삭제 방법

사용자는 언제든 본 앱이 저장한 데이터를 다음 방법으로 삭제할 수 있습니다.

### 방법 1 — 앱 내에서 개별 삭제
- 홈 화면에서 삭제할 책을 길게 누르거나 편집 화면에서 삭제 버튼을 사용해 개별 책 단위로 데이터를 지울 수 있습니다.

### 방법 2 — 앱 데이터 전체 초기화 (Android 설정)
1. 안드로이드 **설정** → **앱** → **LazyDaddy** 선택
2. **저장공간** → **데이터 삭제** (또는 **저장공간 및 캐시 → 저장공간 지우기**)
3. 앱이 저장한 모든 책, 이미지, 음성 캐시가 즉시 영구 삭제됩니다.

### 방법 3 — 앱 제거
- 본 앱을 제거하면 기기에 저장된 본 앱의 모든 데이터가 함께 삭제됩니다.

### 광고 식별자 삭제
- 안드로이드 **설정** → **Google** → **광고** → **광고 ID 삭제**에서 재설정/삭제할 수 있습니다.

본 앱은 외부 서버에 사용자 데이터를 보관하지 않으므로, **삭제 요청을 위해 개발자에게 별도로 연락할 필요가 없습니다**. 다만 문의가 있을 경우 아래 7항의 연락처로 요청해 주시면 안내해 드립니다.

---

## 6. 어린이의 개인정보 보호

본 앱은 부모(보호자)가 자녀에게 동화책을 읽어 주는 데 사용하도록 설계되었으며, **만 13세 미만 어린이를 직접 대상으로 하지 않습니다**. 어린이가 직접 본 앱을 사용하는 경우에도 본 앱은 어린이의 개인정보를 식별·수집·저장하지 않습니다.

보호자께서 자녀가 본 앱에 정보를 입력했다고 생각하시는 경우, 위 5항의 데이터 삭제 방법을 사용하시거나 아래 연락처로 문의해 주시기 바랍니다.

---

## 7. 개발자 연락처

본 개인정보처리방침에 대한 문의·요청은 아래로 연락 주시기 바랍니다.

- **개발자명:** LazyDaddyPresent
- **이메일:** ocxeverywhere@gmail.com
- **국가/지역:** 대한민국

---

## 8. 본 방침의 변경

본 개인정보처리방침의 내용이 변경될 경우, 변경 사항은 본 페이지에 게시되며 "최종 수정일"이 갱신됩니다. 중대한 변경이 있을 경우 앱 내 공지를 통해 안내드릴 수 있습니다.

---

# Privacy Policy (English Summary)

**App:** LazyDaddy
**Package:** `io.ocxeverywhere.easyreader`
**Effective:** May 12, 2026

LazyDaddy is a Korean children's storybook reader for parents. The app does not collect personal account information (name, email, phone).

- **Camera permission** is used solely to let the user photograph a storybook page so that on-device OCR (Google ML Kit, Korean) can extract its text. Images are never transmitted off-device and are not retained after the book is saved.
- **All saved books, page images, and audio caches are stored locally on the device only.** There is no cloud sync or server backup.
- **Third-party services:**
  - Google Cloud Text-to-Speech / Google Gemini API: receives only the book text the user asks the app to read aloud.
  - Google AdMob: receives standard advertising signals (Google Advertising ID, coarse IP, device/OS info, ad events) to serve ads.
  - Google ML Kit Korean text recognition: runs on-device; no data leaves the device.
- **Data deletion:** Delete individual books inside the app, clear app data in Android Settings, or uninstall the app. Because no user data is held on remote servers, no separate deletion request is required.
- **Children:** The app is intended for parents, not for direct use by children under 13. It does not knowingly collect personal information from children.

For questions, contact: ocxeverywhere@gmail.com
