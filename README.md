# RiftSight
Graph-Based Financial Fraud Intelligence System


## Problem

Financial fraud in modern banking systems has evolved beyond isolated suspicious transactions into coordinated, multi-entity networks. Traditional rule-based monitoring systems evaluate transactions individually, making them incapable of identifying patterns that span across multiple accounts, branches, and time intervals.

For instance, a transfer of ₹10 crores routed through several accounts within a short time frame may appear legitimate when analyzed transaction-by-transaction. However, when viewed as a network of interactions, it reveals structured laundering behavior. This limitation creates significant blind spots in existing fraud detection systems.

---

## Solution

RiftSight approaches fraud detection as a network intelligence problem rather than a transaction validation problem. By modeling financial activity as a graph, it enables the detection of hidden relationships, fund flows, and coordinated fraud patterns that are otherwise undetectable in traditional systems.

---

## System Architecture

### Graph Data Layer

- Built using Neo4j
- Accounts are represented as nodes
- Transactions are modeled as directed, time-stamped edges
- Supports efficient traversal and pattern discovery across large-scale transaction networks

---

### Detection Modules

RiftSight incorporates multiple graph-based detection mechanisms:

**Temporal Layering**  
Identifies rapid movement of funds across multiple accounts within short time windows, indicating potential laundering activity.

**Cycle Detection**  
Detects loops in the transaction graph where funds return to the originating account after passing through intermediate accounts.

**Structuring (Smurfing)**  
Identifies fragmentation of large transactions into smaller amounts below regulatory thresholds (₹10 lakhs under PMLA).

**Dormant Re-Entry**  
Flags accounts that have been inactive for extended periods and suddenly exhibit high transaction activity.

---

### Behavioral Intelligence

- Accounts are dynamically profiled based on transaction behavior
- Clustering techniques group similar behavioral patterns
- Deviations from expected peer group behavior are flagged
- Example: accounts with low declared income exhibiting high-volume commercial activity

---

### Privacy and Security

- Sensitive identifiers such as Aadhaar, PAN, and account numbers are hashed using SHA-256
- Personally identifiable information remains masked by default
- De-masking is restricted to authorized investigative workflows

---

### Explainability Layer

- Generates human-readable explanations for detected fraud patterns
- Provides clear descriptions of:
  - fraud typology
  - involved accounts
  - transaction pathways

---

### Visualization Dashboard

Built using React and Cytoscape.js

- Interactive graph visualization of account networks
- Time-based exploration of transaction flows
- Risk-based highlighting of accounts using graph centrality measures
- Investigator-focused drill-down capabilities

---

### Automated Reporting

- Generates structured Suspicious Transaction Reports
- Includes:
  - complete transaction trail
  - identified risk indicators
  - system-generated narrative
- Designed for regulatory submission workflows

---

## Impact

**Operational Efficiency**  
Reduces manual effort required to trace complex transaction chains by enabling graph-based querying and visualization.

**Targeted Detection**  
Improves detection accuracy by focusing on behavioral anomalies and network patterns, reducing false positives.

**Regulatory Compliance**  
Automates reporting processes and ensures consistency, minimizing the risk of compliance-related errors.

---

## Tech Stack

- Backend: Python
- Database: Neo4j
- Graph Processing: Cypher queries, network analysis
- Machine Learning: clustering and anomaly detection
- Frontend: React, Cytoscape.js
- Security: SHA-256 hashing
- AI Layer: natural language generation for explanations

---

## Future Work

- Real-time transaction streaming and detection
- Advanced graph-based machine learning models
- Cross-institution fraud network analysis
- Adaptive risk scoring systems

---

## Conclusion

RiftSight redefines fraud detection by shifting from isolated transaction monitoring to network-level analysis. By integrating graph databases, behavioral intelligence, and explainable systems, it enables more effective identification of complex financial fraud patterns.
