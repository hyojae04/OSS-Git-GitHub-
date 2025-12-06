# 📘 Git & GitHub 주차별 정리 (1~15주차)

## **1주차 — Git & 오픈소스 기본 개념**

### ✔ Git이란?

* 리눅스 토발즈가 만든 **분산 버전 관리 시스템**
* 모든 개발자가 로컬에 전체 히스토리를 보관 → 빠르고 안전함

### ✔ GitHub란?

* Git 저장소를 클라우드에 올려 협업을 가능하게 하는 플랫폼
* Pull Request, Issue, Wiki 등 협업용 기능 제공
<img width="2816" height="1536" alt="Gemini_Generated_Image_qe2rr2qe2rr2qe2r" src="https://github.com/user-attachments/assets/d8cdfd86-34db-4f07-82ca-ff3d403c3c90" />



### ✔ 오픈소스 특징

* 누구나 코드 열람·수정 가능
* 라이선스에 따라 사용/배포 조건이 다름
* 대표 사례: Linux, VS Code, React
<img width="2816" height="1536" alt="Gemini_Generated_Image_36h9nd36h9nd36h9" src="https://github.com/user-attachments/assets/b8e32681-628e-48dd-8a3f-07d60c7ad30b" />


---

## **2주차 — Git 설치 & 환경 설정 + 리눅스 기초**

### ✔ Git 환경 설정 (Windows)

```bash
git config --global user.name "이름"
git config --global user.email "이메일"
git config --global core.autocrlf input
git config --global init.defaultBranch main
```
<img width="2816" height="1536" alt="Gemini_Generated_Image_ru3cperu3cperu3c" src="https://github.com/user-attachments/assets/f786c29a-73e0-4ebf-b04a-84501e71504f" />


### ✔ 리눅스 필수 명령어

* `ls` : 파일 목록 확인
* `cd` : 디렉토리 이동
* `pwd` : 현재 위치 확인
* `mkdir` : 폴더 생성
* `touch` : 빈 파일 만들기
<img width="2816" height="1536" alt="Gemini_Generated_Image_5cfirc5cfirc5cfi" src="https://github.com/user-attachments/assets/a56d0468-f8eb-4fc5-b0a7-18bc5973c687" />

### ✔ Git 저장소 생성

```bash
git init
```
→ .git 폴더가 생기고 Git으로 버전 관리 시작
<img width="2816" height="1536" alt="Gemini_Generated_Image_983owf983owf983o" src="https://github.com/user-attachments/assets/a071ce42-117a-4d65-9128-b9c52d18d090" />
---

## **3주차 — 버전 관리(Commit) 개념 정복**

### ✔ Git의 3영역 구조

1. **Working Directory**: 실제 파일이 있는 공간
2. **Staging Area(index)**: commit으로 묶을 파일들을 올려두는 대기 공간
3. **Repository**: 최종 기록(commit)이 저장되는 공간
<img width="2816" height="1536" alt="Gemini_Generated_Image_wdgq2pwdgq2pwdgq" src="https://github.com/user-attachments/assets/ccf14f2f-6b07-4200-a2fb-835a459f7817" />

### ✔ 기본 작업 흐름

```bash
git add 파일명    # 스테이지에 올리기
git commit -m "메시지"  # 버전 생성
git status         # 상태 확인
git log            # 커밋 이력 확인
```

### ✔ 버전 과거로 이동

```bash
git checkout 커밋ID
```

→ 코드 수정용이 아닌 ‘과거 조회용’

---

## **4주차 — 파일 비교·삭제·복원 완전 정복**

### ✔ 파일 차이 비교

```bash
git diff            # 작업 디렉토리 ↔ 스테이지
git diff --staged   # 스테이지 ↔ 저장소
```

### ✔ 파일 삭제

```bash
git rm 파일명
```
<img width="2816" height="1536" alt="Gemini_Generated_Image_c37f64c37f64c37f" src="https://github.com/user-attachments/assets/d15df703-c477-4a22-b27e-bf90becf0c8a" />

→ 삭제된 상태까지 커밋됨

### ✔ 스테이징 취소 & 복원

```bash
git restore 파일명            # 작업 디렉토리 복원
git restore --staged 파일명   # 스테이징 취소
```
<img width="2816" height="1536" alt="Gemini_Generated_Image_bmvfcpbmvfcpbmvf" src="https://github.com/user-attachments/assets/88ed15e5-d6a3-4ce8-916a-2a8a3c749077" />

---

## **5주차 — 태그(Tag) & 브랜치 상세**

### ✔ 태그(Tag)

* 특정 버전에 이름 부여(배포 버전 표시)

```bash
git tag v1.0
```

### ✔ 브랜치

* 새로운 기능 개발, 실험 코드 분리 등에 활용

```bash
git branch feature/login
git switch feature/login
# 혹은 생성 + 이동
git switch -c feature/login
```

### ✔ 브랜치 삭제

```bash
git branch -d 브랜치명
```

---

## **6주차 — 원격 저장소(GitHub) 연동 상세**

### ✔ 원격 추가 & 확인

```bash
git remote add origin URL
git remote -v
```

### ✔ push / pull / fetch

* `push`: 로컬 → 원격 업로드
* `pull`: 원격 → 로컬 다운로드 + merge
* `fetch`: 다운로드만 하고 merge는 하지 않음

### ✔ 인증(PAT) 원리

* 비밀번호 대신 GitHub Personal Access Token (PAT)사용
* HTTPS 기반 저장소 접근에 필수

---

## **7주차 — 라이선스 적용 & Stash 활용**

### ✔ 오픈소스 라이선스

* **MIT**: 거의 모든 자유 허용, 보편적
* **GPL**: 소스 공개 강제(강한 카피레프트)
* **Apache 2.0**: 특허 관련 보호 포함

### ✔ stash (임시저장)

```bash
git stash push    # 작업 내용 숨김
git stash list    # 목록 확인
git stash pop     # 꺼내오기
git stash apply   # 복원만, stash 유지
```

---

## **8주차 — Merge 상세 + 충돌 해결**

### ✔ Fast-forward merge

* 브랜치가 단순히 앞으로 이동하는 가장 간단한 병합

### ✔ 3-way merge

* 서로 다른 히스토리 병합
* 충돌 발생 가능

### ✔ 충돌 해결 개념

* 파일 내부에 `<<<<<<<`, `=======`, `>>>>>>>` 형식으로 표시됨
* 개발자가 직접 수정 후 커밋

---

## **9주차 — Rebase & 커밋 정리**

### ✔ Rebase란?

* 브랜치의 시작점을 새로 재배치해 히스토리를 깔끔하게 만드는 기술

```bash
git rebase main
```

### ✔ 커밋 수정

```bash
git commit --amend   # 가장 최근 커밋 메시지/내용 수정
git rebase -i HEAD~3 # 최근 3개 커밋 정리
```

---

## **10주차 — Reset vs Revert 상세 비교**

### ✔ Reset (이력 자체를 변경)

* 위험하지만 강력
* 종류:

  * soft: 커밋만 취소, 파일은 그대로
  * mixed: 스테이징 취소
  * hard: **모든 변경 삭제**

```bash
git reset --hard 커밋ID
```

### ✔ Revert (안전한 되돌리기)

* 기존 커밋은 남기고 ‘반대로 되돌리는 커밋’을 하나 더 생성

```bash
git revert 커밋ID
```

