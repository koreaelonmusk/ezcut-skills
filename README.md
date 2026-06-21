# EZcut Hermes Agent Skills

EZCut 프롬프트→영상 편집 에이전트(Hermes)의 **공개 기본 스킬 레지스트리**입니다.

> ⚠️ **라이선스 / 영리 이용 금지** — 이 저장소의 모든 스킬은 **EZCut 자산**입니다.
> 공개분은 **기본(basic) 샘플뿐**이며 전체 라이브러리는 비공개입니다.
> **개인·비영리 학습/평가만 허용**. 영리적 이용·재배포·2차 저작·경쟁 제품 편입·ML 학습데이터 사용·대량 추출은
> **사전 서면 동의 없이 금지**합니다. 자세한 내용은 [LICENSE](LICENSE). 영리 라이선스 문의: repo 소유자.

---

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

## 저작권
© EZCut (koreaelonmusk). 무단 영리 이용 시 저작권 및 관련 법률에 따라 책임을 물을 수 있습니다.
