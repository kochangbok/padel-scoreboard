# 📊 Google Analytics 설정 가이드

Google Analytics를 통해 방문자 통계를 확인할 수 있습니다.

## 🚀 설정 방법 (5분)

### 1단계: Google Analytics 계정 만들기

1. **https://analytics.google.com/** 접속
2. 구글 계정으로 로그인
3. "측정 시작" 버튼 클릭

### 2단계: 속성 생성

1. **계정 이름**: "빠델 스코어보드" (원하는 이름)
2. **속성 이름**: "Padel Scoreboard"
3. **보고 시간대**: "대한민국"
4. **통화**: "대한민국 원 (₩)"

### 3단계: 데이터 스트림 설정

1. **플랫폼**: "웹" 선택
2. **웹사이트 URL**: `https://padel-scoreboard-mu.vercel.app`
3. **스트림 이름**: "빠델 스코어보드"
4. "스트림 만들기" 클릭

### 4단계: 측정 ID 복사

생성 후 나오는 **측정 ID**를 복사하세요:
- 형식: `G-XXXXXXXXXX` (G- 로 시작하는 코드)
- 예: `G-ABC123XYZ9`

### 5단계: 측정 ID 적용

**index.html** 파일에서 두 곳의 `G-XXXXXXXXXX`를 실제 측정 ID로 변경:

```html
<!-- 수정 전 -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
    gtag('config', 'G-XXXXXXXXXX');
</script>

<!-- 수정 후 (예시) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-ABC123XYZ9"></script>
<script>
    gtag('config', 'G-ABC123XYZ9');
</script>
```

---

## 📈 확인 가능한 통계

Google Analytics에서 다음을 확인할 수 있습니다:

### 실시간
- 현재 접속자 수
- 어느 페이지를 보고 있는지
- 어느 나라에서 접속하는지

### 사용자
- 총 방문자 수
- 신규 vs 재방문
- 평균 체류 시간
- 이탈률

### 획득
- 어디서 유입되었는지 (직접 입력, SNS 등)
- 검색 키워드 (일부)

### 참여도
- 인기 있는 기능
- 언어 선택 비율
- 득점 버튼 클릭 수

### 기술
- 모바일 vs PC 비율
- 운영체제 (iOS, Android, Windows)
- 브라우저 종류
- 화면 해상도

### 위치
- 국가별 방문자
- 도시별 방문자

---

## ⏱️ 데이터 확인 시간

- **실시간**: 즉시 확인 가능
- **보고서**: 24~48시간 후부터 정확한 데이터

---

## 💡 추가 팁

### 이벤트 추적 (선택)
득점 버튼 클릭, 모드 선택 등을 별도로 추적하려면:

```javascript
// 득점 버튼 클릭 추적 예시
gtag('event', 'score_button_click', {
    'team': 1,
    'game_mode': 'official'
});
```

### 개인정보 보호
- Google Analytics는 개인 식별 정보를 수집하지 않습니다
- IP 주소는 익명화됩니다
- 쿠키 사용 동의가 필요할 수 있습니다

---

## 🔗 유용한 링크

- [Google Analytics 시작하기](https://support.google.com/analytics/answer/9304153)
- [측정 ID 찾기](https://support.google.com/analytics/answer/9539598)
- [실시간 보고서](https://support.google.com/analytics/answer/9271392)

---

## ❓ 문제 해결

### "데이터가 보이지 않아요"
- 24시간 기다려보세요
- 측정 ID가 정확한지 확인
- 브라우저 캐시 삭제 후 다시 접속

### "실시간에 내가 안 보여요"
- 시크릿 모드로 접속해보세요
- Ad Blocker 비활성화

---

**설정 완료 후 측정 ID를 알려주시면 제가 코드에 적용해드리겠습니다!** 📊
