<div align="center">

<img src="https://img.shields.io/badge/B.Tech%20CSE-PDEU%20Gandhinagar-CAFF3C?style=flat-square&labelColor=060D08&color=1A2B1A&logo=graduation-cap&logoColor=CAFF3C" alt="degree" />
<img src="https://img.shields.io/badge/GATE%202026%20CS-AIR%2010%2C143-CAFF3C?style=flat-square&labelColor=060D08&logoColor=CAFF3C" alt="gate" />
<img src="https://img.shields.io/badge/%F0%9F%93%8D_Gandhinagar%2C%20India-1A2B1A?style=flat-square&labelColor=060D08&logoColor=CAFF3C" alt="location" />
<img src="https://img.shields.io/badge/Status-Open%20to%20SDE%20Backend%20%2F%20Fullstack%20Roles-CAFF3C?style=flat-square&labelColor=060D08&logoColor=CAFF3C" alt="status" />

<br/><br/>

<a href="https://www.linkedin.com/in/sujal-tailor/"><img src="https://img.shields.io/badge/LinkedIn-CAFF3C?style=for-the-badge&logo=linkedin&logoColor=CAFF3C&labelColor=060D08" alt="linkedin" /></a>
<a href="mailto:s.sujal.profiquence@gmail.com"><img src="https://img.shields.io/badge/Email-CAFF3C?style=for-the-badge&logo=gmail&logoColor=CAFF3C&labelColor=060D08" alt="email" /></a>
<a href="https://github.com/Sujal007T"><img src="https://img.shields.io/badge/GitHub-CAFF3C?style=for-the-badge&logo=github&logoColor=CAFF3C&labelColor=060D08" alt="github" /></a>

<br/><br/>

<img src="https://komarev.com/ghpvc/?username=Sujal007T&style=flat-square&color=CAFF3C&labelColor=060D08&label=Profile+Views" alt="views" />
<img src="https://img.shields.io/github/followers/Sujal007T?style=flat-square&color=CAFF3C&labelColor=060D08&logo=github&label=Followers" alt="followers" />
<img src="https://img.shields.io/github/stars/Sujal007T?style=flat-square&color=CAFF3C&labelColor=060D08&logo=github&label=Stars" alt="stars" />

<br/><br/>

