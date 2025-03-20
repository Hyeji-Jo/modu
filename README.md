# 다국어 회의록 요약

## 개요 👩🏻‍🏫 
### 1️⃣  &nbsp; 배경 및 목적
- 글로벌 기업 및 다국적 협력 프로젝트의 증가로 인해 다양한 언어로 회의가 진행됨
- 수동 기록, 녹취 후 수기 정리 등 기존의 회의록 작성 방식은 시간과 비용이 많이 소요됨
- 본 프로젝트는 다국어 회의 내용을 인식하고 요약하여, **회의록 작성의 효율성을 높이고 언어 장벽을 줄이는 것이 목표**

### 2️⃣  &nbsp; 개요  
1. 회의 녹음 파일을 입력 받음
2. ASR: Whisper or WhisperX / Speeker Diarization: pyannote or Nemo
   - 중첩된 음섬 40%
   - 중첩되지 않은 음성 60% 
3. (선택) + WavLM 대강 이런 모델 고려
4. 회의록 전체 출력
5. 전문 기계 번역(처음엔 영어, Max(언어))
6. 요약 모델 사용 : BART 계열
7. GPT 사용
8. 웹 개발

   

### 3️⃣  &nbsp; 진행 기간 : 25.03.10 ~ 
  
### 4️⃣  &nbsp; Member
  | **분야**   | **이름**  | **역할** |
  |-----------|---------|----------------------------|
  | **음성 AI** | [조혜지](https://github.com/Hyeji-Jo)  | 음성인식 모델 파라미터 튜닝 |
  | **음성 AI** | [김수효](https://github.com/KimSooHyo)  | 음성인식 모델 파라미터 튜닝 |
  | **음성 AI** | [한종현](https://github.com/smilish67)  | 음성합성 모델 파라미터 튜닝 |
  | **자연어 AI** | [김주보](https://github.com/winjujae)  | 자연어 모델 파라미터 튜닝 |



## 진행 상세 일정
- 25.03.10 : 프로젝트 주제 고민
- 25.03.11 : 3/12까지 주제 선정하기
- 25.03.12 : 화자 분리 모델 조사 (cam++, Pyannote, NeMo), 요약 언어 모델 조사 (GPT, BART, T5)
- 25.03.13 : 한국어, 영어, 중국어 각각 언어의 대화, 텍스트 데이터 조사
- 25.03.14 : 데이터셋 구축, whisper+pyannote, whisper+nemo 모델 베이스라인, 언어 모델(BART, T5) 선정 
- 25.03.15~16 : 데이터셋 구축, 언어 모델(BART, T5) 파인튜닝

- 25.03.17 : whisper+pyannote, 언어 모델 평가지표 선정 및 확인
- 25.03.18 : Speaker Diarization 성능 비교 - Pyannote vs NeMo ( 사전학습된 기본 모델 )
- 25.03.19 : 화자 분리모델 선정해서 성능 올리기 + whisperX 어떻게 할지 생각
   - Pyannote : 평균 DER 32.01
   - NeMo - telephonic : 평균 DER 43
   - NeMo - 평균 DER 41
 
   - 추가 해야할 일
     - 한국어, 중국어, 영어 데이터 셋 Pyannote 파인튜닝
     - 최적화 진행 (최대한 자료조사)
     - whisper + faster_whisper 붙여서 wer, eer 비교  
- 25.03.20 : Pyannote 파인튜닝 / Multilingual 데이터 생성
