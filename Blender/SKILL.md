# Blender

- **저장소:** https://github.com/blender/blender (공식 미러)
- **별:** 약 22,417개 (2026-11-25 확인)
- **라이선스:** GPL v3

## 용도
무료 오픈소스 3D 제작 스위트. 3D 파이프라인 전체를 지원.

## 핵심 기능
- 모델링·리깅·애니메이션·시뮬레이션·렌더링·합성·모션 트래킹·비디오 편집
- Cycles/Eevee 렌더러, Geometry Nodes, Grease Pencil
- Python API로 자동화 가능 (스크립트·애드온)

## MG의 쇼츠/영상 제작에서 활용
- three.js 프리비즈를 옮겨 실사 렌더하는 최종 3D 영상 제작
- 블록 3D 과학/액션 쇼츠, 캐릭터·소품 모델링과 애니메이션
- 썸네일용 3D 장면 렌더, 타이틀 3D 모션
- blender-mcp / blender-skills와 함께 AI가 Blender를 직접 조작

## 설치 / 기본 사용법
- 공식 사이트 blender.org에서 설치 프로그램 다운로드 (Windows/macOS/Linux)
- 소스 빌드는 developer.blender.org의 빌드 안내 참조
- GitHub 미러 클론 시 `GIT_LFS_SKIP_SMUDGE=1 git clone` 권장 (LFS 오류 방지)
- Python 스크립트 실행: Blender 내 Scripting 탭, 또는 `blender -b -P script.py`

## 함께 쓰는 도구
three.js(프리비즈), blender-mcp(AI 조작 연결), blender-skills(94종 작업 요령), FFmpeg(렌더 결과 합성)
