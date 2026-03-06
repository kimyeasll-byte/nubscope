# 🚀 NubScope — GitHub Pages 배포 가이드

단일 `index.html` 파일 하나로 무료 배포합니다.

---

## 1단계 · GitHub 레포 생성

1. [github.com/new](https://github.com/new) 접속
2. Repository name: `nubscope` (원하는 이름)
3. **Public** 선택 → **Create repository**

---

## 2단계 · index.html 업로드

```
레포 메인 페이지 → Add file → Upload files
→ index.html 드래그 앤 드롭
→ Commit changes
```

또는 git으로:
```bash
git init
git add index.html
git commit -m "init"
git remote add origin https://github.com/YOUR_ID/nubscope.git
git push -u origin main
```

---

## 3단계 · GitHub Pages 활성화

```
레포 → Settings → Pages
→ Source: Deploy from a branch
→ Branch: main / (root)
→ Save
```

약 1~2분 후 배포 완료:
```
https://YOUR_ID.github.io/nubscope
```

---

## ✅ API 키는 어떻게?

이 앱은 **사용자가 직접 API 키를 입력**하는 방식입니다.

- 앱 첫 실행 시 API 키 입력 모달이 뜸
- 키는 **브라우저 localStorage에만 저장** (서버 전송 없음)
- [console.anthropic.com](https://console.anthropic.com) 에서 발급

> 본인 혼자 쓰거나 가족/지인과 공유 시 각자 API 키 입력하면 됩니다.

---

## 비교

| | GitHub Pages | Render |
|---|---|---|
| 비용 | **완전 무료** | 무료(슬립 있음) |
| 서버 필요 | ❌ 불필요 | ✅ 필요 |
| API 키 관리 | 사용자가 직접 입력 | 서버 환경변수 |
| 배포 난이도 | ⭐ 매우 쉬움 | ⭐⭐ 보통 |
| 슬립 이슈 | ❌ 없음 | ✅ 있음 (무료) |
