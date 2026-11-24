# faster-whisper

- **저장소:** https://github.com/SYSTRAN/faster-whisper
- **별:** 약 26,983개 (2026-11-25 확인)
- **라이선스:** MIT

## 용도
OpenAI Whisper를 CTranslate2로 다시 구현한 음성 인식(STT). 같은 정확도로 최대 4배 빠르고 메모리도 적게 씀. 8비트 양자화 지원.

## 핵심 기능
- tiny/base/small/medium/large-v3, distil-whisper-large-v3, turbo 모델 지원
- 단어 단위 타임스탬프, VAD(무음 구간) 필터, 배치 전사
- GPU(CUDA 12, cuDNN 9) / CPU 모두 동작, FFmpeg 별도 설치 불필요(PyAV 내장)

## MG의 쇼츠/영상 제작에서 활용
- 내레이션을 받아쓰고 자막 타이밍을 맞추는 핵심 도구
- 단어 자막(한 줄씩 타이밍 맞는 자막) 생성 → FFmpeg으로 영상에 굽기
- 롱폼 영상의 대본을 자동 전사해 바이럴 구간 찾기

## 설치 / 기본 사용법
```bash
pip install faster-whisper
# GPU: pip install nvidia-cublas-cu12 nvidia-cudnn-cu12==9.*
```
```python
from faster_whisper import WhisperModel
model = WhisperModel("large-v3", device="cuda", compute_type="float16")
# CPU면 device="cpu", compute_type="int8"
segments, info = model.transcribe("audio.mp3", beam_size=5, word_timestamps=True)
for s in segments:
    print(f"[{s.start:.2f} -> {s.end:.2f}] {s.text}")
```
- 한국어: `model.transcribe("audio.mp3", language="ko")`로 지정 가능

## 함께 쓰는 도구
FFmpeg(자막 굽기·오디오 추출), edge-tts/Chatterbox(내레이션 생성 → 받아쓰기 검증), librosa(오디오 분석)
