# 8470 코미코 스마트팩토리팀 AI 프로젝션

코미코(스마트팩토리팀) ASM Kit AI 프로젝션 프로젝트의 템플릿 및 리소스 저장소입니다.
대용량 바이너리(`.mars` 등)는 **Git LFS**로 관리합니다.

## 저장소 구조

```
.
├── templates/                         # 템플릿 .mars 파일
│   ├── Komico_Template.mars           # 코미코 템플릿 (단일 파일, git 이력으로 버전 관리)
│   └── MediSim_Template.mars          # MediSim 템플릿 (별개 파일)
├── PCView_ASM_Kit/                    # PCView ASM Kit (별개로 버전 관리)
│   └── PCView_ASM Kit_v.1.0_0521.mars
├── docs/
│   └── 코미코_ASM_Kit_씬분석.xlsx      # 씬 분석 문서
├── assets/
│   └── 2D/                            # 2D UI 에셋 (버튼/아이콘 PNG, 제작 가이드)
├── .gitattributes                     # Git LFS 추적 규칙
└── .gitignore
```

## 파일별 버전 관리 정책

### Komico_Template.mars — 단일 파일 관리
- `Komico_Template.mars`(초기 백업본)와 `Komico_Template_260528.mars`(갱신본)는
  **같은 파일의 서로 다른 버전**입니다.
- 날짜 접미사 파일을 따로 두지 않고, **`templates/Komico_Template.mars` 하나의 파일**로 통합하여
  git 커밋 이력으로 버전을 관리합니다.
  - `초기 버전(백업본)` 커밋 → `260528 버전` 커밋
- **앞으로 갱신 시**: 새 날짜 파일을 만들지 말고 동일 파일을 덮어쓴 뒤 커밋하세요.

```bash
# 버전 이력 보기
git log --oneline -- templates/Komico_Template.mars

# 특정 과거 버전 복원 예시
git checkout <commit> -- templates/Komico_Template.mars
```

#### 관련 리소스 (UI 테스트 산출물)
`Komico_Template_260528.mars`의 UI 테스트 산출물(이미지/영상/zip, 약 900MB)은
저장소 용량 문제로 포함하지 않고 **Jira에 보관**되어 있습니다.

- 🔗 https://virtualconnection.atlassian.net/browse/SOLUTION-11887

### MediSim_Template.mars — 별개 파일
- 코미코 템플릿과 무관한 독립 템플릿. 별도로 취급/관리합니다.

### PCView_ASM Kit — 별개 버전 관리
- `PCView_ASM_Kit/` 폴더에서 독립적으로 버전을 관리합니다.
- 현재 버전: `PCView_ASM Kit_v.1.0_0521.mars`

## Git LFS 사용 안내

이 저장소는 `.mars`, `.mp4`, `.zip` 파일을 Git LFS로 추적합니다.
클론 후 LFS 파일을 받으려면:

```bash
git lfs install
git lfs pull
```

추적 대상 확인:

```bash
git lfs ls-files
```
