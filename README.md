# agent

## Prompt Chaining 
Decomposing into fixed subtasks. 

```mermaid
flowchart LR;
    IN((IN))-->LLM1;
    LLM1-->GATE;
    GATE-->LLM2;
    LLM2-->LLM3;
    LLM3-->OUT((OUT));

classDef blue fill:#0080FE
class GATE blue
```

## Routing 
A LLM decides which LLM to route the task into

```mermaid

flowchart LR;
    IN((IN))-->LLM1;
    LLM1-->LLM2;
    LLM1-->LLM3;
    LLM1-->LLM4;
    LLM2-->OUT((OUT));
    LLM3-->OUT((OUT));
    LLM4-->OUT((OUT));
```

## Parallelization

```mermaid

flowchart LR;




```
