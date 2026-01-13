---
title: "macOS 터미널에서 VS Code를 code .으로 실행하기"
date: 2026-01-13
categories: [Development, Tool]
tags: [vscode, macos, terminal]
---
## 1. VS Code에서 `code` 명령어 설치 (필수)

### 가장 간단한 방법
1. **VS Code 실행**
2. 상단 메뉴 → **View → Command Palette**
   - 단축키: `Cmd + Shift + P`
3. 아래 명령어 입력 후 실행
   ```bash
   Shell Command: Install 'code' command in PATH
   ```
4. 설치 완료

---

## 2. 터미널 재시작

설치 후에는 **터미널을 완전히 종료 후 다시 실행**해야 `code` 명령어가 인식됩니다.

---

## 3. 사용 방법
터미널을 실행하고 원하는 프로젝트 폴더로 이동한 후에

```bash
cd 프로젝트_폴더
code .
```

- 현재 디렉토리를 VS Code로 엽니다.

---

## 4. 설치 여부 확인

```bash
which code
```

정상적으로 설치된 경우 예시:
```text
/usr/local/bin/code
```
또는 (Apple Silicon 기준)
```text
/opt/homebrew/bin/code
```

---

## 5. `code` 명령어가 인식되지 않을 때 (zsh 기준)

macOS 기본 쉘(zsh)에서 PATH를 직접 추가합니다.

```bash
echo 'export PATH="$PATH:/Applications/Visual Studio Code.app/Contents/Resources/app/bin"' >> ~/.zshrc
source ~/.zshrc
```

---

## 6. 자주 발생하는 문제

### `command not found: code`
- 터미널 재시작을 하지 않은 경우
- PATH 적용이 되지 않은 경우

→ **1번 단계부터 다시 진행**

---

### VS Code가 `/Applications`에 없는 경우

```bash
ls /Applications | grep "Visual Studio Code"
```

없다면 VS Code를 **Applications 폴더로 이동**해야 합니다.

---

## 7. 자주 사용하는 옵션

```bash
code .        # 현재 폴더 열기
code 파일명   # 특정 파일 열기
code -r .     # 기존 VS Code 창 재사용
```

---

## 8. 한 줄 요약

> **VS Code → Command Palette → “Install 'code' command in PATH” → 터미널 재시작 → `code .`**

---

## 참고
- macOS + zsh 기준
- GitHub Blog / 기술 메모용 문서