[`whoami`](#-whoami) · [`projects`](#-ls-projectssortimpact) · [`stats`](#-git-stats---global) · [`contact`](#-ping-me)

</div>

---

## `> whoami`

Final-year CSE undergrad (PDEU, Gandhinagar &mdash; 9.66 GPA) building **backend systems and the full-stack products around them**, not CRUD wrappers. I design for correctness under concurrency first, features second: CRDT merge logic, idempotent event pipelines, and auth systems that fail closed, not open &mdash; then ship the React/TypeScript client that talks to them.

GATE 2026 CS: **AIR 10,143** (top ~5% of ~2.1 lakh candidates). 440+ problems solved across LeetCode, Codeforces, CSES, and GFG.

```bash
$ cat .profile

ROLE        =  Backend / Fullstack Engineer (Fresher)
EDU         =  B.Tech CSE, PDEU Gandhinagar (2027) | GPA 9.66
RANK        =  GATE 2026 CS - AIR 10,143 (Top ~5%)
DOMAIN      =  Real-time systems | Event-driven pipelines | Auth/RBAC
BUILDING    =  GridSync  |  Notifly  |  JournalApp
LOCATION    =  Gandhinagar, India
OPEN_TO     =  SDE Backend / Fullstack (Fresher) | Amazon | Flipkart | Swiggy | Razorpay | CRED
```

---

## `> ls /projects --sort=impact`

<details open>
<summary><b>&#9654; GridSync &mdash; Real-Time Collaborative Spreadsheet Engine</b></summary>

<br/>

A Google-Sheets-style collaborative spreadsheet engine built from first principles: CRDT-based conflict resolution, Hybrid Logical Clocks for causal ordering, and fractional indexing for concurrent row/column inserts &mdash; no OT library, no shortcuts.

| Aspect | Detail |
| :-- | :-- |
| **Stack** | Spring Boot 4.1 &middot; Java 21 &middot; React/TypeScript &middot; PostgreSQL 16 &middot; Redis 7 &middot; STOMP-over-SockJS |
| **Concurrency** | Custom CRDT merger (pure function), HLC validation at the WebSocket boundary, atomic `op_id` idempotency |
| **Correctness** | Reject-not-clamp clock validation, `(sheet_id, op_id)`-scoped idempotency, per-op `sheet_members` authorization |
| **Frontend** | React/TypeScript grid client driving live cell edits over the same WebSocket channel &mdash; full request-to-render loop, not a backend-only build |
| **Impact** | 14-phase system design executed from scratch; persistence layer with race-condition fixes verified |
| **Repo** | [`github.com/Sujal007T/GridSync`](https://github.com/Sujal007T/GridSync) |

</details>

<details>
<summary><b>&#9654; Notifly &mdash; High-Throughput Kafka Notification Pipeline</b></summary>

<br/>

An event-driven notification backbone built to survive failure, not just handle the happy path: DLQ routing, idempotent delivery, and a measured 78x throughput recovery after diagnosing a synchronous I/O bottleneck.

| Aspect | Detail |
| :-- | :-- |
| **Stack** | Java &middot; Spring Boot &middot; Apache Kafka &middot; PostgreSQL &middot; Docker |
| **Performance** | Diagnosed a sync-I/O bottleneck capping consumer throughput at ~4 events/sec |
| **Fix** | Partition-level concurrency (6-way) + async dispatch on virtual threads |
| **Result** | ~290 events/sec sustained, zero message loss, 5,400+ event backlog cleared &mdash; **78x improvement** |
| **Repo** | [`github.com/Sujal007T/Notifly`](https://github.com/Sujal007T/Notifly) |

</details>

<details>
<summary><b>&#9654; JournalApp &mdash; Hardened Auth Service</b></summary>

<br/>

A 23-endpoint Spring Boot auth service taken from "JWT that works" to production-hardened: token rotation race conditions closed with Redis Lua scripts, family-level revocation, and role-to-permission mapping.

| Aspect | Detail |
| :-- | :-- |
| **Stack** | Java 21 &middot; Spring Boot &middot; PostgreSQL &middot; Redis &middot; AWS EC2 |
| **Security** | Hashed refresh tokens, reuse-detection with family revocation, granular RBAC |
| **Reliability** | Redis-backed rate limiting via atomic Lua script (closes token-rotation race condition) |
| **Deployment** | Live on AWS EC2 (Ubuntu 24.04), actuator health endpoint, unified error handling |
| **Repo** | [`github.com/Sujal007T/journal-app-auth-service`](https://github.com/Sujal007T/journal-app-auth-service) |

</details>

---

## `> ls /tech-stack`

<div align="center">

**[ Languages ]**

<img src="https://skillicons.dev/icons?i=java,ts,js,c,python,bash&theme=dark" alt="languages" />

**[ Frontend ]**

<img src="https://skillicons.dev/icons?i=react,html,css&theme=dark" alt="frontend" />

**[ Backend &amp; Data ]**

<img src="https://skillicons.dev/icons?i=spring,nodejs,postgres,redis,kafka&theme=dark" alt="backend" />

**[ Cloud, DevOps &amp; Infra ]**

<img src="https://skillicons.dev/icons?i=aws,docker,git,linux&theme=dark" alt="cloud" />

</div>

<br/>

<div align="center">

**[ Systems &amp; Concurrency ]**

<img src="https://img.shields.io/badge/CRDTs%20%2F%20HLC-CAFF3C?style=flat-square&labelColor=060D08" alt="crdt" />
<img src="https://img.shields.io/badge/WebSockets%20%2F%20STOMP-CAFF3C?style=flat-square&labelColor=060D08" alt="ws" />
<img src="https://img.shields.io/badge/Kafka%20%2F%20DLQ%20%2F%20Idempotency-CAFF3C?style=flat-square&logo=apachekafka&logoColor=CAFF3C&labelColor=060D08" alt="kafka" />
<img src="https://img.shields.io/badge/JWT%20%2F%20RBAC%20%2F%20OAuth-CAFF3C?style=flat-square&labelColor=060D08" alt="auth" />
<img src="https://img.shields.io/badge/Virtual%20Threads-CAFF3C?style=flat-square&logo=openjdk&logoColor=CAFF3C&labelColor=060D08" alt="vthreads" />
<img src="https://img.shields.io/badge/Rate%20Limiting-CAFF3C?style=flat-square&labelColor=060D08" alt="ratelimit" />

</div>

---

## `> cat systems-expertise.json`

| Domain | Proficiency | Details |
| :-- | :-- | :-- |
| **Concurrent &amp; Distributed Systems** | `&#9608;&#9608;&#9608;&#9608;&#9607; Advanced` | CRDT merge logic, Hybrid Logical Clocks, fractional indexing, pessimistic locking |
| **Event-Driven Architecture** | `&#9608;&#9608;&#9608;&#9608;&#9607; Advanced` | Kafka producer/consumer, DLQ, idempotency, partition-level concurrency |
| **Auth &amp; Authorization** | `&#9608;&#9608;&#9608;&#9608;&#9607; Advanced` | JWT, refresh-token rotation with reuse detection, RBAC, per-op authorization |
| **API &amp; Backend Design** | `&#9608;&#9608;&#9608;&#9608;&#9608; Strong` | Spring Boot, REST, WebSocket/STOMP, rate limiting (token bucket) |
| **Frontend / Fullstack Delivery** | `&#9608;&#9608;&#9608;&#9607;&#9607; Working` | React, TypeScript &mdash; real-time UI wired to WebSocket/STOMP backend |
| **Performance Engineering** | `&#9608;&#9608;&#9608;&#9608;&#9607; Advanced` | Diagnosed I/O bottlenecks, async dispatch on virtual threads, load testing |
| **Cloud Deployment** | `&#9608;&#9608;&#9608;&#9607;&#9607; Working` | AWS EC2 deploys, Docker, actuator health checks |

---

## `> cat current-focus.yaml`

```yaml
building:
  - GridSync   # Phase 4: JWT auth + per-op WebSocket authorization
  - Notifly    # Elasticsearch search layer + HTTP-layer backpressure fix

learning:
  - Consistent hashing, sharding, rate limiter design patterns
  - JVM internals: vtable mechanics, static vs dynamic binding

grinding:
  - DSA: full Striver A2Z + Graphs playlist (440+ problems solved)
  - System design: outbox pattern, API gateway, service discovery

open_to:
  - SDE Backend / Fullstack (Fresher) - campus & off-campus
  - Amazon | Flipkart | Swiggy | Razorpay | CRED | Meesho | Zepto | PhonePe
```

---

## `> cat coding-profiles.sh`

<div align="center">

<a href="https://leetcode.com/u/Sujal_D_Tailor/"><img src="https://img.shields.io/badge/LeetCode-CAFF3C?style=for-the-badge&logo=leetcode&logoColor=CAFF3C&labelColor=060D08" alt="leetcode" /></a>
<a href="https://codeforces.com/profile/Sujal007T"><img src="https://img.shields.io/badge/Codeforces-CAFF3C?style=for-the-badge&logo=codeforces&logoColor=CAFF3C&labelColor=060D08" alt="codeforces" /></a>
<a href="https://www.geeksforgeeks.org/profile/ssujalprowudu"><img src="https://img.shields.io/badge/GeeksforGeeks-CAFF3C?style=for-the-badge&logo=geeksforgeeks&logoColor=CAFF3C&labelColor=060D08" alt="gfg" /></a>

</div>

---

## `> git stats --global`

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=Sujal007T&show_icons=true&count_private=true&include_all_commits=true&hide_rank=false&hide_border=true&title_color=CAFF3C&icon_color=8AFF57&text_color=E8F5E1&bg_color=0A0F08" alt="stats" />
<img height="165" src="https://github-readme-streak-stats.herokuapp.com/?user=Sujal007T&hide_border=true&background=0A0F08&stroke=CAFF3C&ring=8AFF57&fire=39FF14&currStreakLabel=CAFF3C&sideLabels=8AFF57&dates=8AFF57&currStreakNum=CAFF3C&sideNums=CAFF3C" alt="streak" />

<br/>

<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Sujal007T&layout=compact&hide_border=true&langs_count=8&title_color=CAFF3C&text_color=E8F5E1&bg_color=0A0F08" alt="top-langs" />

</div>

---

## `> trophy-case --display`

<div align="center">

<img src="https://github-profile-trophy.vercel.app/?username=Sujal007T&no-frame=true&no-bg=true&margin-w=4&column=7&title=Commits,Repositories,Stars,Followers&rank=-B,-A,-A,-A,-A&title_color=CAFF3C&text_color=E8F5E1&icon_color=8AFF57&background=00000000" alt="trophies" />

</div>

---

## `> activity-graph --timeline`

<div align="center">

<img src="https://github-readme-activity-graph.vercel.app/graph?username=Sujal007T&bg_color=0A0F08&color=CAFF3C&line=8AFF57&point=CAFF3C&area=true&area_color=1A2B0A&hide_border=true" alt="activity-graph" />

</div>

---

## `> ./snake-animation.sh`

<div align="center">

<img src="https://raw.githubusercontent.com/Sujal007T/Sujal007T/output/github-contribution-grid-snake-dark.svg" alt="snake" />

</div>

> Requires the [snake action](https://github.com/Platane/snk) set up on a `Sujal007T/Sujal007T` repo with an `output` branch &mdash; won't render until configured.

---

## `> ping me`

<div align="center">

<a href="mailto:s.sujal.profiquence@gmail.com"><img src="https://img.shields.io/badge/Gmail-CAFF3C?style=for-the-badge&logo=gmail&logoColor=CAFF3C&labelColor=060D08" alt="gmail" /></a>
<a href="https://www.linkedin.com/in/sujal-tailor/"><img src="https://img.shields.io/badge/LinkedIn-CAFF3C?style=for-the-badge&logo=linkedin&logoColor=CAFF3C&labelColor=060D08" alt="linkedin" /></a>
<a href="https://github.com/Sujal007T"><img src="https://img.shields.io/badge/GitHub-CAFF3C?style=for-the-badge&logo=github&logoColor=CAFF3C&labelColor=060D08" alt="github" /></a>

</div>

---

<div align="center">

<sub><i>// building systems that don't fall over under concurrency</i></sub>

<br/><br/>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&height=120&section=footer&color=0a0f08&fontColor=CAFF3C" alt="footer" />

</div>
