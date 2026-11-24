# blender-mcp

- **저장소:** https://github.com/ahujasid/blender-mcp (현재 이름: mcp-for-blender, PyPI 패키지 `mcp-for-blender`)
- **별:** 약 35,645개 (2026-11-25 확인)
- **라이선스:** MIT
- **주의:** Blender Foundation 공식이 아닌 커뮤니티 플러그인

## 용도
Claude 등 LLM이 Blender 3D를 직접 조작하게 이어 주는 MCP(Model Context Protocol) 연결 도구.

## 핵심 기능
- 양방향 통신: AI가 Blender에 오브젝트 생성·수정·삭제, 재질·색상 적용
- 시각 검증: 다각도·와이어프레임·X-ray·렌더 뷰로 AI가 스스로 결과 확인
- 코드 실행: AI가 Blender Python을 직접 작성·실행
- 에셋 생성: Poly Haven, Sketchfab, Poly Pizza, Meshy/Tripo/Hunyuan3D AI 3D 모델 연동

## MG의 쇼츠/영상 제작에서 활용
- Claude가 Blender를 직접 조작하게 이어 주는 연결 도구 — "블록 세계에 집을 지어줘" 같은 말로 3D 장면 생성
- blender-skills(94종)와 함께 쓰면 프롬프트만으로 모델링→조명→렌더 파이프라인 실행
- 프리비즈 장면을 Blender 실사 렌더로 바로 연결

## 설치 / 기본 사용법
```bash
# macOS/Linux 자동 설치
curl -LsSf https://www.mcp-for-blender.com/install.sh | sh
# Windows PowerShell
irm https://www.mcp-for-blender.com/install.ps1 | iex
# 이미 uv가 있으면
uvx mcp-for-blender setup
```
- 필요: Blender 3.0+, Python 3.10+, uv
- Claude Code: `claude mcp add blender uvx mcp-for-blender`
- Blender에서 애드온 설치: `uvx mcp-for-blender install-addon` → Edit → Preferences → Add-ons → Interface: MCP for Blender 활성화
- Blender 3D 뷰에서 `N` 키 → MCP for Blender 탭 → Start MCP Server

## 함께 쓰는 도구
Blender(본체), blender-skills(작업 요령 94종), three.js(프리비즈)
