# OpenCV

- **저장소:** https://github.com/opencv/opencv
- **별:** 약 91,704개 (2026-11-25 확인)
- **라이선스:** Apache-2.0

## 용도
오픈소스 컴퓨터 비전 라이브러리. 이미지·영상 처리의 표준 도구.

## 핵심 기능
- 이미지 입출력, 색 공간 변환, 리사이즈, 자르기, 필터, 모폴로지
- 얼굴·물체 검출, 특징점 매칭, 카메라 보정, 광학 흐름
- 영상 캡처·쓰기, 배경 제거, 윤곽 검출
- C++·Python·Java 등 다언어 지원, `opencv-contrib` 확장 모듈

## MG의 쇼츠/영상 제작에서 활용
- 프레임을 비교하고 잘라내고 색을 보정하는 영상 처리
- 장면 전환 검출, 얼굴 위치 추적 → 세로 크롭 시 얼굴 따라가기
- 밝기·채도 보정, 블러·샤프닝, 워터마크 삽입
- Pillow/rembg와 함께 프레임 단위 전처리

## 설치 / 기본 사용법
```bash
pip install opencv-python
# GUI 없는 서버용: pip install opencv-python-headless
```
```python
import cv2
cap = cv2.VideoCapture("in.mp4")
ok, frame = cap.read()
gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
small = cv2.resize(frame, (540, 960))
cv2.imwrite("frame.jpg", small)
# 영상 쓰기
out = cv2.VideoWriter("out.mp4", cv2.VideoWriter_fourcc(*"mp4v"), 30, (1080, 1920))
```

## 함께 쓰는 도구
FFmpeg(최종 조립), Pillow(이미지 합성), rembg(배경제거), librosa(오디오 분석과 동기화)
