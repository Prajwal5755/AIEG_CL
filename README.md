```
---
## 🗄️ Dataset: NSL-KDD
* **Total Records**: ~148,517 network connection flows.
* **Raw Features**: 41 network traffic attributes (protocol, service, flags, duration, byte counts, error rates, etc.).
* **Processed Dimension**: 122 one-hot encoded and standardized features.
* **Class Incremental Task Splits**:
  * **Task 1**: Normal (0) vs. DoS (1) — *113,270 train / 17,169 test*
  * **Task 2**: Add Probe (2) — *11,656 train / 2,421 test*
  * **Task 3**: Add R2L (3) — *995 train / 2,887 test*
  * **Task 4**: Add U2R (4) — *52 train / 67 test*
> **Synthetic Fallback**: If `KDDTrain+.txt` and `KDDTest+.txt` are not present in `./data/`, `data.py` automatically generates a synthetic multi-modal dataset so the pipeline and dashboard continue running without crashing.
---
## 🛠️ Troubleshooting & FAQ
* **Port 8501 is already in use:**
  Run the dashboard on an alternative port:
  ```bash
  streamlit run app.py --server.port 8502
  ```
* **To run in background mode on a remote server:**
  ```bash
  nohup ./run_dashboard.sh > dashboard.log 2>&1 &
  ```
* **Missing module errors:**
  Ensure you are using the correct Python interpreter:
  ```bash
  /home/prajwal/Traffic_Baseine/traffic_baseline/dl/bin/python3 app.py
  ```
---
## 📜 Citations & References
1. **NSL-KDD Dataset**: M. Tavallaee, E. Bagheri, W. Lu, and A. Ghorbani, *"A detailed analysis of the KDD CUP 99 data set,"* IEEE Symposium on Computational Intelligence for Security and Defense Applications (CISDA), 2009.
2. **Elastic Weight Consolidation (EWC)**: J. Kirkpatrick et al., *"Overcoming catastrophic forgetting in neural networks,"* Proceedings of the National Academy of Sciences (PNAS), 2017.
3. **Experience Replay**: D. Rolnick et al., *"Experience Replay for Continual Learning,"* NeurIPS, 2019.
