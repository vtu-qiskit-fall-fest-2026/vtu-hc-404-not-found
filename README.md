<div align="center">

# 404 Not Found

**VTU-QFF-HC-0046** &nbsp;|&nbsp; Tier: **Both**

</div>

---

<div align="center">

| | |
| :--- | :--- |
| **Team** | 404 Not Found |
| **Team ID** | VTU-QFF-HC-0046 |
| **Tier** | Both |
| **Repository** | [vtu-hc-404-not-found](https://github.com/vtu-qiskit-fall-fest-2026/vtu-hc-404-not-found.git) |
| **Organisation** | [vtu-qiskit-fall-fest-2026](https://github.com/vtu-qiskit-fall-fest-2026) |
| **Event** | VTU-QFF Hackathon — VTU-Qiskit Fall Fest 2026 |

</div>

---

## 📌 Table of Contents

- [Team Members](#-team-members-github-ids)
- [Problem Statement](#-problem-statement)
- [Proposed Solution](#-proposed-solution)
- [Approach & Architecture](#-approach--architecture)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [How to Run](#-how-to-run)
- [How to Push Code](#-how-to-push-code)
- [Submission Checklist](#-submission-checklist)
- [Resources](#-resources)
- [License](#-license)

---

## 👥 Team Members (GitHub IDs)

> Members are added to this repository as **collaborators** and must accept the
> GitHub invitation before they can push. Add your GitHub username below.

| # | Name | GitHub Username | Role |
| :-- | :--- | :--- | :--- |
| 1 | Deepak Prakash Yaragatti | deepakyaragatti24-max | _Team Lead_ |
| 2 | Supreet Raghavendra Salunke | SupreetSalunke | _Developer_ |
| 3 | Rohit | rohitjadhav181205 | _Developer_ |

<!--
Optional: add a plain list instead of the table above.
- @username1
- @username2
-->

---

## ❓ Problem Statement

<!--
State the problem you are solving. Be specific: what is broken or missing,
who experiences it, and why does it matter. Link to the official problem
statement from the brief if one applies.
-->

**Problem:** Quantum Key Distribution (QKD) systems can experience noise, photon loss, and potential eavesdropping attempts, making it challenging to distinguish security threats from normal communication disturbances. Q-Sentinel uses AI/ML to analyze simulated quantum communication data and identify suspicious patterns.

**Why it matters:** Early detection of unusual communication behavior can help improve security monitoring, reduce false alarms, and support the development of more reliable quantum communication networks. The project is fully software-based and does not require physical quantum hardware.

**Track / Category:** Quantum Computing + Artificial Intelligence & Machine Learning (AI/ML) · Online / Offline: As per hackathon guidelines · Track 1 / Track 2: Confirm with the organizer's track definitions.

---

## 💡 Proposed Solution

<!--
Describe your solution. Keep it concrete: the core idea, the user flow, and
the quantum/ML technique you are applying.
-->

**Solution:** Q-Sentinel is an AI-powered monitoring system that simulates Quantum Key Distribution (QKD) communication and analyzes measurements to detect suspicious activity. It uses machine learning to identify unusual patterns caused by simulated eavesdropping, channel noise, or photon loss and displays alerts through an interactive dashboard.

**Key idea:** Combine quantum communication simulation with ML-based anomaly detection to identify suspicious communication patterns and distinguish them from normal channel disturbances.

**Why this works:** By analyzing multiple communication measurements rather than relying only on fixed thresholds, Q-Sentinel can identify complex patterns and help reduce false alarms. Its performance is evaluated against conventional detection methods using simulated scenarios, without requiring physical quantum hardware.

---

## 🧩 Approach & Architecture

<!--
Walk through how it works. A simple pipeline diagram in text or Mermaid is ideal.
-->

```mermaid
flowchart LR
    A[Input Data] --> B[Preprocessing]
    B --> C[Quantum Circuit / Model]
    C --> D[Post-processing]
    D --> E[Output]
```

1. **Input** — Communication Data
The system takes simulated Quantum Key Distribution (QKD) data generated using the BB84 protocol. The data is stored in CSV format and includes QBER, photon detection rate, channel loss, measurement outcomes, and scenario labels such as normal communication, noise, or simulated eavesdropping.
2. **Preprocessing** — Feature Extraction
The system cleans missing or invalid values, normalizes numerical features where necessary, and extracts useful indicators such as QBER changes and detection-rate variations. The features are organized into numerical vectors suitable for machine learning.
3. **Quantum core** — BB84 Simulation
A quantum circuit simulator, such as Qiskit, models quantum-state preparation, transmission, measurement, and selected attack scenarios. The simulator generates measurement outcomes and communication statistics; a quantum machine learning classifier can optionally be added as an advanced extension.
4. **Post-processing** — Detection and Risk Scoring
The measured statistics are used by a machine learning model, such as Random Forest, to classify communication scenarios or identify anomalies. The system calculates alert levels based on model predictions and configured rules, helping distinguish suspicious patterns from ordinary channel disturbances.
5. **Output** — Security Monitoring Dashboard
The user receives a dashboard displaying communication status, QBER graphs, detected anomalies, potential threat alerts, and explanations of relevant measurements. The system also provides model evaluation metrics such as precision, recall, F1 score, and false-positive rate.

---

## 🛠️ Tech Stack

| Layer | Technology |
| :--- | :--- |
| Language | Python 3.11+ |
| Quantum SDK | Qiskit `>=1.0`, Qiskit Aer, Qiskit Runtime |
| Optimisation | Qiskit Optimization / COBYLA / SPSA |
| Simulation | AerSimulator (statevector / noisemodel) |
| Environment | JupyterLab / VS Code, `venv` |
| Version control | Git + GitHub |

---

## 📁 Project Structure

```text
vtu-hc-404-not-found/
├── README.md              # This file
├── requirements.txt       # Python dependencies
├── pyproject.toml         # Project metadata (optional)
├── .gitignore
├── notebooks/             # Jupyter notebooks for experiments
│   └── exploration.ipynb
├── src/
│   ├── __init__.py
│   ├── circuit.py         # Quantum circuit construction
│   ├── optimizer.py       # Optimization loop
│   └── main.py            # Entry point
├── data/                  # Datasets (use Git LFS for large files)
├── tests/                 # Unit tests
│   └── test_circuit.py
└── docs/                  # Notes, diagrams, reports
```

---

## 🚀 How to Run

### Prerequisites

- Python 3.11 or newer
- [Git](https://git-scm.com/downloads)
- A GitHub account (you need collaborator access to this repo)

### 1. Clone the repository

```bash
git clone https://github.com/vtu-qiskit-fall-fest-2026/vtu-hc-404-not-found.git
cd vtu-hc-404-not-found
```

### 2. Create a virtual environment

```bash
python3 -m venv .venv
source .venv/bin/activate        # Linux / macOS
# .venv\Scripts\activate         # Windows (PowerShell)
```

### 3. Install dependencies

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Run

```bash
python -m src.main
```

Or launch the notebook workflow:

```bash
jupyter lab
```

### 5. Run the tests

```bash
pytest -q
```

---

## 🔁 How to Push Code

> Full walkthrough: **[Git & Collaboration Handbook](../vtu-hc-guide-git-and-collaboration)** — collaboration
> workflow, branches, pull requests, reviews and conflict resolution.

### Configure Git (first time only)

```bash
git config --global user.name  "Your Name"
git config --global user.email "you@example.com"
```

### Everyday workflow

```bash
# 1. Get the latest changes
git checkout main
git pull origin main

# 2. Create a branch for your work
git checkout -b feature/my-task

# 3. Commit your work
git add .
git commit -m "feat: add variational circuit for the search problem"

# 4. Push the branch
git push -u origin feature/my-task

# 5. Open a Pull Request on GitHub and request a review
#    https://github.com/vtu-qiskit-fall-fest-2026/vtu-hc-404-not-found/compare/main...feature/my-task

# 6. After approval, merge into main
git checkout main
git pull origin main
git branch -d feature/my-task
```

### Commit message convention

| Prefix | Meaning |
| :--- | :--- |
| `feat:` | New feature |
| `fix:` | Bug fix |
| `docs:` | Documentation only |
| `test:` | Adding or fixing tests |
| `refactor:` | Code restructure, no behaviour change |
| `chore:` | Build/config/dependency changes |

### Useful commands

```bash
git status              # what changed
git log --oneline -10   # recent commits
git diff                # review changes before committing
git stash               # shelve changes temporarily
git pull --rebase       # update your branch on top of main
```

### Collaborating on the same repo

- **Never push directly to `main`** — open a Pull Request.
- **Pull before you push** to avoid rejected commits.
- **Commit often** with clear messages.
- **Resolve conflicts** locally: `git pull --rebase`, fix the files, then `git add` + `git rebase --continue`.
- **Ask for a review** before merging — a second pair of eyes catches bugs fast.

---

## ✅ Submission Checklist

- [ ] Repository created and **public**
- [ ] All team members added as **collaborators** and invitations accepted
- [ ] `README.md` updated with project details, problem statement and solution
- [ ] Team members listed under [Team Members](#-team-members-github-ids)
- [ ] `requirements.txt` committed and project runs from a clean clone
- [ ] Code pushed to `main` and the latest `main` builds successfully
- [ ] Notebooks committed with **cleared outputs** (or use `nbstrip`)
- [ ] `README` includes a demo screenshot / video link
- [ ] Short project summary submitted on the hackathon portal

---

## 📚 Resources

| Resource | Link |
| :--- | :--- |
| 🔁 Git & collaboration handbook | [Git & Collaboration Handbook](../vtu-hc-guide-git-and-collaboration) |
| ❓ Problem statements, solutions & terms | [Problem Statements, Solutions & Terms](../vtu-hc-guide-problem-and-solution) |
| 📄 README writing guide | [README Guide & Template](../vtu-hc-guide-readme-template) |
| ⚛️ Qiskit documentation | https://docs.quantum.ibm.com/ |
| ⚛️ Qiskit Runtime & primitives | https://quantum.cloud.ibm.com/docs/ |
| 🧪 Qiskit Aer simulator | https://docs.quantum.ibm.com/guides/simulator |
| 💻 IBM Quantum Platform | https://quantum.cloud.ibm.com/ |
| 🎓 Qiskit textbook | https://qiskit.qotlabs.org/learning/ |
| 📋 GitHub Docs | https://docs.github.com/ |

---

## 📄 License

Released under the [MIT License](LICENSE). See `LICENSE` for details.

---

<div align="center">

**404 Not Found** · Team ID `VTU-QFF-HC-0046` · Tier `Both`
· Built with ⚛️ Qiskit for the VTU-QFF Hackathon

[⬆ Back to Top](#404-not-found)

</div>
