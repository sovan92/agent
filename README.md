# agent

```mermaid
graph TD;
    flowchart LR
    IN-->LLM1;
    LLM1-->GATE;
    GATE-->LLM2;
    LLM2-->LLM3;
    LLM3-->OUT
```
