# Lingbeat 단어팩 저장소 (공식 배포 채널)

Lingbeat 앱이 단어팩을 내려받는 공식 저장소입니다.

- `packs/catalog.app.json` — 카탈로그 (앱이 가장 먼저 읽는 파일)
- `packs/<word>.app_manifest.json` — 단어별 매니페스트 (장면·오디오 경로)
- `packs/<word>.app_wordpack.json` — 단어별 콘텐츠 (계약 스키마 1.0.0)
- `packs/motion_recipes/` · `packs/assets/` — 모션 레시피·SVG·프레임·음원

## 앱 연결 방법

GitHub Pages 활성화 후(Settings → Pages → Branch: main), 카탈로그 주소는:

    https://<계정명>.github.io/lingbeat-packs/packs/catalog.app.json

즉시 테스트(앱 재빌드 없이): 배포된 앱 주소 뒤에

    ?catalog=https://<계정명>.github.io/lingbeat-packs/packs/catalog.app.json

정식 연결(재빌드 시): 빌드 환경 변수

    VITE_WORDPACK_CATALOG_URL=https://<계정명>.github.io/lingbeat-packs/packs/catalog.app.json

## 팩 추가 절차 (매일 배치)

1. 새 단어의 manifest/wordpack/모션/자산을 `packs/` 에 추가
2. `packs/catalog.app.json` 의 `packs[]` 에 항목 추가
3. commit & push — 앱은 다음 접속 때 새 카탈로그를 자동으로 읽음 (캐시는 no-cache)

콘텐츠 수정 금지 원칙: 의미·품사·장면·말풍선은 계약 산출물 그대로 — 저장소에서 직접 편집하지 않는다.
