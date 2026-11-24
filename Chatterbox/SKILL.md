# Chatterbox

- **저장소:** https://github.com/resemble-ai/chatterbox
- **별:** 약 28,071개 (2026-11-25 확인)
- **라이선스:** MIT
- **주의: 2026년 8월 기준 연구 종료·보관 상태(archived). 더 이상 유지보수되지 않음.**

## 용도
Resemble AI의 오픈소스 최신 TTS(텍스트→음성) 모델군. 제로샷 음성 복제 지원.

## 핵심 기능
- **Chatterbox-Turbo** (350M, 영어, 저지연, `[laugh]` `[chuckle]` 등 표현 태그)
- **Chatterbox-Nano** (110M, CPU에서 실시간 3배 속도, 온디바이스용)
- **Chatterbox-Multilingual V3** (500M, 23개+ 언어, 한국어 포함, 음성 복제)
- Single Language Pack (언어별 파인튠 6종)
- 모든 생성 오디오에 PerTh 워터마크 내장

## MG의 쇼츠/영상 제작에서 활용
- 캐릭터 목소리를 로컬에서 만드는 음성 합성 (유키 하나 등 고정 캐릭터 내레이션)
- 10초 참조 음성만으로 목소리 복제 → 대본을 그 목소리로 읽기
- 표현 태그로 웃음·한숨 등 자연스러운 내레이션

## 설치 / 기본 사용법
```bash
pip install chatterbox-tts   # Python 3.11 권장
```
```python
from chatterbox.tts import ChatterboxTTS
import torchaudio as ta
model = ChatterboxTTS.from_pretrained(device="cuda")  # 또는 "cpu"
wav = model.generate("안녕하세요, 오늘의 이야기입니다.", audio_prompt_path="ref.wav")
ta.save("narration.wav", wav, model.sr)
# 다국어: from chatterbox.mtl_tts import ChatterboxMultilingualTTS
# model.generate(text, language_id="ko")
```
- 기본 설정 `exaggeration=0.5, cfg_weight=0.5`가 무난함. 극적 표현은 exaggeration↑, cfg_weight↓

## 함께 쓰는 도구
edge-tts(무료 시험용 내레이션), Supertonic(가벼운 온디바이스 TTS), Seed-VC(목소리 변환), FFmpeg(오디오 믹스)
