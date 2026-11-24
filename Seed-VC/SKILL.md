# Seed-VC

- **저장소:** https://github.com/Plachtaa/seed-vc
- **별:** 약 3,906개 (2026-11-25 확인)
- **라이선스:** GPL-3.0
- **주의: 저장소가 보관(archived) 상태. 더 이상 유지보수되지 않음.**

## 용도
제로샷 음성 변환·노래 음성 변환, 실시간 지원. 학습 없이 1~30초 참조 음성만으로 목소리 복제.

## 핵심 기능
- 제로샷 음성 변환(VC), 실시간 음성 변환(약 300ms 지연), 제로샷 노래 음성 변환(SVC)
- v1 모델(VC용·SVC용), v2 모델(음성+억양 변환, 원본 화자 특성 억제 우수)
- 소량 파인튜닝 가능 (화자당 최소 1개 발화, 100스텝·T4 기준 2분)
- 웹 UI(`app_vc.py`, `app_svc.py`), 실시간 GUI

## MG의 쇼츠/영상 제작에서 활용
- 녹음한 목소리를 캐릭터 목소리로 바꾸는 음성 변환 (유키 하나 목소리 고정)
- edge-tts로 만든 평범한 내레이션을 캐릭터 목소리로 변환
- 노래·효과음의 목소리를 캐릭터 톤으로 통일

## 설치 / 기본 사용법
```bash
pip install -r requirements.txt   # Python 3.10 권장, Windows/macOS/Linux
```
```bash
# CLI 변환
python inference.py --source source.wav --target reference.wav --output out/ \
  --diffusion-steps 25 --f0-condition False
# 노래 변환은 --f0-condition True, diffusion-steps 30~50 권장
# 웹 UI
python app_vc.py
# http://localhost:7860 접속
```
- 체크포인트는 첫 실행 시 Hugging Face에서 자동 다운로드

## 함께 쓰는 도구
Chatterbox/edge-tts(원본 내레이션 생성), FFmpeg(오디오 믹스), Demucs(보컬 분리 후 변환)
