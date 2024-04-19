# Magical_SOLARgodong
AIKU에서 진행한 2024년 겨울 방학 프로젝트입니다.

![image](https://github.com/AIKU-Official/Magical_SOLARgodong/assets/80198264/6fc49bf3-0a46-45fd-b3c2-ce2b11af0850)
---
## 소개
가끔 친구들과 인터넷 메신저로 대화를 하다보면 상황에 맞는 재밌는 짤을 가져오는 친구들이 꼭 있습니다. 하지만 불행히도, 그런 능력을 모두가 가지고 있는 것은 아니죠... 재밌는 짤을 친구들에게 보내고 싶은 분들을 위해 사용자가 입력한 Query에 맞는 사진을 추천해주는 프로젝트입니다.
이를 위해 사용자가 입력한 query와 인터넷 짤 사이의 유사도를 딥러닝 모델을 통해 구하고 가장 유사도가 높은 사진을 output해주는 모델을 구축했습니다.

## 방법론

### 데이터셋
Tag가 붙어있는 인터넷 짤들을 크롤링하여 수집. (2runzzal.com, Jjalbang.today, jjalbang.net 사이트에서 데이터 수집)

### 모델
![image](https://github.com/AIKU-Official/Magical_SOLARgodong/assets/80198264/cb47d752-54ef-4227-adb0-e6966fdab7ea)

Sbert를 사용하여 입력 query와 이미지 태그들 사이의 유사도를 도출하고 상위 K개를 추출

LLM(OPEN-SOLAR-KO-10.7B)를 사용하여 이미지 태그들이 감정이나 상황 등의 정보를 담을 수 있도록 가다듬는 역할과 Sbert를 사용하여 추출한 특정 query에 맞는 상위 K개의 이미지 중 하나의 이미지를 최종 output으로 결정하는 역할을 담당

BLIP-2를 사용하여 이미지 캡셔닝을 진행. 기존 크롤링으로 수집한 태그들로는 부족한 이미지에 대한 설명을 보충하는 역할을 담당.

## 환경 설정
Google Colab Pro A100

## 사용 방법
현재 ipynb 파일만 올라와 있으므로 전체를 돌리셔야 합니다.. 추후 모듈화 진행 후 코드를 업데이트할 예정입니다.

## 예시 결과
![image](https://github.com/AIKU-Official/Magical_SOLARgodong/assets/80198264/9a78913d-a947-4b8d-b981-44a2ecdb1d19)

![image](https://github.com/AIKU-Official/Magical_SOLARgodong/assets/80198264/661a9f15-b312-450f-b3d6-8029eeb4b2e0)

![image](https://github.com/AIKU-Official/Magical_SOLARgodong/assets/80198264/17212892-7f20-4a2e-8be1-54ca8a60e073)

## 팀원
- [김민영](https://github.com/EuroMinyoung186/)
- 박서현
- 박정규
