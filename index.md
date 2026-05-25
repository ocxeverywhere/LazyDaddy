# 개인정보처리방침 (Privacy Policy)

**앱 이름:** LazyDaddy (게으른 아빠의 동화책 리더)
**패키지명:** `io.ocxeverywhere.easyreader`
**시행일:** 2026년 5월 12일
**최종 수정일:** 2026년 5월 25일

본 개인정보처리방침은 LazyDaddy(이하 "본 앱")가 사용자의 정보를 어떤 방식으로 처리하는지 설명합니다. 본 앱은 부모 또는 보호자가 종이 동화책을 촬영하고, OCR로 추출한 텍스트를 음성으로 들려주는 데 사용하도록 제작되었으며, 어린이 직접 사용을 주된 대상으로 하지 않습니다.

---

## 1. 수집·처리하는 정보

본 앱은 사용자를 식별할 수 있는 계정 정보(이름, 이메일, 전화번호 등)를 **수집하지 않습니다**. 회원 가입, 로그인, 클라우드 계정 동기화 기능도 제공하지 않습니다. 다만 앱 기능 제공을 위해 아래 정보를 처리합니다.

| 항목 | 처리 방식 | 외부 전송 여부 |
|---|---|---|
| 카메라로 촬영한 책 페이지 이미지 | 앱 전용 비공개 저장 영역(`filesDir/photos`)에 저장되어 OCR, 미리보기, 저장된 책의 페이지/표지 표시용으로 사용 | **전송하지 않음** |
| Android Photo Picker로 선택한 이미지 | 선택한 파일을 앱 전용 비공개 저장 영역(`filesDir/photos`)으로 복사하여 OCR, 미리보기, 저장된 책의 페이지/표지 표시용으로 사용 | **전송하지 않음** |
| OCR로 추출하거나 사용자가 수정한 텍스트(동화책 본문) | 기기 내 로컬 데이터베이스(Room)에 저장 | Google Cloud TTS 사용 시 Google에 전송(아래 5항 참조) |
| 책 제목, 페이지 순서, OCR 언어 | 기기 내 로컬 데이터베이스(Room) 또는 로컬 설정에 저장 | **전송하지 않음** |
| TTS 설정(엔진, 목소리, 속도, 높낮이) 및 앱 언어 설정 | 기기 내 로컬 설정(EncryptedSharedPreferences 또는 SharedPreferences)에 저장 | Cloud TTS 요청 시 선택한 목소리/합성 설정 일부가 Google에 전송될 수 있음 |
| Cloud TTS로 생성된 오디오 캐시 | 앱 전용 비공개 저장 영역(`filesDir/audio`)에 저장 | **앱에서 별도로 외부 전송하지 않음** |
| 광고 관련 데이터 | Google Mobile Ads SDK(AdMob)가 광고 로드·표시 시 처리 | Google에 전송(아래 5항 참조) |
| 네트워크 연결 상태 | 광고 또는 Cloud TTS 요청 가능 여부 판단에 사용 | **전송하지 않음** |

본 앱은 위치 권한, 연락처, 통화 기록, SMS, 마이크, 캘린더, 사진/동영상 라이브러리 전체 접근, 신체 활동 정보 등을 수집하지 않습니다.

---

## 2. 권한 사용 목적

본 앱은 Android에서 다음 권한을 사용합니다.

| 권한 | 사용 목적 |
|---|---|
| `android.permission.CAMERA` | 사용자가 책 페이지를 직접 촬영하여 OCR로 텍스트를 추출하기 위해 사용 |
| `android.permission.INTERNET` | Google Cloud Text-to-Speech 요청 및 AdMob 광고 요청에 사용 |
| `android.permission.ACCESS_NETWORK_STATE` | 네트워크 연결 상태를 확인하여 광고 또는 Cloud TTS 요청 가능 여부를 판단하는 데 사용 |

카메라 권한은 사용자가 "사진 찍기" 기능을 선택한 시점에만 런타임에 요청됩니다. 카메라가 없는 기기에서도 본 앱은 설치 가능합니다(`uses-feature android:required="false"`).

갤러리 이미지는 Android Photo Picker를 통해 선택하며, 본 앱은 사진/동영상 라이브러리 전체 접근 권한을 요청하지 않습니다.

---

## 3. OCR 및 이미지 처리

본 앱은 Google ML Kit의 온디바이스(on-device) 텍스트 인식 모델을 사용하여 한국어 및 영어(라틴 문자) OCR을 수행합니다.

