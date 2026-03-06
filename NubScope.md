# 🚀 NubScope — GitHub → Render 배포 가이드

---

## 1단계 · GitHub 레포 생성

```bash
# 프로젝트 폴더로 이동
cd nub-theory-app

# Git 초기화
git init
git add .
git commit -m "first commit"

# GitHub에서 새 레포 생성 후 (예: nubscope)
git remote add origin https://github.com/YOUR_USERNAME/nubscope.git
git branch -M main
git push -u origin main
```

> **⚠️ `.env.local` 파일은 절대 push하지 마세요.**  
> `.gitignore`에 `.env.local`이 포함되어 있는지 확인하세요.

---

## 2단계 · Render 배포 설정

1. [https://render.com](https://render.com) 접속 → 회원가입 / 로그인
2. **New +** → **Web Service** 클릭
3. **GitHub 연결** → `nubscope` 레포 선택

### Build & Deploy 설정

| 항목 | 값 |
|---|---|
| **Name** | `nubscope` (원하는 이름) |
| **Region** | Singapore (한국에서 가장 가까움) |
| **Branch** | `main` |
| **Runtime** | `Node` |
| **Build Command** | `npm install && npm run build` |
| **Start Command** | `npm start` |
| **Instance Type** | `Free` (무료 플랜) |

---

## 3단계 · 환경변수 설정 (중요!)

Render 대시보드 → 해당 서비스 → **Environment** 탭

| Key | Value |
|---|---|
| `ANTHROPIC_API_KEY` | `sk-ant-xxxxxx...` |
| `NODE_VERSION` | `20` |

> API 키는 [https://console.anthropic.com](https://console.anthropic.com) 에서 발급

---

## 4단계 · 배포 완료

- **Manual Deploy** → **Deploy latest commit** 클릭
- 약 2~3분 후 배포 완료
- 주소 형식: `https://nubscope.onrender.com`

---

## ✅ 체크리스트

- [ ] `.gitignore`에 `.env.local` 포함 확인
- [ ] Render Environment에 `ANTHROPIC_API_KEY` 입력
- [ ] Build Command: `npm install && npm run build`
- [ ] Start Command: `npm start`
- [ ] Node version: `20`

---

## ⚠️ 무료 플랜 주의사항

- **15분 비활성 시 슬립** → 첫 요청 시 30초~1분 대기
- 슬립 방지하려면 **Starter 플랜** ($7/월) 업그레이드
- 또는 [UptimeRobot](https://uptimerobot.com) 으로 5분마다 핑 전송 (무료 우회)

---

## 🔗 배포 후 공유

```
https://nubscope.onrender.com
```

이 링크를 그대로 공유하면 됩니다. PWA이므로 모바일에서 **홈 화면에 추가**도 가능합니다.
