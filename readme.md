<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=rect&color=0:080B0A,50:111914,100:202B1C&height=230&section=header&text=SUBHRA%20BIKIRAN%20NAYAK&fontSize=39&fontColor=E8F5E9&fontAlignY=42&desc=BACKEND%20ENGINEERING%20%C2%B7%20DISTRIBUTED%20SYSTEMS%20%C2%B7%20SYSTEMS%20DESIGN&descSize=12&descColor=A3E635&descAlignY=65" />

<br/>

<code>ENGINEERING THE SYSTEMS BEHIND THE SOFTWARE.</code>

<br/><br/>

<a href="https://github.com/SubhraBNayak">
<img src="https://img.shields.io/badge/GITHUB-080B0A?style=for-the-badge&logo=github&logoColor=A3E635"/>
</a>
<a href="www.linkedin.com/in/subhra-bikiran-nayak-438807288">
<img src="https://img.shields.io/badge/LINKEDIN-080B0A?style=for-the-badge&logo=linkedin&logoColor=A3E635"/>
</a>
<a href="mailto:subhrabikiran@gmail.com">
<img src="https://img.shields.io/badge/EMAIL-080B0A?style=for-the-badge&logo=gmail&logoColor=A3E635"/>
</a>

<br/><br/>

<img src="https://komarev.com/ghpvc/?username=SubhraBNayak&style=flat-square&color=A3E635&label=PROFILE+SIGNALS" />

</div>

---

<table>
<tr>
<td width="60%" valign="top">

## 00 / IDENTITY

# Software is more than its interface.

I'm a Computer Science engineering student focused on backend engineering and the systems that power modern applications.

I enjoy exploring what happens beneath an API: how databases organize information, how services communicate, how concurrent workloads are handled, and how distributed systems recover when things inevitably break.

Currently building with **Node.js and Python**, while exploring **Go, distributed systems and infrastructure engineering**.

</td>
<td width="40%" valign="top">

### SYSTEM PROFILE

```yaml
name: Subhra Bikiran Nayak

domain:
  - Backend Engineering
  - Distributed Systems

building_with:
  - Node.js
  - Python
  - PostgreSQL

exploring:
  - Go
  - Kafka
  - Concurrency
  - System Design

mindset:
  - Fundamentals first
  - Correctness over shortcuts
  - Understand the internals
```

</td>
</tr>
</table>

---

<div align="center">

## 01 / THE ENGINEERING STACK

<sub>A SNAPSHOT OF THE TOOLS I BUILD WITH AND THE SYSTEMS I'M EXPLORING.</sub>

</div>

<table>
<tr>
<td width="50%" valign="top">

### `01. LANGUAGES`

<img src="https://skillicons.dev/icons?i=js,ts,py,go,cpp,c,java&theme=dark" />

### `02. BACKEND`

<img src="https://skillicons.dev/icons?i=nodejs,express,django,fastapi&theme=dark" />

### `03. DATA`

<img src="https://skillicons.dev/icons?i=postgres,mongodb,redis,sqlite&theme=dark" />

</td>
<td width="50%" valign="top">

### `04. INFRASTRUCTURE`

<img src="https://skillicons.dev/icons?i=docker,kubernetes,linux,nginx&theme=dark" />

### `05. MESSAGING & SYSTEMS`

<img src="https://skillicons.dev/icons?i=kafka,rabbitmq&theme=dark" />

### `06. FRONTEND`

<img src="https://skillicons.dev/icons?i=react,tailwind,vite&theme=dark" />

</td>
</tr>
</table>

---

<div align="center">

## 02 / SYSTEMS THAT INTEREST ME

<sub>NOT JUST WHAT A TECHNOLOGY DOES. WHY IT EXISTS.</sub>

</div>

<table>
<tr>
<td width="50%" valign="top">

### DISTRIBUTED COMPUTING

- Concurrency and synchronization
- Fault tolerance and recovery
- Consistency and replication
- Message delivery guarantees
- Service discovery and communication

</td>
<td width="50%" valign="top">

### DATA ENGINEERING

