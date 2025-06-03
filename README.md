# agent

Blue boxes are Applications. Rest are LLMs. 
- Prompt chaining
- Routing
- Paralleization
- Orchestrator-worker
- generator-evaluator

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
flowchart LR
    IN((IN)) --> GENERATOR
    GENERATOR -->|generates the solution| EVALUATOR
    EVALUATOR -->|Evaluates the work and provides feedback| GENERATOR
    EVALUATOR --> OUT((OUT))

```
## What models should we be using 
- Open API:  gpt-4o-mini , o1,o3-mini
- Antropic:  cloude-3-7-sonet 
- Google: gemini-2-0-flash
- Deep Seek: Deep SeekAI , Deep Seek: R1 (It costs a fraction 30 times less spend than Open API)
- Groq : llama3.3
- Ollama: local model . 
- Grok: Elon Musk . 


Duet - AI 
LeaderBoard - Vellum leaderboard . https://www.vellum.ai/llm-leaderboard 



