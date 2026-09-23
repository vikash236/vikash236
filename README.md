<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=1a1b26,7aa2f7,bb9af7&height=120&section=header"/>

<div align="center">

# Hi there, I'm <a href="https://ksvikash236.vercel.app/">Vikash Reddy</a> <img height="35" src="https://raw.githubusercontent.com/innng/innng/master/assets/kyubey.gif"/>

<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=28&pause=1000&color=7aa2f7&center=true&vCenter=true&width=800&lines=B.Tech+CSE+Student+%26+Compiler+Enthusiast;Building+Agam%3A+A+Systems+Language+in+Rust;Exploring+Compilers%2C+AI+%26+Low-Level+Systems;Always+Learning+from+First+Principles" alt="Typing SVG" />

<br/>

[![Portfolio](https://img.shields.io/badge/🌐_Portfolio-ksvikash236.vercel.app-7aa2f7?style=for-the-badge&logo=vercel&logoColor=white)](https://ksvikash236.vercel.app/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ksvikash236/)
[![Gmail](https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:ksvikash236@gmail.com)

<img src="https://komarev.com/ghpvc/?username=vikash236&label=Profile%20Views&color=7aa2f7&style=for-the-badge" alt="Profile views" />

</div>

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/People/Technologist.png" width="35" /> About Me

```typescript
const vikash = {
    location: "Nagari, Andhra Pradesh, India 🇮🇳",
    education: "B.Tech CSE — JNTUA College of Engineering, Kalikiri",
    languages: ["English", "Telugu", "Tamil"],
    title: "B.Tech CSE Student & Aspiring Systems/Software Engineer",
    portfolio: "https://ksvikash236.vercel.app/",
    focus: ["Compiler Engineering", "Systems Programming", "AI & Machine Learning"],
    currentProjects: {
        Agam: "Compiled systems language in Rust with custom SSA MIR, Cranelift JIT & LLVM AOT",
        MediManage: "Desktop pharmacy management app with local AI assistance",
        OmniAIBench: "Hardware monitoring & CPU benchmark utility (WIP)"
    },
    exploring: [
        "Modern Web Frameworks (FastAPI, Django)",
        "Docker & Containerization",
        "Databases (PostgreSQL, MongoDB)",
        "Computer Vision (OpenCV)"
    ],
    philosophy: "Build solid fundamentals and learn how systems work from first principles.",
    currentGoal: "Master compiler middle-ends, low-level systems, and build robust software"
};
```

> I'm a B.Tech Computer Science student at JNTUA College of Engineering, Kalikiri, passionate about compiler engineering, systems programming, and machine learning. My deepest technical work is **Agam**—an experimental compiled systems language implemented in Rust featuring custom SSA intermediate representation, Cranelift JIT, and LLVM AOT code generation. I enjoy building from first principles, from compilers and system monitoring tools to desktop applications with local AI assistance.

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Bullseye.png" width="35" /> Current Focus Areas

<table align="center">
<tr>
<td width="33%" align="center">

### 🎯 Learning
- Compiler Optimizations & SSA
- Data Structures & Algorithms
- Systems Programming (Rust/C)
- Backend Development (Node.js/MySQL)
- Linux & Networking Basics

</td>
<td width="33%" align="center">

### 🚀 Building
- Agam (Systems Language & Compiler)
- MediManage (Pharmacy App)
- OmniAIBench (Hardware Monitor)
- Open Source Contributions

</td>
<td width="34%" align="center">

### 📚 Reading & Exploring
- Modern Compiler Design & IRs
- Computer Systems & OS Internals
- Modern Web Frameworks (FastAPI)
- Container Basics (Docker)

</td>
</tr>
</table>

---

## <img src="https://media.tenor.com/Pnb_hVWq2sgAAAAj/on-process-dig.gif" width="35" height="35"/> Featured Projects

<div align="center">

<table>
<tr>
<td colspan="2" align="left">

### 🔱 Agam — The Systems Programming Language
**My Flagship Project: An Experimental Compiled Language Implemented in Rust**

<p align="center">
  <img src="https://img.shields.io/badge/Rust-DEA584?style=for-the-badge&logo=rust&logoColor=black" />
  <img src="https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white" />
</p>

An experimental systems programming language implemented from scratch across a **27-crate modular Rust workspace**. It bridges high-level developer ergonomics (Python-inspired `@lang.base`) with low-level systems control (`@lang.advance`) by lowering both syntax profiles into the exact same intermediate representation with 100% performance parity. Built from first principles to deeply master compiler architecture, intermediate representations, and the hardware/OS boundary.

#### ⚙️ Compiler Pipeline (Implemented & Tested)
- **Frontend (`crates/core`)**: UTF-8 span-tracking lexer (`agam_lexer`), Pratt parser with recursive descent for expressions and statements (`agam_parser`, `agam_ast`), and scope-aware bidirectional type checker (`agam_sema`).
- **Middle-End SSA Optimizer (`crates/middle`)**: Lowers to a custom Mid-level Intermediate Representation (`agam_mir`) in **Static Single Assignment (SSA)** form with explicit control flow graphs, basic blocks, immutable `ValueId` bindings, and phi nodes.
- **Transforming Optimization Passes**: Inlining of small leaf functions (`inline.rs`), constant folding & propagation (`constant_fold.rs`), dead-code elimination pruning unreachable blocks (`dce.rs`), loop unrolling (`loop_unroll.rs`), and E-Graph algebraic rewriting via equality saturation (`egg_engine.rs`).
- **Dual Execution Backends (`crates/backends`)**: 
  - **Cranelift JIT (`agam_jit`)**: In-memory compilation executing in `<15ms` for an instant interactive developer loop.
  - **Native LLVM 18+ AOT (`agam_codegen`)**: Direct SSA-to-LLVM IR lowering generating standalone native binaries through Clang with `-O3` optimizations.
  - **C Transpiler (`c_emitter.rs`)**: Portable C code generation fallback.
- **Platform Abstraction Layer (`crates/runtime/agam_runtime`)**: OS virtual memory management (`VirtualAlloc` on Windows, `mmap` on Linux) and cross-platform async I/O demuxing (`WSAPoll` / `epoll`).

#### 💡 Defensible Design Decisions & Engineering Insights
- **Dual-Syntax Unified IR**: Demonstrates that syntactic ergonomics and systems performance are not mutually exclusive—both syntax profiles share the identical SSA pipeline and machine code output.
- **Classical Linguistic Foundations**: Standard library operations structured on Pāṇinian root derivation (*Dhātu*) and Tamil case-marking (*Vibhakti*), treating API verbs as canonical immutable roots.
- **Nyāya Diagnostic Proof Engine**: Compiler diagnostics deliver 4-part structured logic proofs (Fact, Reason, Suggested Fix, Specification Law).
- **AI-Assisted with First-Principles Ownership**: Built using AI pair programming for rapid iteration, but architected, audited, and defended through personal mastery of SSA mathematics, graph lowering, dominance frontiers, and ABI conventions.
- **Benchmark Proven**: 55+ benchmark suites demonstrating native execution speeds 30x–90x faster than CPython, performing neck-and-neck with C++ Clang `-O3` and Rustc `-O`.

<p align="center">
  <a href="https://github.com/agam-lang/agam">
    <img src="https://img.shields.io/badge/View_Project-DEA584?style=for-the-badge&logo=github&logoColor=black" />
  </a>
</p>

</td>
</tr>
<tr>
<td width="50%" align="center">

### 🏥 MediManage
**Desktop Pharmacy Management Application**

<p align="center">
  <img src="https://img.shields.io/badge/Java-007396?style=for-the-badge&logo=openjdk&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
</p>

A desktop pharmacy management application built with JavaFX and SQLite, featuring offline-first data storage and an integrated local Python microservice for AI assistance.

**Key Features:**
- 📊 Real-time Inventory & Low-Stock Alerts
- 🤖 Local AI Microservice (Python & ONNX for offline inference)
- 📷 Barcode Scanner Integration (ZXing)
- 💰 Fast POS Billing & Thermal Receipt Printing
- 📈 Expense Tracking & Profit Calculation
- 🔒 Offline-First Local Storage (SQLite)
- 📄 PDF Invoice Generation (JasperReports / OpenPDF)

<a href="https://github.com/vikash236/MediManage">
  <img src="https://img.shields.io/badge/View_Project-7aa2f7?style=for-the-badge&logo=github&logoColor=white" />
</a>

</td>
<td width="50%" align="center">

### ⚡ OmniAIBench
**Hardware Monitoring & Benchmark Utility (WIP)**

<p align="center">
  <img src="https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white" />
</p>

An open-source desktop utility built with C/C++ and Qt for Windows to monitor system hardware in real-time, benchmark CPU performance, and track scores locally.

**Key Features:**
- 📡 Real-Time Hardware Detection (CPU, RAM, GPU via Windows WMI)
- 🔧 Multi-Threaded CPU Benchmarking (Single-core & multi-core tests)
- 📊 Hardware Sensor Monitoring (CPU load, temperatures & GPU metrics via PDH/NVML)
- 🏆 Local Score Tracking & Leaderboard (SQLite persistence)
- 🎨 Native Desktop UI (VS Code Dark-inspired theme built with Qt)

<a href="https://github.com/vikash236/OmniAIBench">
  <img src="https://img.shields.io/badge/View_Project-e6ff00?style=for-the-badge&logo=github&logoColor=black" />
</a>

</td>
</tr>
</table>

</div>

---

## <img src="https://media2.giphy.com/media/QssGEmpkyEOhBCb7e1/giphy.gif?cid=ecf05e47a0n3gi1bfqntqmob8g9aid1oyj2wr3ds3mg700bl&rid=giphy.gif" width="32px"/> Tech Stack & Skills

<details open>
<summary><b>💻 Programming Languages</b></summary>
<br>

<div align="center">

<table>
<tr>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=rust" width="55"/><br><b>Rust</b>
</td>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=python" width="55"/><br><b>Python</b>
</td>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=java" width="55"/><br><b>Java</b>
</td>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=c" width="55"/><br><b>C</b>
</td>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=r" width="55"/><br><b>R</b>
</td>
</tr>
</table>

</div>

</details>

<details open>
<summary><b>🧠 Machine Learning & Data Science</b></summary>
<br>

<div align="center">

<table>
<tr>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=tensorflow" width="55"/><br><b>TensorFlow</b>
</td>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=pytorch" width="55"/><br><b>PyTorch</b>
</td>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=sklearn" width="55"/><br><b>Scikit-learn</b>
</td>
<td align="center" width="100">
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/pandas/pandas-original.svg" width="55"/><br><b>Pandas</b>
</td>
<td align="center" width="100">
<img src="https://raw.githubusercontent.com/numpy/numpy/main/branding/logo/logomark/numpylogoicon.svg" width="55"/><br><b>NumPy</b>
</td>
<td align="center" width="100">
<img src="https://raw.githubusercontent.com/matplotlib/matplotlib/main/doc/_static/logo2.svg" width="55"/><br><b>Matplotlib</b>
</td>
</tr>
</table>

</div>

</details>

<details open>
<summary><b>🌐 Web & Backend</b></summary>
<br>

<div align="center">

<table>
<tr>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=react" width="55"/><br><b>React</b>
</td>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=nodejs" width="55"/><br><b>Node.js</b>
</td>
</tr>
</table>

</div>

</details>

<details open>
<summary><b>🗄️ Database</b></summary>
<br>

<div align="center">

<table>
<tr>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=mysql" width="55"/><br><b>MySQL</b>
</td>
</tr>
</table>

</div>

</details>

<details open>
<summary><b>🛠️ Tools & Networking</b></summary>
<br>

<div align="center">

<table>
<tr>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=git" width="55"/><br><b>Git</b>
</td>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=linux" width="55"/><br><b>Linux</b>
</td>
<td align="center" width="100">
<img src="https://api.iconify.design/lucide:network.svg?color=%237aa2f7" width="55"/><br><b>Networking</b>
</td>
</tr>
</table>

</div>

</details>

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Magnifying%20Glass%20Tilted%20Right.png" width="35" /> Currently Exploring

> Technologies, frameworks, and tools I am actively exploring and learning through hands-on practice.

<div align="center">

<table>
<tr>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=opencv" width="55"/><br><b>OpenCV</b>
</td>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=django" width="55"/><br><b>Django</b>
</td>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=fastapi" width="55"/><br><b>FastAPI</b>
</td>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=graphql" width="55"/><br><b>GraphQL</b>
</td>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=postgres" width="55"/><br><b>PostgreSQL</b>
</td>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=mongodb" width="55"/><br><b>MongoDB</b>
</td>
<td align="center" width="100">
<img src="https://skillicons.dev/icons?i=docker" width="55"/><br><b>Docker</b>
</td>
</tr>
</table>

</div>

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Travel%20and%20places/Fire.png" width="35" /> GitHub Statistics

<div align="center">
  
<img width="90%" src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=vikash236&theme=tokyonight" />
<br/>

<table>
<tr>
<td width="40%" align="center">

<img src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=vikash236&theme=tokyonight" width="100%" />

</td>
<td width="60%" align="center">

<img src="https://github-readme-activity-graph.vercel.app/graph?username=vikash236&bg_color=0d1117&color=7aa2f7&line=7aa2f7&point=ffffff&area=true&hide_border=false&border_color=7aa2f7&title_color=7aa2f7" width="100%" />

</td>
</tr>
</table>

</div>

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Animals/Snake.png" width="35" /> Contribution Snake

<div align="center">
  
<img src="https://raw.githubusercontent.com/vikash236/vikash236/output/snake.svg" alt="Snake animation" />

</div>

---

## <img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Chart%20Increasing.png" width="35" /> Development Journey

<div align="center">

```mermaid
timeline
    title My Coding Journey
    section 2022
        Getting Started : Programming Fundamentals
                        : C & Python Basics
    section 2023
        Core Foundations : Java & Object-Oriented Programming
                         : Data Structures & Algorithms
                         : Basic Machine Learning
    section 2024
        Applied Projects : Built MediManage (Desktop Pharmacy App)
                         : SQL & Relational Databases
                         : Systems Programming in Rust
    section 2025
        Deep Systems Learning : Building Agam (Rust Compiler, SSA MIR, JIT & LLVM)
                              : OmniAIBench Utility (Hardware & Benchmarking)
                              : Exploring Web Frameworks & Docker
    section 2026
        Future Focus : Compiler Engineering & Systems Software
                     : Open Source Contributions
                     : Continuous Learning & Building
```

</div>

---

## <img src="https://raw.githubusercontent.com/ShahriarShafin/ShahriarShafin/main/Assets/handshake.gif" width="60px"/> Connect With Me

<div align="center">

<table>
  <tr>
    <td align="center" width="120">
      <a href="https://ksvikash236.vercel.app/">
        <img src="https://skillicons.dev/icons?i=vercel" width="65" height="65" alt="Portfolio" />
        <br><b>Portfolio</b>
      </a>
    </td>
    <td align="center" width="120">
      <a href="https://www.linkedin.com/in/ksvikash236/">
        <img src="https://skillicons.dev/icons?i=linkedin" width="65" height="65" alt="LinkedIn" />
        <br><b>LinkedIn</b>
      </a>
    </td>
    <td align="center" width="120">
      <a href="mailto:ksvikash236@gmail.com">
        <img src="https://skillicons.dev/icons?i=gmail" width="65" height="65" alt="Gmail" />
        <br><b>Email</b>
      </a>
    </td>
    <td align="center" width="120">
      <a href="https://github.com/vikash236">
        <img src="https://skillicons.dev/icons?i=github" width="65" height="65" alt="GitHub" />
        <br><b>GitHub</b>
      </a>
    </td>
    <td align="center" width="120">
      <a href="https://x.com/KsVikashRe84251">
        <img src="https://skillicons.dev/icons?i=twitter" width="65" height="65" alt="Twitter" />
        <br><b>Twitter</b>
      </a>
    </td>
  </tr>
</table>

</div>

---

<div align="center">

## 🌟 "Building the future, one commit at a time." 🌟

<br/>

**⭐ If you like what you see, show some love by starring repositories! ⭐**

</div>

<p align="center">
  <b>Thanks for visiting my profile! If you appreciate my work, consider buying me a coffee. 😊</b>
</p>

<p align="center">
  <a href="https://buymeacoffee.com/vikash236" target="_blank">
    <img src="https://cdn.buymeacoffee.com/buttons/v2/default-red.png" alt="Buy Me A Coffee" width="160"/>
  </a>
</p>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=90&section=footer"/>
