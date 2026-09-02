# Danila Gorbatenko

**Software developer building applications where correctness matters — applied cryptography, systems programming in C++, and machine learning.**

📍 Brussels, Belgium · Computer Science (Industrial Automation) at HE2B–ESI

---

## About Me

I write software across the stack, with a consistent pull toward problems that have a verifiable right answer: an encryption scheme that either holds or does not, a game engine whose rule system must resolve deterministically, a cryptanalytic attack that either recovers the key or does not.

Most of what I build falls into three areas:

- **Secure web applications** — Django backends with client-side cryptography, authentication hardening and auditable access control.
- **Systems and desktop programming** — C++20 with object-oriented design, unit tests and documented architecture.
- **Applied machine learning** — reinforcement learning agents in PyTorch and computer vision models in TensorFlow/Keras, served over HTTP APIs.

My degree is in industrial automation, so I am also comfortable close to hardware — embedded controllers, PLCs and networking — which shapes how I think about constraints and failure modes in software.

I am looking for a **junior software developer** or **graduate programme** position, with particular interest in backend development, security engineering or applied ML. Open to roles in Belgium and remote.

---

## Tech Stack

Technologies below are ones I have used to build and ship the projects in this profile or in my coursework.

### Languages

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=flat&logo=cplusplus&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat&logo=c&logoColor=black)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat&logo=openjdk&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=postgresql&logoColor=white)

### Backend