- OCR 입력 이미지와 인식 결과 텍스트는 ML Kit OCR 처리 과정에서 Google 서버로 전송되지 않습니다.
- ML Kit는 버그 수정, 모델 업데이트, 하드웨어 가속 호환성 정보 수신을 위해 Google 서버와 통신할 수 있습니다.
- ML Kit는 API 성능, 사용량, 안정성 관련 메트릭을 Google에 전송할 수 있습니다.
- 촬영 또는 선택된 이미지는 앱의 비공개 저장 영역에 보관되며, 사용자가 책이나 페이지를 삭제하거나 앱 데이터를 삭제하면 함께 삭제됩니다.

---

## 4. 데이터 보관 위치 및 기간

본 앱이 생성한 사용자 데이터는 기본적으로 **사용자의 기기 내부에만** 보관됩니다.

- 저장소: 앱 전용 내부 저장 영역의 로컬 데이터베이스(Room), 앱 비공개 파일 디렉터리(`filesDir/photos`, `filesDir/audio`), 로컬 설정 저장소
- 클라우드 동기화, 계정 백업, 개발자 서버 업로드 기능을 제공하지 않습니다.
- 보관 기간: 사용자가 책/페이지를 직접 삭제하거나 앱 데이터를 삭제하거나 앱을 제거할 때까지

Cloud TTS로 생성된 오디오 캐시는 동일 텍스트를 다시 재생할 때 네트워크 요청을 줄이기 위한 용도로만 사용됩니다.

---

## 5. 제3자 서비스 및 외부 전송

본 앱은 다음 Google 서비스를 사용합니다.

### 5.1 Google Cloud Text-to-Speech

