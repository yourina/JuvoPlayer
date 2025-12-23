```mermaid
graph TD
  A[examples/train.py로 학습] --> B[checkpoint 생성]
  B --> C[update_model: CDF 버퍼 업데이트]
  C --> D[eval_model: 데이터셋 평가]
  D --> E[결과파일(RD points)]
  F[bench: 전통 코덱 평가] --> E
  E --> G[plot: RD curve 비교]
  H[zoo: pretrained 모델 로딩] --> D
```
