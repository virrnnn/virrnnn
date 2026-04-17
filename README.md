<h1 align="center">Virendra Singh Sisodia</h1>
<h3 align="center">C++ Low-Latency Engineer | Trading Systems | Multithreading</h3>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=virrnnn&label=Profile%20Views&color=blue&style=flat" />
</p>

<p align="center">
  <a href="mailto:viren.vs93@gmail.com">Email</a> •
  <a href="https://www.linkedin.com/in/virendra-singh-33a7b9218/">LinkedIn</a> •
  <a href="https://github.com/virrnnn">GitHub</a>
</p>

---

## 🧠 Who I Am

I build **low-latency C++ systems that survive production pressure**.

- ⚙️ 3+ years in **trading infrastructure**
- 🚀 Focused on **latency, memory optimization, and concurrency**
- 🧵 Strong in **multithreading, IOCP, synchronization**
- 🛡️ Experienced in **VAPT fixes, crash debugging, reverse engineering protection**

Worked on production-grade systems used by exchanges:

> **ODIN Suite** — Client, Admin, Diet, CNT  
> Previously at **63 Moons Technologies (FTIL)**  
> Currently at **SynapseWave Innovations**

---

## ⚡ Impact (Production Work)

- 🔐 Fixed **50+ security vulnerabilities** across 20+ VAPT tickets  
- 🚀 Reduced application login latency by **40%**  
- 🧠 Replaced legacy `CMap` with STL → **better performance + lower memory usage**  
- 🏦 Implemented **SEBI-compliant trading features** in live systems  

---

## 🛠️ Tech Stack

### Languages
`C` `C++17` `Python`

### Systems & Concurrency
`Multithreading` `IOCP` `Mutex` `Atomics`

### Frameworks & Libraries
`MFC` `STL` `Redis`

### Networking
`Socket Programming` `Client-Server Architecture` `Async IO`

### Databases
`SQL`

### DevOps
`Git` `Bitbucket` `Shell Scripting`

### Core Concepts
`OOP` `DSA` `DBMS` `Agile`

---

## 🚀 Projects

### 🏦 Banking System (C++17)
- Multi-user banking system with **fine-grained locking**
- File persistence + session management
- Focus on **data consistency and concurrency safety**
- Modular OOP design with strong error handling

---

### 🌐 IOCP Client-Server System
- High-performance server using **Windows IOCP**
- Handles **multiple concurrent clients efficiently**
- Designed for **low-latency communication**
- Scalable multithreaded architecture

---

## ⚙️ Sample: Thread-Safe Counter

```cpp
#include <atomic>
#include <thread>
#include <vector>
#include <iostream>

std::atomic<int> counter = 0;

void increment() {
    for (int i = 0; i < 100000; ++i)
        counter.fetch_add(1, std::memory_order_relaxed);
}

int main() {
    std::vector<std::thread> threads;

    for (int i = 0; i < 4; ++i)
        threads.emplace_back(increment);

    for (auto& t : threads)
        t.join();

    std::cout << "Counter: " << counter << std::endl;
}
