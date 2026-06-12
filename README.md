# 보라해 한글 챌린지 · Borahae Hangul Challenge

K-POPSTAY BUSAN 2026 · BTS ARMY를 위한 보라해 한글 스티커 챌린지 랜딩 페이지.

- **라이브 미리보기:** https://josanku.github.io/hangulmaru/
- **목표 도메인:** https://hangulmaru.com (아래 DNS 전환 후 적용)
- 정적 사이트 (단일 `index.html` + 이미지). 빌드 과정 없음.

## hangulmaru.com 으로 연결하기 (GoDaddy DNS 전환)

현재 `hangulmaru.com` 은 **GoDaddy 웹사이트 빌더의 "곧 시작" 임시 페이지**를 가리키고 있어
인증서 오류(`ERR_CERT_COMMON_NAME_INVALID`)가 납니다. GitHub Pages로 옮기려면:

### 1) GoDaddy DNS 레코드 변경
GoDaddy → 내 도메인 → `hangulmaru.com` → **DNS 관리**

기존 빌더 연결(Forwarding / 임시 A레코드)을 끄고 아래로 설정:

| 유형  | 이름 | 값 |
|------|------|-----|
| A    | @    | 185.199.108.153 |
| A    | @    | 185.199.109.153 |
| A    | @    | 185.199.110.153 |
| A    | @    | 185.199.111.153 |
| CNAME| www  | josanku.github.io |

### 2) GitHub Pages 커스텀 도메인 재설정
Repo `josanku/hangulmaru` → Settings → Pages → **Custom domain** 에 `hangulmaru.com` 입력 후 Save.
DNS 전파(최대 수십 분~수 시간) 후 **Enforce HTTPS** 체크.

> 전환하면 GoDaddy "곧 시작" 페이지 대신 이 사이트가 표시되고, SSL 인증서도 자동 발급됩니다.

## 구조
```
index.html              메인 페이지 (EN/KO 토글)
404.html                index 복사본
favicon.svg
assets/
  poster-challenge.jpg    ① 챌린지 안내 (강조)
  poster-philosophy.jpg   ② 한글 우주 철학 (강조)
  stickers/sticker-1~5.jpg 스티커 5장
robots.txt · sitemap.xml
```
