# FFmpeg

- **저장소:** https://github.com/FFmpeg/FFmpeg (미러, 원본 https://git.ffmpeg.org/ffmpeg.git)
- **별:** 약 68,054개 (2026-11-25 확인)
- **라이선스:** 주로 LGPL, 일부 GPL

## 용도
오디오·비디오·자막·메타데이터를 처리하는 멀티미디어 도구 모음. MG의 영상/쇼츠 제작에서 모든 영상의 컷 조립, 자막 입히기, 오디오 믹스, 인코딩을 맡는 기본 도구.

## 핵심 기능
- `ffmpeg`: 변환·자르기·합치기·리사이즈·자막 합성·오디오 믹스·스트리밍용 CLI
- `ffprobe`: 코덱·해상도·길이 등 미디어 정보 조회
- `ffplay`: 간단한 미디어 플레이어
- 라이브러리: `libavcodec`(코덱), `libavformat`(컨테이너/스트리밍), `libavfilter`(필터 그래프), `libswscale`(색 변환·스케일), `libswresample`(오디오 리샘플)

## MG의 쇼츠/영상 제작에서 활용
- 1080×1920 세로 쇼츠로 자르기·리사이즈, 10초 단위 컷 나누기
- 자막(.srt/.ass) 영상에 굽기: `ffmpeg -i in.mp4 -vf subtitles=sub.srt out.mp4`
- 내레이션·BGM 믹스, 볼륨 정규화, 무음 구간 제거
- MP4/WebM 인코딩, 썸네일 프레임 추출: `ffmpeg -i in.mp4 -ss 00:00:01 -vframes 1 thumb.jpg`
- 여러 클립 연결(concat), 속도 조절, 페이드 인/아웃

## 설치 / 기본 사용법
- Windows: 공식 빌드 다운로드(ffmpeg.org) 또는 `winget install FFmpeg`
- macOS: `brew install ffmpeg`
- Linux: `apt install ffmpeg` / `dnf install ffmpeg`
- 버전 확인: `ffmpeg -version`
- 주의: GitHub 저장소는 미러라 PR은 받지 않음. 공식 문서 ffmpeg.org 참조.

## 함께 쓰는 도구
faster-whisper(자막 생성) → FFmpeg(자막 굽기·합성), yt-dlp(자료 다운로드) → FFmpeg(변환), OpenCV/rembg(프레임 처리) → FFmpeg(조립)
