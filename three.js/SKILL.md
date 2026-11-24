# three.js

- **저장소:** https://github.com/mrdoob/three.js
- **별:** 약 119,283개 (2026-11-25 확인)
- **라이선스:** MIT

## 용도
브라우저에서 3D 장면을 그리는 JavaScript 3D 라이브러리. WebGL/WebGPU 렌더러 기반.

## 핵심 기능
- Scene·Camera·Mesh·Material·Light·Animation 등 3D 기본 요소
- WebGL/WebGPU 렌더링, SVG/CSS3D 렌더러는 애드온으로 제공
- GLTF/FBX 등 3D 모델 로더, 애니메이션·파티클·포스트프로세싱 애드온 다수
- 예제·문서·매뉴얼이 풍부 (threejs.org)

## MG의 쇼츠/영상 제작에서 활용
- 3D 장면의 카메라와 움직임을 실시간으로 잡는 프리비즈(Pre-visualization) 엔진
- 블록 3D 세계, 타이틀 3D 모션, 제품 3D 회전 쇼츠의 화면을 브라우저에서 미리 확인
- Playwright와 함께 three.js 장면을 렌더링해 정지컷·프레임을 자동 캡처
- Remotion/Blender로 옮기기 전 구도·카메라 워크를 빠르게 검증

## 설치 / 기본 사용법
```bash
npm install three
# 또는 CDN import
```
```js
import * as THREE from 'three';
const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(70, width/height, 0.01, 10);
const renderer = new THREE.WebGLRenderer({ antialias: true });
renderer.setAnimationLoop(() => renderer.render(scene, camera));
```
- 클론 시 전체 히스토리는 약 2GB라 `git clone --depth=1` 권장

## 함께 쓰는 도구
Blender(실사 렌더) ← three.js(프리비즈), Playwright(캡처), Remotion(모션 그래픽)
