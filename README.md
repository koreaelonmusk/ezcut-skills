# EZcut Hermes Agent Skills

EZCut 프롬프트→영상 편집 에이전트(Hermes)의 **공개 기본 스킬 레지스트리**입니다.

> 공개된 것은 **기본(basic) 스킬**뿐입니다. 전체 2000+ 프로 스킬 라이브러리는 비공개(인앱, 회사 자산)입니다.

## 연결
```
VITE_SKILL_REGISTRY_URL=https://raw.githubusercontent.com/koreaelonmusk/EZcut-hermes-agent-skill/HEAD/registry.json
```
앱이 런타임에 fetch → 검증 → 안전 스캔(인젝션/유출 등) → 인앱 라이브러리와 머지.

## 형식 (registry.json)
`name`과 `prompt`만 필수.
```json
{ "version": 1, "skills": [
  { "id":"my-hook","name":"내 훅","platform":"tiktok","category":"hook",
    "difficulty":"beginner","prompt":"첫 1초에 강한 질문 자막을 띄워줘.","whenToUse":"도입부에." }
]}
```
- platform: `all|tiktok|youtube|instagram|reels` · category: `hook|retention|pacing|caption|cta|trend|aesthetic` · difficulty: `beginner|intermediate|pro`

## 개별 SKILL.md (hermeshub 방식)
`skills/<이름>/SKILL.md` → 임포트 창에 `github:koreaelonmusk/EZcut-hermes-agent-skill/skills/<이름>`

## 안전
가져온 스킬은 추가 전 8 카테고리 위협 스캔(프롬프트 인젝션·데이터 유출·자격증명·코드실행 등). 영상 편집 프롬프트 텍스트만 담아주세요.
