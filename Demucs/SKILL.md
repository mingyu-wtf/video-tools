# Demucs

- **저장소:** https://github.com/facebookresearch/demucs
- **별:** 약 10,423개 (2026-11-25 확인)
- **라이선스:** MIT
- **주의: 원본 저장소는 보관(archived)·유지보수 중단. 포크 https://github.com/adefossez/demucs 에서 중요 버그 수정만 진행.**

## 용도
음악 소스 분리 모델. 노래 한 곡을 드럼·베이스·보컬·기타 악기로 나눈다.

## 핵심 기능
- Hybrid Transformer Demucs v4 (기본 모델 `htdemucs`, MUSDB HQ 기준 SDR 9.0dB)
- 4개 스템 분리: drums / bass / vocals / other (6개 스템 실험 모델은 guitar·piano 추가)
- `--two-stems=vocals`로 보컬만 분리(가라오케 모드), MP3 출력, Python API

## MG의 쇼츠/영상 제작에서 활용
- 음악에서 보컬과 반주를 분리하는 도구 — BGM에서 보컬만 빼고 반주만 쓰기, 보컬만 따로 효과 주기
- 쇼츠 BGM 정리: 보컬이 거슬리는 구간은 반주만 사용
- 노래 커버·효과음 제작 전 보컬/반주 분리

## 설치 / 기본 사용법
```bash
python3 -m pip install -U demucs   # Python 3.8+
```
```bash
demucs song.mp3
# 결과: separated/htdemucs/song/ 에 drums.wav bass.wav other.wav vocals.wav
demucs --two-stems=vocals song.mp3
demucs --mp3 --mp3-bitrate 320 song.mp3
demucs -n mdx_q song.mp3   # 가벼운 양자화 모델
# GPU 메모리 부족 시: demucs -d cpu song.mp3
```
- Colab 데모, Hugging Face Spaces 웹 데모, GUI(Ultimate Vocal Remover 등)도 있음

## 함께 쓰는 도구
librosa(박자 분석 후 분리 스템과 동기화), FFmpeg(분리 스템 믹스), Seed-VC(분리한 보컬 목소리 변환)
