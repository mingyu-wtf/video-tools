# rembg

- **저장소:** https://github.com/danielgatis/rembg
- **별:** 약 25,662개 (2026-11-25 확인)
- **라이선스:** MIT

## 용도
이미지 배경 제거 도구. CLI·Python 라이브러리·HTTP 서버·Docker로 사용 가능.

## 핵심 기능
- U2Net 등 다양한 모델 선택 (`u2net`, `u2netp`, `isnet-general-use`, `sam` 등)
- 엣지 모드 3종: 기본(naive), 색 번짐 제거(`-dc`), 알파 매팅(`-a`, 머리카락 등 정교한 가장자리)
- 배치 처리(`rembg p`), 감시 모드(`-w`), FFmpeg 파이프라인 연동(`rembg b`)

## MG의 쇼츠/영상 제작에서 활용
- 사진 배경을 자동으로 지우는 누끼 도구 — 캐릭터·제품 사진을 투명 PNG로 만들어 썸네일·카드뉴스에 합성
- AI 생성 캐릭터를 배경 없이 잘라내 쇼츠 화면에 배치
- Pillow와 함께 배경 제거 → 합성 워크플로

## 설치 / 기본 사용법
```bash
pip install "rembg[cpu]"        # CPU
pip install "rembg[cpu,cli]"    # 라이브러리 + CLI
pip install "rembg[gpu]"        # NVIDIA GPU (onnxruntime-gpu, CUDA 필요)
# Python 3.11~3.13
```
```bash
# 단일 파일
rembg i input.png output.png
# 폴더 일괄
rembg p input_dir output_dir
# Python
from rembg import remove
from PIL import Image
output = remove(Image.open("input.png"))
output.save("output.png")
# FFmpeg과 연동
ffmpeg -i input.mp4 -f rawvideo -pix_fmt rgb24 pipe:1 | rembg b 1280 720 -o out/output-%03u.png
```

## 함께 쓰는 도구
Pillow(합성), OpenCV(프레임 처리), FFmpeg(영상 파이프라인), Real-ESRGAN(누끼 전 화질 개선)
