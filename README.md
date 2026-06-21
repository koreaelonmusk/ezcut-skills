# EZCut Skills Registry

EZCut 마케팅 스킬 마켓플레이스가 런타임에 불러오는 **커뮤니티 스킬 레지스트리**입니다.

## 연결 방법

EZCut 환경변수에 이 repo의 raw URL을 넣으면 끝:

```
VITE_SKILL_REGISTRY_URL=https://raw.githubusercontent.com/koreaelonmusk/ezcut-skills/HEAD/registry.json
```

- 로컬: `.env.local`
- Vercel: Project → Settings → Environment Variables → 재배포
- 여러 소스: 콤마로 구분 `URL1,URL2`

앱이 켜지면 자동으로 fetch → 검증 → 안전 스캔(인젝션/유출 등) → 내장 스킬과 머지해 마켓에 노출합니다.

## 스킬 추가 (registry.json)

`name`과 `prompt`만 필수. 나머지는 자동 기본값.

```json
{
  "version": 1,
  "skills": [
    {
      "id": "my-hook-1",
      "name": "내 시그니처 훅",
      "platform": "tiktok",
      "category": "hook",
      "difficulty": "beginner",
      "description": "첫 1초에 강한 질문으로 멈춰세운다.",
      "tags": ["hook"],
      "author": "your-handle",
      "prompt": "첫 1초에 '이거 진짜야?' 질문 자막을 크게 띄우고 바로 결과로 들어가게 편집해줘.",
      "whenToUse": "정보·리뷰 콘텐츠 도입부에."
    }
  ]
}
```

| 필드 | 값 |
|---|---|
| `platform` | `all` `tiktok` `youtube` `instagram` `reels` |
| `category` | `hook` `retention` `pacing` `caption` `cta` `trend` `aesthetic` |
| `difficulty` | `beginner` `intermediate` `pro` |

## 개별 SKILL.md (hermeshub 방식)

폴더당 스킬을 두려면 `skills/<이름>/SKILL.md`. EZCut 임포트 창에서:

```
github:koreaelonmusk/ezcut-skills/skills/<이름>
```

예시: [skills/cinematic-hook/SKILL.md](skills/cinematic-hook/SKILL.md)

## 안전

EZCut는 가져온 스킬을 추가 전 스캔합니다(프롬프트 인젝션·데이터 유출·자격증명 요구·코드 실행·파괴 명령 등 8 카테고리). 위험 패턴이 있으면 차단됩니다. 스킬은 **영상 편집 프롬프트 텍스트**만 담아주세요.
