# librosa

- **저장소:** https://github.com/librosa/librosa
- **별:** 약 9,152개 (2026-11-25 확인)
- **라이선스:** ISC

## 용도
오디오·음악 분석용 Python 라이브러리. 음악 정보 검색(MIR)의 기초 알고리즘 제공.

## 핵심 기능
- 오디오 로드·리샘플, 스펙트로그램·멜 스펙트로그램·MFCC
- 박자(beat) 추적·템포 추정, 온셋 검출, 피치·크로마 분석
- 무음 구간 검출, 음량(RMS)·스펙트럼 분석

## MG의 쇼츠/영상 제작에서 활용
- 음악 박자와 음량을 분석해 컷 타이밍을 맞추는 오디오 분석
- BGM 박자에 맞춰 장면 전환·자막 팝업 타이밍 자동 계산
- 무음 구간·박자 위치를 찾아 하이라이트 컷 추출 기준 제공
- Demucs 분리 스템과 박자 동기화

## 설치 / 기본 사용법
```bash
pip install librosa
# conda: conda install -c conda-forge librosa
```
```python
import librosa
y, sr = librosa.load("bgm.mp3", sr=22050)
tempo, beats = librosa.beat.beat_track(y=y, sr=sr)
print("템포:", tempo)
beat_times = librosa.frames_to_time(beats, sr=sr)
# 무음 구간
intervals = librosa.effects.split(y, top_db=30)
# 스펙트로그램
S = librosa.feature.melspectrogram(y=y, sr=sr)
```

## 함께 쓰는 도구
FFmpeg(오디오 추출), Demucs(스템 분리 후 박자 분석), faster-whisper(음성 구간과 박자 대조)
