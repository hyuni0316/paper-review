# 📄 Paper Review: ReelFramer: Human-AI Co-Creation for News-to-Video Translation

## 📝 Basic Info
- **Title**: ReelFramer: Human-AI Co-Creation for News-to-Video Translation- **Authors**: 
- **Conference/Journal**: Proceedings of the CHI Conference on Human Factors in Computing Systems (CHI ’24)
- **Year**: 2024
- **Link**: [link/DOI](https://dl.acm.org/doi/pdf/10.1145/3613904.3642868#page=14.66)

---

## 🎯 Summary

이 논문은 뉴스 기사를 짧은 소셜미디어 영상(뉴스 릴스)로 변환하는 과정에서 저널리스트들이 겪는 어려움을 다룬다. 전통적인 글 기반 뉴스는 긴 설명과 맥락 제공에 초점을 두지만, 릴은 짧고 시각적이며 오락성을 요구하기 때문에 형식적·창의적 간극이 크다.

이를 해결하기 위해 저자들은 ReelFramer라는 인간-AI 공동 창작 시스템을 제안했다. ReelFramer는 뉴스 기사를 세 가지 내러티브 프레임(전문가-초심자 대화, 현장 재연, 코믹한 비유)을 통해 스크립트와 스토리보드로 전환한다. 이 과정에서 AI는 GPT-4, 이미지 생성 모델 등을 활용해 premise → 스크립트 → 시각적 스토리보드의 단계적 워크플로우를 지원한다.

실험과 사용자 연구 결과, ReelFramer는 뉴스 릴 제작의 효율성과 탐색성을 높였으며, 특히 premise 단계가 정보 구조화와 서사 적합성 향상에 기여했다. 다만 AI가 생성하는 유머와 시각적 일관성의 한계는 여전히 존재했다.

즉, ReelFramer는 저널리스트가 뉴스 콘텐츠를 새로운 형식(릴스)으로 번역할 수 있도록 돕는 창의적 보조 도구로서의 가능성을 보여준다.

---

## 🔑 Key Points
- 핵심 기여 1: 세 가지 대표적인 **내러티브 프레이밍(expository dialog, reenactment, comedic analogy)**을 정의하고, 뉴스 기사를 릴 형식에 맞게 재구성하는 구조 제공.
- 핵심 기여 2: AI(LLM·텍스트-투-이미지 모델)를 활용한 스크립트 및 스토리보드 생성 워크플로우 제안.
- 핵심 기여 3: **저널리스트와 공동 디자인(co-design)**을 통해 실제 제작 과정에 적합한 시스템 설계.
- 핵심 기여 4: 사용자 연구를 통해 ReelFramer가 뉴스 릴스 제작 과정의 탐색성과 효율성을 높여줌을 입증.

---


## 🔧 System
- **이름**: ReelFramer  
- **목적**: 뉴스 기사를 **짧은 소셜미디어 릴(영상)**로 변환하는 **인간-AI 공동 창작 도구**  
- **구성 단계**:  
  1. **Scriptwriting**  
     - 기사 입력 → LLM이 인물·장소·행동 추출  
     - 사용자가 **내러티브 프레임** 선택 (Expository dialog / Reenactment / Comedic analogy)  
     - AI가 premise(캐릭터, 플롯, 설정, 핵심 정보) 제안 → 수정·확정 후 스크립트 생성  
  2. **Storyboarding**  
     - 캐릭터 보드 생성 (의상·소품·배경)  
     - 대사별 **컷 설명(표정, 동작, 감정)** 자동 생성 → 스토리보드 시각화  
- **기술 스택**: GPT-4 (텍스트), BERT (정보 매칭), DALL·E 2 (이미지), Flask/Python  

---

## 🧪 Evaluation
- **LLM 스크립트 평가 실험**  
  - 조건: *With premise* vs *Without premise*  
  - 데이터: 6개 기사 × 3 프레임 × 2회 = 24개 스크립트  
  - 평가자: 언론학 배경 전문가 4명  
  - 기준: 내러티브 적합성, 정보 정확성, 커버리지, 일관성, 재미, 틱톡 스타일  

- **사용자 연구**  
  - 참가자: 언론학 대학원생 5명  
  - 과제: Associated Press 기사 기반 릴 제작 (총 10개)  
  - 절차: 기사 읽기 → ReelFramer → 스크립트 → 스토리보드 → 촬영 → 인터뷰  
  - 평균 소요: 스크립트 제작 12.8분  

---

## 📊 Result
- **LLM 평가 결과**  
  - Premise 제공 시 ↑  
    - 내러티브 적합성 (p=0.028)  
    - 정보 커버리지 (p=0.034)  
    - 일관성 (p=0.011)  
  - 재미·틱톡 스타일 점수 → 큰 차이 없음 (AI 유머 한계)  
  - 정보 정확성 → premise 여부와 관계없이 유사  

- **사용자 연구 결과**  
  - ReelFramer → **탐색성**(다양한 프레임·스크립트 시도) & **효율성**(시간 절약) 향상  
  - Premise 단계 → 정보 구조화·제어력 강화  
  - 자동 생성 스크립트 → “90% 완성”, punchline 등은 수정 필요  
  - 최종 품질 확보를 위해 **사용자 개입·편집 필수**
    
---

## 💡 Thoughts
- 아이디어 확장 가능성
  - 다른 내러티브 프레임 추가 (예: 뮤지컬, 시사 패러디, 밈 기반 등).
  - 멀티모달 제어(예: 음성 톤, 배경 음악, 카메라 앵글까지 제안) 확장.
  - 교육용 도구로 활용 가능 (저널리즘 수업에서 릴 제작 훈련).
  - 자동 fact-checking 모듈과 결합해 정보 정확성 강화 가능.