- Database internals and indexing
- Query optimization
- Caching strategies
- Change Data Capture
- Event streaming and OLAP

</td>
</tr>
<tr>
<td width="50%" valign="top">

### BACKEND ARCHITECTURE

- API design and scalability
- Asynchronous job processing
- WebSockets and real-time systems
- Authentication and security
- Microservices and gRPC

</td>
<td width="50%" valign="top">

### INFRASTRUCTURE

- Containers and orchestration
- CI/CD and deployment
- Observability and monitoring
- Load balancing
- Linux and networking

</td>
</tr>
</table>

---

<div align="center">

## 03 / AN ARCHITECTURE I LOVE EXPLORING

<div align="center">

<sub>FROM A SINGLE WRITE TO A DISTRIBUTED ECOSYSTEM OF INDEPENDENT SYSTEMS</sub>

</div>

```mermaid
flowchart TB

    subgraph CLIENT["01 / CLIENT & API LAYER"]
        U["Web / Mobile Clients"]
        GW["API Gateway"]
        AUTH["Authentication & Authorization"]
        U --> GW --> AUTH
    end

    subgraph CORE["02 / OPERATIONAL CORE"]
        API["Application Services"]
        CMD["Command Handler"]
        DB[("Operational Database<br/>PostgreSQL / Cassandra")]
        OUTBOX[("Transactional Outbox")]
        API --> CMD
        CMD --> DB
        CMD --> OUTBOX
    end

    subgraph INGEST["03 / CHANGE CAPTURE & INGESTION"]
        CDC["CDC Connector<br/>Debezium / Native CDC"]
        SERIAL["Event Serializer"]
        REG["Schema Registry"]
        CDC --> SERIAL
        REG -. Schema Validation .-> SERIAL
    end

    subgraph STREAM["04 / DISTRIBUTED EVENT BACKBONE"]
        K[("APACHE KAFKA")]
        T1["orders.events"]
        T2["users.events"]
        T3["payments.events"]
        T4["activity.events"]
        K --> T1
        K --> T2
        K --> T3
        K --> T4
    end

    subgraph PROCESS["05 / STREAM PROCESSING"]
        SP["Stream Processing<br/>Flink / Kafka Streams"]
        ENRICH["Enrichment & Transformation"]
        STATE[("State Store")]
        DLQ[("Dead Letter Queue")]
        RETRY["Retry Topics"]
        SP --> ENRICH
        SP --> STATE
        SP --> DLQ
        RETRY --> SP
    end

    subgraph READ["06 / QUERY & SERVING LAYER"]
        SEARCH[("Elasticsearch<br/>Full-text Search")]
        CACHE[("Redis<br/>Cache / Read Models")]
        OLTPREAD[("Read Database<br/>CQRS Projection")]
        APIREAD["Query Services"]
        SEARCH --> APIREAD
        CACHE --> APIREAD
        OLTPREAD --> APIREAD
    end

    subgraph ANALYTICS["07 / ANALYTICS & INTELLIGENCE"]
        WAREHOUSE[("Data Warehouse / OLAP")]
        BI["BI Dashboards"]
        ML["Recommendation / ML"]
        WAREHOUSE --> BI
        WAREHOUSE --> ML
    end

    subgraph ASYNC["08 / ASYNCHRONOUS WORKFLOWS"]
        WORK["Worker Fleet"]
        QUEUE[("Job Queue<br/>BullMQ / RabbitMQ")]
        EMAIL["Notifications"]
        WEBHOOK["Webhooks"]
        MEDIA["Media Processing"]
        QUEUE --> WORK
        WORK --> EMAIL
        WORK --> WEBHOOK
        WORK --> MEDIA
    end

    subgraph OBS["09 / OBSERVABILITY & RELIABILITY"]
        METRICS["Metrics & Tracing"]
        LOGS["Centralized Logs"]
        ALERTS["Alerting"]
        RECON["Reconciliation & Replay"]
        METRICS --> ALERTS
        LOGS --> ALERTS
    end

    AUTH --> API
    OUTBOX --> CDC
    CDC --> SERIAL
    SERIAL --> K

    T1 --> SP
    T2 --> SP
    T3 --> SP
    T4 --> SP

    ENRICH --> SEARCH
    ENRICH --> CACHE
    ENRICH --> OLTPREAD
    ENRICH --> WAREHOUSE
    ENRICH --> QUEUE
    ENRICH --> ML

    K -. Failed Processing .-> RETRY
    DLQ -. Manual Recovery .-> RECON
    K -. Event Replay .-> RECON
    API -. Telemetry .-> METRICS
    SP -. Telemetry .-> METRICS
    WORK -. Telemetry .-> METRICS

    classDef core fill:#18291D,stroke:#A3E635,color:#E8F5E9,stroke-width:2px
    classDef infra fill:#151D27,stroke:#67E8F9,color:#E0F2FE
    classDef data fill:#211C30,stroke:#A78BFA,color:#F3E8FF
    classDef reliability fill:#302018,stroke:#FB923C,color:#FFEDD5

    class DB,OUTBOX,STATE,SEARCH,CACHE,OLTPREAD,WAREHOUSE,K,DLQ,QUEUE core
    class CDC,SERIAL,REG,SP,ENRICH,WORK,GW,AUTH,API,CMD,APIREAD infra
    class T1,T2,T3,T4,BI,ML,EMAIL,WEBHOOK,MEDIA data
    class RETRY,METRICS,LOGS,ALERTS,RECON reliability
```

