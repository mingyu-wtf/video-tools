# Pillow

- **저장소:** https://github.com/python-pillow/Pillow
- **별:** 약 14,013개 (2026-11-25 확인)
- **라이선스:** HPND(오픈소스, PIL 포크)

## 용도
Python용 이미지 처리 라이브러리(PIL의 친화적 포크). 이미지 열기·변환·합성·그리기.

## 핵심 기능
- JPEG/PNG/WebP/GIF 등 다양한 포맷 지원, 리사이즈·자르기·회전·필터
- `ImageDraw`로 텍스트·도형 그리기, 폰트 적용
- 색상 모드 변환, 알파 채널 합성, 썸네일 생성

## MG의 쇼츠/영상 제작에서 활용
- 자막 카드, 타이틀 카드, 썸네일(1080×1920 등) 그리기
- AI 생성 이미지·프레임을 합성하고 텍스트·로고 오버레이
- 카드뉴스 이미지(1080×1350) 제작, 이미지 배치·여백 조정
- rembg로 배경을 지운 이미지와 합성

## 설치 / 기본 사용법
```bash
pip install Pillow
```
```python
from PIL import Image, ImageDraw, ImageFont
img = Image.open("frame.png").convert("RGB")
img = img.resize((1080, 1920))
draw = ImageDraw.Draw(img)
font = ImageFont.truetype("Hahmlet-Bold.ttf", 72)
draw.text((80, 1600), "쇼츠 제목", font=font, fill="white")
img.save("card.jpg", quality=92)
```

## 함께 쓰는 도구
Hahmlet(한글 폰트), rembg(배경제거), FFmpeg(프레임 추출 → Pillow 합성 → 다시 조립), OpenCV
