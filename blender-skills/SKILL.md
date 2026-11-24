# blender-skills

- **저장소:** https://github.com/arjun988/blender-skills
- **별:** 약 4,826개 (2026-11-25 확인)
- **라이선스:** MIT

## 용도
Cursor·Claude Code·Kiro·Codex용 Blender 전문 스킬 94종 모음. MCP 기반 블록아웃→엔진 내보내기 생산 파이프라인.

## 핵심 기능
- 94개 스킬: 오케스트레이션(blender-director), 모델링, 프로덕션(스컬프팅·리토폴로지·UV·재질), 테크니컬(지오메트리 노드·조명·카메라·렌더링·애니메이션·리깅), 파이프라인(최적화·LOD·내보내기), 스타일(호러·로우폴리·애니메·복셀 등), 세계/장르 연출
- `blender-director`가 요청을 분석해 스킬 체인을 자동 라우팅
- 참조 이미지 매칭: 사진 분석 → 카메라 매칭 → 지오메트리 → 재질 → 조명 → 스크린샷 비교 루프
- 게임 엔진 내보내기: Unreal·Unity·Godot

## MG의 쇼츠/영상 제작에서 활용
- Blender 작업 요령을 담은 Claude용 스킬 모음 — "공포 복도 키트 만들어줘" 같은 요청을 실제 Blender 작업으로 변환
- 블록 3D 쇼츠 파이프라인의 표준 작업 지침서로 사용
- blender-mcp와 함께 쓰면 에이전트가 Blender 안에서 직접 실행

## 설치 / 기본 사용법
```bash
git clone https://github.com/arjun988/blender-skills.git
# Claude Code
cp -r blender-skills/.claude/skills /path/to/your/project/.claude/skills/
# Cursor (Windows)
Copy-Item -Recurse -Force "blender-skills\.claude\skills\*" ".cursor\skills\"
# Kiro / Codex: 각 스킬 디렉토리로 복사 후 재시작
```
- 전제: Blender MCP 연결 (docs/BLENDER_MCP_SETUP.md 참조)
- 사용 예: `"Build a game-ready sci-fi rifle for Unreal Engine, 3k tris, realistic PBR"` → director → hard-surface → uv-workflow → materials → asset-optimization → export-pipeline

## 함께 쓰는 도구
Blender(본체), blender-mcp(MCP 연결), three.js(프리비즈), FFmpeg(렌더 합성)