- **전송 데이터:** 사용자가 읽어 주기를 요청한 동화책 텍스트, 선택한 음성 이름, 말하기 속도·높낮이 등 음성 합성 설정
- **목적:** 텍스트를 음성으로 변환하여 재생하고, 앱 내부 오디오 캐시에 저장
- **수신자:** Google LLC
- **전송 시점:** 사용자가 Cloud TTS 엔진으로 책을 저장·재생·재생성할 때
- **참고:** Google의 [Cloud TTS 데이터 로깅 문서](https://cloud.google.com/text-to-speech/docs/data-logging)에 따르면 Google은 고객의 Cloud TTS 텍스트 또는 오디오 데이터를 로그로 기록하지 않는다고 안내합니다.

사용자가 Android 기기 내장 TTS 엔진을 선택한 경우, 책 텍스트는 Cloud TTS로 전송되지 않습니다.

### 5.2 Google AdMob / Google Mobile Ads SDK

본 앱은 앱 내 광고를 위해 Google AdMob SDK를 포함합니다. 광고가 로드되거나 표시될 때 Google Mobile Ads SDK는 광고 제공, 분석, 부정행위 방지 목적을 위해 다음 데이터를 자동으로 수집·공유할 수 있습니다.

- IP 주소(대략적인 위치 추정에 사용될 수 있음)
- 사용자 상호작용 정보(앱 실행, 탭, 광고 표시·클릭·동영상 조회 등)
- 진단 정보(앱 및 SDK 성능, 앱 실행 시간, 중단률, 에너지 사용량 등)
- 기기 및 계정 식별자(Android 광고 ID, 앱 세트 ID 등)

모든 AdMob 전송 데이터는 전송 중 암호화됩니다. 사용자는 Android 설정에서 광고 ID를 삭제하거나 재설정할 수 있습니다.

본 앱은 만 13세 미만 어린이를 직접 대상으로 하지 않으며, 부모 또는 보호자를 주 사용자로 하는 앱입니다.

참고: [Google Mobile Ads SDK 데이터 공개 요구사항](https://developers.google.com/admob/android/privacy/play-data-disclosure), [Google 광고 정책](https://policies.google.com/technologies/ads)

### 5.3 Google ML Kit 텍스트 인식

본 앱의 OCR은 온디바이스 ML Kit 텍스트 인식 모델을 사용합니다. OCR 입력 이미지와 OCR 결과 텍스트는 Google 서버로 전송되지 않습니다. 다만 ML Kit는 모델 업데이트, 버그 수정, 호환성 정보 및 API 사용 메트릭 처리를 위해 Google 서버와 통신할 수 있습니다.

참고: [ML Kit 약관 및 개인정보 안내](https://developers.google.com/ml-kit/terms)

---

## 6. 데이터 삭제 방법

사용자는 언제든 본 앱이 저장한 데이터를 다음 방법으로 삭제할 수 있습니다.

### 방법 1 - 앱 내에서 개별 삭제

- 홈 화면에서 책 삭제 기능을 사용하면 해당 책의 텍스트, 페이지 이미지, 표지 이미지, 오디오 캐시가 삭제됩니다.
- 편집 화면에서 페이지를 삭제하거나 사진을 교체하면 더 이상 참조되지 않는 기존 이미지와 해당 페이지의 오디오 캐시가 삭제됩니다.

### 방법 2 - 앱 데이터 전체 초기화(Android 설정)

1. Android **설정** → **앱** → **LazyDaddy** 선택
2. **저장공간** → **데이터 삭제** 또는 **저장공간 및 캐시** → **저장공간 지우기** 선택
3. 앱이 저장한 책, 페이지 이미지, OCR 텍스트, 오디오 캐시, 앱/TTS 설정이 삭제됩니다.

### 방법 3 - 앱 제거

- 본 앱을 제거하면 기기에 저장된 본 앱의 데이터가 함께 삭제됩니다.

### 광고 식별자 삭제

- Android **설정** → **개인정보 보호** 또는 **Google** → **광고** 메뉴에서 광고 ID를 삭제하거나 재설정할 수 있습니다. 기기 제조사와 Android 버전에 따라 메뉴 이름은 다를 수 있습니다.

본 앱은 개발자 서버에 사용자 데이터를 보관하지 않으므로, 서버 데이터 삭제를 위해 개발자에게 별도로 요청할 필요가 없습니다. 다만 문의가 있을 경우 아래 연락처로 요청해 주시면 안내해 드립니다.

---

## 7. 어린이의 개인정보 보호

본 앱은 부모 또는 보호자가 자녀에게 책을 읽어 주기 위해 사용하는 도구로 설계되었으며, **만 13세 미만 어린이를 직접 대상으로 하지 않습니다**. 본 앱은 어린이의 이름, 연락처, 위치 등 개인정보를 의도적으로 수집하지 않습니다.

사용자가 책 제목이나 OCR 텍스트를 직접 수정하는 과정에서 개인정보를 입력하면 해당 내용은 기기 내부에 저장될 수 있으며, Cloud TTS 사용 시 읽어 주기를 요청한 텍스트가 Google Cloud Text-to-Speech로 전송될 수 있습니다. 개인정보가 포함된 텍스트를 입력하지 않도록 주의해 주세요.

보호자께서 자녀가 본 앱에 개인정보를 입력했다고 생각하시는 경우, 위 6항의 데이터 삭제 방법을 사용하시거나 아래 연락처로 문의해 주시기 바랍니다.

---

## 8. 개발자 연락처

본 개인정보처리방침에 대한 문의·요청은 아래로 연락 주시기 바랍니다.

- **개발자명:** LazyDaddyPresent
- **이메일:** ocxeverywhere@gmail.com
- **국가/지역:** 대한민국

---

## 9. 본 방침의 변경

본 개인정보처리방침의 내용이 변경될 경우, 변경 사항은 본 페이지에 게시되며 "최종 수정일"이 갱신됩니다. 중대한 변경이 있을 경우 앱 내 공지 또는 스토어 등록 정보 등을 통해 안내드릴 수 있습니다.

---

# Privacy Policy (English Summary)

**App:** LazyDaddy
**Package:** `io.ocxeverywhere.easyreader`
**Effective:** May 12, 2026
**Last updated:** May 25, 2026

LazyDaddy is a storybook reader app for parents and guardians. It lets users photograph or select book pages, extract Korean or English text with on-device OCR, and play the text aloud with Android built-in TTS or Google Cloud Text-to-Speech.

- The app does not provide accounts, login, cloud sync, or developer-server backup.
- Camera images and Photo Picker images are copied into the app's private storage and used for OCR, preview, saved page images, and cover images. The app does not upload these images.
- OCR text, edited text, book titles, page order, selected OCR language, app language, and TTS settings are stored locally on the device.
- Google Cloud Text-to-Speech receives only the text and voice synthesis settings needed to generate speech when the Cloud TTS engine is used. Built-in Android TTS does not send book text to Cloud TTS.
- Cloud TTS audio files are cached locally under the app's private storage to reduce repeated network requests.
- Google ML Kit OCR runs on-device. Input images and OCR results are not sent to Google servers, although ML Kit may contact Google for model updates, fixes, compatibility information, and API usage metrics.
- Google AdMob / Google Mobile Ads SDK may collect and share IP address, user interactions, diagnostic information, and device/account identifiers for ads, analytics, and fraud prevention when ads are loaded or shown.
- Users can delete data by deleting books or pages in the app, clearing app data in Android Settings, or uninstalling the app.
- The app is intended for parents or guardians, not for direct use by children under 13.

For questions, contact: ocxeverywhere@gmail.com