![Django](https://img.shields.io/badge/Django-092E20?style=flat&logo=django&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat&logo=flask&logoColor=white)
![Uvicorn](https://img.shields.io/badge/Uvicorn%20%2F%20ASGI-499848?style=flat)
![REST](https://img.shields.io/badge/REST%20APIs-005571?style=flat)

### Frontend

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![Web Crypto API](https://img.shields.io/badge/Web%20Crypto%20API-4B0082?style=flat)
![Qt](https://img.shields.io/badge/Qt5-41CD52?style=flat&logo=qt&logoColor=white)

Vanilla ES modules and Django templates; Qt5 and ncurses for desktop and terminal interfaces.

### Databases

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white)
![Oracle](https://img.shields.io/badge/Oracle-F80000?style=flat&logo=oracle&logoColor=white)
![IBM Db2](https://img.shields.io/badge/IBM%20Db2-052FAD?style=flat&logo=ibm&logoColor=white)

### Machine Learning

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-D00000?style=flat&logo=keras&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=opencv&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)

Gymnasium for reinforcement learning environments; Matplotlib for analysis.

### Security

Applied cryptography with the Web Crypto API and Python `cryptography`: AES-256-GCM, ECDH and ECDSA on P-256, HKDF, TLS, Merkle trees, SRP-6a, multi-factor authentication and hash-chained audit logs. Classical cryptanalysis — frequency analysis, the Index of Coincidence, and a ciphertext-only Playfair attack scored on English quadgrams.

### Tools

![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![GNU Make](https://img.shields.io/badge/GNU%20Make-427819?style=flat&logo=gnu&logoColor=white)
![Doxygen](https://img.shields.io/badge/Doxygen-2C4AA8?style=flat)
![Catch2](https://img.shields.io/badge/Catch2-DC322F?style=flat)

Git, Linux, GNU Make, Doxygen and Javadoc, Catch2, StarUML for UML modelling.

### Also worked with

Embedded and automation coursework outside these repositories: Arduino and ESP8266, Raspberry Pi, LabVIEW, Siemens TIA Portal and SIMATIC STEP 7, Stäubli Robotics Suite, Cisco Packet Tracer, Flutter.

---

## Featured Projects

### 🔐 [Secure Medical Records](https://github.com/dagorbatenko/secure-medical-records)

An end-to-end encrypted medical records portal where patients own their data cryptographically and grant doctors access through signed, explicit consent. Files are encrypted in the browser — the server stores ciphertext only and can never read a patient's record.

**Tech:** Django 5.2 · Python · Web Crypto API · SRP-6a · PostgreSQL / SQLite · Uvicorn

**Highlights:**
- Per-file AES-256-GCM keys generated client-side and wrapped for each authorised doctor using ECDH (P-256) + HKDF, so access is granted by cryptography rather than by a database flag the server could flip.
- Uploads are committed via an ECDSA-signed Merkle root over 64 KiB chunks, giving tamper detection and non-repudiation for changes to a clinical record.
- Doctor-initiated changes go to a staging area and require the patient's cryptographically signed approval; every security event is written to a hash-chained audit log verifiable offline.
- Login with SRP-6a (password stays in the browser), email OTP, brute-force lockouts, CSP and a single-active-session policy.

**Demonstrates:** applied cryptography, threat modelling, zero-trust architecture, full-stack Django, and designing a system whose security properties do not depend on trusting the operator.

→ [Repository](https://github.com/dagorbatenko/secure-medical-records)

---

### 🎮 [Baba Is You — C++ Game Engine](https://github.com/dagorbatenko/baba-is-you-cpp)

A C++20 implementation of the puzzle game where the rules of play are objects on the board that the player can rearrange to redefine how the game behaves. One engine core drives two interchangeable front-ends.

**Tech:** C++20 · Qt5 · ncurses · GNU Make · Catch2 · Doxygen

**Highlights:**
- Dynamic rule engine: `<SUBJECT> IS <PROPERTY>` sentences are re-parsed from board state after every move and applied to a fixed point, so cascading effects — a transformation that forms a new sentence which activates a new rule — resolve correctly within one turn.
- Seven rule types implemented as polymorphic Strategy objects, so a new game mechanic is a new class rather than a new branch.
- Model–View–Controller with the Observer pattern: the same core runs unchanged behind an ncurses terminal renderer and a Qt5 animated GUI.
- Compiles under `-Wpedantic -Werror`, unit tested with Catch2, documented with Doxygen and UML class diagrams.

**Demonstrates:** object-oriented design, design patterns, modern C++, separation of concerns, and testing and documenting a non-trivial codebase.

→ [Repository](https://github.com/dagorbatenko/baba-is-you-cpp)

---

### 🧊 [Frozen Lake — Q-Learning vs. Deep Q-Networks](https://github.com/dagorbatenko/frozen-lake-rl)

A comparative reinforcement learning study on a stochastic grid-world, implementing tabular Q-learning and a Deep Q-Network from scratch, plus a custom renderer that draws live Q-values onto the game board.

**Tech:** Python · PyTorch · Gymnasium · NumPy · Matplotlib · pygame

**Highlights:**
- DQN assembled from its components against raw PyTorch: a 16→128→128→4 network over one-hot states, a 10,000-transition replay buffer, a periodically synchronised target network and an annealed epsilon-greedy policy.
- Reward shaping to make a sparse binary reward learnable, with committed training curves showing mean reward rising from roughly −100 to +40 over 25,000 episodes.
- A fork of the Gymnasium environment that overlays all four Q-values on every tile and highlights the greedy action, turning a learned policy into something you can watch.
- Trained artifacts committed, so both agents can be evaluated without retraining.

**Demonstrates:** reinforcement learning fundamentals, PyTorch, experiment instrumentation, and reasoning about why one approach outperforms another rather than only that it does.

→ [Repository](https://github.com/dagorbatenko/frozen-lake-rl)

---

### 🧩 [Playfair Cryptanalysis](https://github.com/dagorbatenko/playfair-cryptanalysis)

A ciphertext-only attack on the Playfair cipher: recover a working 5×5 grid from ciphertext alone by shotgun hill-climbing, scored against English letter quadgrams. Brute force is impossible (25! keys); the program searches by how English a decryption looks.

**Tech:** Python (standard library only) · unittest

**Highlights:**
- Playfair encrypt/decrypt with homework padding and a `j`→`i` 5×5 grid, covered by unit tests including the statement vector `Hello World!` → `eiyvrvvqdrkv`.
- Shotgun hill-climbing over random squares, with restarts when the search sticks on an “almost English” local maximum (~−6.7) instead of real English (~−4.1).
- Quadgram log-probabilities in a flat `25⁴` table, in-place undo of failed mutations, and a cheap 25-way row/column-shift cleanup that exploits Playfair’s grid symmetries.
- A `demo` that encrypts an Alice excerpt, then attacks it without being told the keyword.

**Demonstrates:** heuristic cryptanalysis, scoring functions as a substitute for a known key, and implementing a search that cannot be brute-forced.

→ [Repository](https://github.com/dagorbatenko/playfair-cryptanalysis)

---

### 🔓 [Classical Cipher Cryptanalysis](https://github.com/dagorbatenko/classical-cipher-cryptanalysis)

A toolkit that breaks Caesar and repeating-key XOR ciphers without knowing the key, recovering both key length and key material from ciphertext alone.

**Tech:** Python (standard library only) · GNU Make

**Highlights:**
- Two-stage attack on repeating-key XOR: the period is recovered statistically via the Index of Coincidence, which reduces an unbounded key space to *n* independent single-byte problems that are then brute-forced per column.
- English letter-frequency scoring as the recognition function that makes ciphertext-only attacks possible — the actual difficulty in breaking a cipher, as opposed to decrypting one.
- Verified end to end against a full-length English corpus: correct Caesar shift recovery, correct key-length detection, and key reconstruction.
- Zero third-party dependencies; every statistical routine implemented directly.

**Demonstrates:** cryptanalysis and statistical reasoning, translating mathematical technique into working code, and clean modular Python.

→ [Repository](https://github.com/dagorbatenko/classical-cipher-cryptanalysis)

---

## Contact

- **GitHub:** [dagorbatenko](https://github.com/dagorbatenko)
- **Email:** [gorbatenko.danila1999@gmail.com](mailto:gorbatenko.danila1999@gmail.com)
- **Location:** Brussels, Belgium
- **Languages:** English (advanced), French (advanced)
