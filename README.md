# # 🧠 YOLOv11 Object Detection Project

## 📌 프로젝트 개요
이 프로젝트는 **YOLOv11**을 기반으로 한 객체 탐지(Object Detection) 실습 프로젝트입니다.  
최신 버전인 YOLOv11의 특징을 이해하고, 이전 버전인 **YOLOv8**과 비교하여 성능 및 구조적 차이를 학습하는 것을 목표로 합니다.

---

## 🚀 YOLO란?
YOLO(You Only Look Once)는 이미지를 한 번만 보는 것(One-shot)으로 객체의 위치와 종류를 동시에 예측하는 **실시간 객체 탐지 알고리즘**입니다.  
빠른 속도와 높은 정확도로 인해 자율주행, 보안, 드론, 산업 자동화 등 다양한 분야에서 활용되고 있습니다.

---

## 📊 YOLOv8 vs YOLOv11 비교

| 구분 | YOLOv8 | YOLOv11 |
|------|---------|---------|
| **출시 연도** | 2023 | 2025 |
| **개발사 / 저장소** | Ultralytics | Ultralytics |
| **기반 프레임워크** | PyTorch | PyTorch (최적화 및 경량화 개선) |
| **백본(Backbone)** | CSPDarknet 개선 구조 | 새로 설계된 **YOLO11-Backbone**, 더 깊고 효율적인 네트워크 |
| **탐지 헤드(Head)** | Decoupled Head (클래스/박스 분리) | 효율적 구조 유지, 더 나은 Feature Fusion |
| **Anchor 방식** | Anchor-Free | Anchor-Free (향상된 Feature Alignment) |
| **입력 크기** | 가변 (640 기본) | 가변 (자동 스케일링 향상) |
| **학습 속도** | 빠름 | 더 빠름 (메모리 효율 향상) |
| **추론 성능** | 높은 정확도 | 더 높은 mAP, 더 적은 파라미터 |
| **지원 기능** | 분류(Classify), 탐지(Detect), 세분화(Segment), 포즈 추정(Pose) | 동일 + 개선된 멀티태스크 지원 |
| **사용 예시** | `yolo detect train data=... model=yolov8n.pt` | `yolo detect train data=... model=yolov11n.pt` |

---

## 📚 YOLO 주요 용어 정리

| 용어 | 의미 | 설명 |
|------|------|------|
| **Bounding Box (BBox)** | 경계 상자 | 객체가 있는 영역을 감싸는 사각형 |
| **Anchor** | 기준 박스 | 예측을 위한 초기 참조 박스 (YOLOv8 이후 Anchor-Free로 전환) |
| **mAP (mean Average Precision)** | 평균 정밀도 | 탐지 모델의 전반적인 성능 지표 |
| **IoU (Intersection over Union)** | 교집합/합집합 비율 | 예측 박스와 실제 박스의 겹치는 정도 |
| **Confidence Score** | 신뢰도 점수 | 모델이 객체라고 판단한 확률 |
| **NMS (Non-Maximum Suppression)** | 비최대 억제 | 중복 박스 제거 알고리즘 |
| **Backbone** | 특징 추출기 | 입력 이미지를 통해 중요한 특징(feature)을 추출하는 네트워크 |
| **Neck** | 특징 결합기 | 여러 단계의 특징을 합쳐 탐지 정확도를 높이는 구조 |
| **Head** | 예측기 | 객체의 위치, 클래스, 크기 등을 최종 예측 |
| **Augmentation** | 데이터 증강 | 학습 데이터를 다양하게 변형하여 일반화 성능을 높이는 기법 |

---

## 🛠️ 환경 설정

```bash
# 1. 가상환경 생성 (선택)
python -m venv yolov11-env
source yolov11-env/bin/activate  # (Windows: yolov11-env\Scripts\activate)

# 2. YOLOv11 설치 (예: Ultralytics 최신 버전)
pip install ultralytics

# 3. 버전 확인
yolo version
