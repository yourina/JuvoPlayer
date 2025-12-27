flowchart TB
  IMG[Image] --> STEM[Stem] --> BB[Backbone] --> FPN[FPN]

  subgraph Edge
    FPN --> P2[P2]
    FPN --> P3[P3]
    FPN --> P4[P4]
    FPN --> P5[P5]
    P2 --> ENC[FCM Encoder]
    P3 --> ENC
    P4 --> ENC
    P5 --> ENC
    ENC --> BS[(Bitstream)]
  end

  BS --> NET[Network] --> DBS[(Bitstream)]

  subgraph Cloud
    DBS --> DEC[FCM Decoder]
    DEC --> RPN[RPN]
    RPN --> ROI[ROIAlign]
    ROI --> HEADS[ROIHeads/Mask/KP]
    HEADS --> OUT[Outputs]
  end
