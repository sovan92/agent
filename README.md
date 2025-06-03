# agent

Blue boxes are Applications. Rest are LLMs. 

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
Concurrent task break down by a GATE and Aggregating by a Aggregator
```mermaid

flowchart LR;
    IN((IN))-->COORDINATOR;
    COORDINATOR-->LLM2;
    COORDINATOR-->LLM3;
    COORDINATOR-->LLM4;
    LLM2-->AGGREGATOR;
    LLM3-->AGGREGATOR;
    LLM4-->AGGREGATOR;
    AGGREGATOR-->OUT((OUT));
   
classDef blue fill:#0080FE
class COORDINATOR,AGGREGATOR blue


```

## Orchestrator-Worker
Concurrent task break down by a Orchestrator and Aggregating by a Worker, both of which are LLM
```mermaid

flowchart LR;
    IN((IN))-->ORCHESTRATOR;
    ORCHESTRATOR-->LLM2;
    ORCHESTRATOR-->LLM3;
    ORCHESTRATOR-->LLM4;
    LLM2-->WORKER;
    LLM3-->WORKER;
    LLM4-->WORKER;
    WORKER-->OUT((OUT));
   
```
## LLM Generator Evaluator Loop (Very Popular)
```mermaid

flowchart LR;
    IN((IN))-->GENERATOR;
    GENERATOR-->EVALUATOR:generates the solution;
    EVALUATOR-->GENERATOR:Evaluates the work and provides feedback;
    EVALUATOR-->OUT((OUT))

```





