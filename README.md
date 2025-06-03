# agent

```mermaid
flowchart LR
graph TD;
    IN-->LLM1;
    LLM1-->GATE;
    GATE-->LLM2;
    LLM2-->LLM3;
    LLM3-->OUT;
```