<div align="center">

<sub>ONE WRITE PATH · MULTIPLE READ MODELS · INDEPENDENT CONSUMERS · EVENTUAL CONSISTENCY</sub>

</div>

## 04 / ENGINEERING PRINCIPLES

</div>

```text
┌─────────────────────────────────────────────────────┐
│                                                     │
│  01   Understand the workload before choosing tools.│
│  02   Correctness before optimization.              │
│  03   Design for failure, not just success.         │
│  04   Measure performance instead of guessing.      │
│  05   Prefer simplicity until complexity is needed. │
│  06   Understand the abstraction before using it.   │
│                                                     │
└─────────────────────────────────────────────────────┘
```

---

<div align="center">

## 05 / GITHUB ACTIVITY

<sub>CONTRIBUTIONS, EXPERIMENTS AND THINGS BUILT ALONG THE WAY.</sub>

<br/><br/>

<img src="https://github-readme-stats.vercel.app/api?username=SubhraBNayak&show_icons=true&hide_border=true&bg_color=080B0A&title_color=A3E635&text_color=D1D5DB&icon_color=A3E635&rank_icon=github" height="170" />

<img src="https://github-readme-streak-stats.herokuapp.com/?user=SubhraBNayak&hide_border=true&background=080B0A&ring=A3E635&fire=A3E635&currStreakLabel=A3E635&sideLabels=D1D5DB&dates=737373" height="170" />

<br/><br/>

<img src="https://github-readme-activity-graph.vercel.app/graph?username=SubhraBNayak&bg_color=080B0A&color=D1D5DB&line=A3E635&point=FFFFFF&area=true&hide_border=true" width="100%" />

</div>

---

<div align="center">

## 06 / OPEN CHANNEL

**Interested in backend engineering, distributed systems and building things that scale.**

<br/>

<a href="https://github.com/SubhraBNayak">
<img src="https://img.shields.io/badge/EXPLORE_MY_REPOSITORIES-A3E635?style=for-the-badge&logo=github&logoColor=080B0A"/>
</a>

<br/><br/>

<a href="https://www.linkedin.com/">
<img src="https://img.shields.io/badge/LINKEDIN-111914?style=flat-square&logo=linkedin&logoColor=A3E635"/>
</a>
&nbsp;
<a href="mailto:your-email@gmail.com">
<img src="https://img.shields.io/badge/GET_IN_TOUCH-111914?style=flat-square&logo=gmail&logoColor=A3E635"/>
</a>

<br/><br/>

<sub>SUBHRA BIKIRAN NAYAK · BUILT ON CURIOSITY, REFINED THROUGH ENGINEERING.</sub>

<br/><br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:202B1C,100:080B0A&height=100&section=footer" width="100%" />

</div>
