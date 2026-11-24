# 영상/쇼츠 제작 도구 20종

MG의 영상·쇼츠 제작용 GitHub 도구 정리. 각 저장소의 README를 읽고 한국어로 요약한 것 (2026-11-25 확인). GitHub fork/star는 하지 않음.

## 전체 목록

| # | 도구 | 한 줄 요약 | 폴더 |
|---|------|-----------|------|
| 1 | FFmpeg | 모든 영상의 컷 조립·자막·오디오 믹스·인코딩을 맡는 기본 도구 | [FFmpeg/SKILL.md](sandbox://workspace/custom-skills/video-tools/FFmpeg/SKILL.md) |
| 2 | three.js | 3D 장면의 카메라와 움직임을 실시간으로 잡는 프리비즈 엔진 | [three.js/SKILL.md](sandbox://workspace/custom-skills/video-tools/three.js/SKILL.md) |
| 3 | Pillow | 자막 카드·타이틀 카드·썸네일을 그리고 프레임을 합성하는 이미지 라이브러리 | [Pillow/SKILL.md](sandbox://workspace/custom-skills/video-tools/Pillow/SKILL.md) |
| 4 | Blender | 프리비즈를 옮겨 실사 렌더하는 무료 오픈소스 3D 제작 스위트 | [Blender/SKILL.md](sandbox://workspace/custom-skills/video-tools/Blender/SKILL.md) |
| 5 | Playwright | 화면 없이 브라우저를 돌려 프리비즈 정지컷과 웹 캡처를 자동 수집 | [Playwright/SKILL.md](sandbox://workspace/custom-skills/video-tools/Playwright/SKILL.md) |
| 6 | faster-whisper | 내레이션을 받아쓰고 자막 타이밍을 맞추는 빠른 음성 인식 | [faster-whisper/SKILL.md](sandbox://workspace/custom-skills/video-tools/faster-whisper/SKILL.md) |
| 7 | yt-dlp | 쇼츠에 넣을 실사 영상 자료를 내려받는 다운로더 (저작권 주의) | [yt-dlp/SKILL.md](sandbox://workspace/custom-skills/video-tools/yt-dlp/SKILL.md) |
| 8 | Remotion | React 코드로 모션 그래픽을 렌더하는 영상 프레임워크 | [Remotion/SKILL.md](sandbox://workspace/custom-skills/video-tools/Remotion/SKILL.md) |
| 9 | Chatterbox | 캐릭터 목소리를 로컬에서 만드는 오픈소스 TTS (보관 상태 주의) | [Chatterbox/SKILL.md](sandbox://workspace/custom-skills/video-tools/Chatterbox/SKILL.md) |
| 10 | Real-ESRGAN | 오래되거나 흐린 자료 사진을 선명하게 키우는 업스케일러 | [Real-ESRGAN/SKILL.md](sandbox://workspace/custom-skills/video-tools/Real-ESRGAN/SKILL.md) |
| 11 | OpenCV | 프레임을 비교하고 잘라내고 색을 보정하는 영상 처리 라이브러리 | [OpenCV/SKILL.md](sandbox://workspace/custom-skills/video-tools/OpenCV/SKILL.md) |
| 12 | Hahmlet | 쇼츠 한 줄 자막에 쓰는 개성 있는 한글 폰트 | [Hahmlet/SKILL.md](sandbox://workspace/custom-skills/video-tools/Hahmlet/SKILL.md) |
| 13 | blender-mcp | Claude가 Blender를 직접 조작하게 이어 주는 MCP 연결 도구 | [blender-mcp/SKILL.md](sandbox://workspace/custom-skills/video-tools/blender-mcp/SKILL.md) |
| 14 | edge-tts | 무료로 시험용 내레이션을 빠르게 뽑는 음성 합성 | [edge-tts/SKILL.md](sandbox://workspace/custom-skills/video-tools/edge-tts/SKILL.md) |
| 15 | Seed-VC | 녹음한 목소리를 캐릭터 목소리로 바꾸는 음성 변환 (보관 상태 주의) | [Seed-VC/SKILL.md](sandbox://workspace/custom-skills/video-tools/Seed-VC/SKILL.md) |
| 16 | Supertonic | 가볍게 돌아가는 온디바이스 다국어 TTS (보관 상태 주의) | [Supertonic/SKILL.md](sandbox://workspace/custom-skills/video-tools/Supertonic/SKILL.md) |
| 17 | Demucs | 음악에서 보컬과 반주를 분리하는 도구 (보관 상태 주의) | [Demucs/SKILL.md](sandbox://workspace/custom-skills/video-tools/Demucs/SKILL.md) |
| 18 | rembg | 사진 배경을 자동으로 지우는 누끼 도구 | [rembg/SKILL.md](sandbox://workspace/custom-skills/video-tools/rembg/SKILL.md) |
| 19 | librosa | 음악 박자와 음량을 분석해 컷 타이밍을 맞추는 오디오 분석 라이브러리 | [librosa/SKILL.md](sandbox://workspace/custom-skills/video-tools/librosa/SKILL.md) |
| 20 | blender-skills | Blender 작업 요령 94종을 담은 Claude용 스킬 모음 | [blender-skills/SKILL.md](sandbox://workspace/custom-skills/video-tools/blender-skills/SKILL.md) |

## 분야별 묶음

- **영상 조립·인코딩:** FFmpeg, OpenCV
- **3D:** three.js(프리비즈), Blender(렌더), blender-mcp(AI 조작), blender-skills(작업 요령)
- **이미지:** Pillow, Real-ESRGAN, rembg, Hahmlet(폰트)
- **음성·자막:** faster-whisper, edge-tts, Chatterbox, Supertonic, Seed-VC
- **오디오·음악:** Demucs, librosa
- **자료·자동화:** yt-dlp, Playwright, Remotion

## 표준 쇼츠 파이프라인

1. 자료 수집: yt-dlp / Playwright
2. 3D 프리비즈: three.js → Blender (+ blender-mcp, blender-skills)
3. 이미지 준비: Real-ESRGAN, rembg, Pillow(+ Hahmlet)
4. 내레이션: edge-tts(초안) → Chatterbox/Supertonic(최종) → Seed-VC(캐릭터 목소리)
5. 자막: faster-whisper(단어 타임스탬프)
6. 음악: Demucs(스템 분리) + librosa(박자 타이밍)
7. 조립: FFmpeg(컷·자막·믹스·인코딩) / Remotion(모션 그래픽)

## 주의

- Chatterbox, Seed-VC, Supertonic, Demucs는 보관(archived)·유지보수 중단 상태. 사용은 가능하나 업데이트가 없음.
- yt-dlp로 받은 저작권 영상은 무단 재사용 금지. 본인 영상·무료 라이선스 자료·참고용 분석에만 사용할 것.
- Remotion은 상업 사용 시 라이선스 조건 확인 필요.
