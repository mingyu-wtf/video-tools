# Real-ESRGAN

- **저장소:** https://github.com/xinntao/Real-ESRGAN
- **별:** 약 37,635개 (2026-11-25 확인)
- **라이선스:** BSD-3-Clause

## 용도
실제 사진·영상의 초해상도(업스케일)·복원을 위한 실용 알고리즘. ESRGAN을 실제 환경에 맞게 확장.

## 핵심 기능
- 일반 이미지 x4 업스케일 (`RealESRGAN_x4plus`), 애니메이션 전용 모델 (`RealESRGAN_x4plus_anime_6B`, AnimeVideo-v3)
- 얼굴 강화(GFPGAN 연동, `--face_enhance`), 노이즈 제거(`-dn`), 임의 배율(`--outscale`)
- Python 스크립트, NCNN 포터블 실행파일(Windows/Linux/macOS, CUDA/PyTorch 불필요), Colab 데모

## MG의 쇼츠/영상 제작에서 활용
- 오래되거나 흐린 자료 사진을 선명하게 키워 썸네일·자료 화면에 사용
- 저화질 AI 생성 이미지·옛날 영상 프레임을 1080p급으로 업스케일
- 애니메이션 스타일 이미지·영상은 애니메 모델로 처리

## 설치 / 기본 사용법
```bash
git clone https://github.com/xinntao/Real-ESRGAN.git
cd Real-ESRGAN
pip install basicsr facexlib gfpgan
pip install -r requirements.txt
python setup.py develop
```
```bash
# 일반 이미지
wget https://github.com/xinntao/Real-ESRGAN/releases/download/v0.1.0/RealESRGAN_x4plus.pth -P weights
python inference_realesrgan.py -n RealESRGAN_x4plus -i inputs --face_enhance
# 애니메이션 이미지
python inference_realesrgan.py -n RealESRGAN_x4plus_anime_6B -i inputs
# 간편 실행파일: ./realesrgan-ncnn-vulkan.exe -i input.jpg -o output.png -n realesrgan-x4plus
```
- Python 3.7+, PyTorch 1.7+ 필요

## 함께 쓰는 도구
Pillow(업스케일 전후 합성), FFmpeg(영상 프레임 추출·재조립), OpenCV(프레임 처리)
