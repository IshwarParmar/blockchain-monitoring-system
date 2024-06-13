# Blockchain Monitoring Agent

## Setup Instructions

### Prerequisites

- Docker
- Docker Compose
- Go
- Anvil --- _Using `curl -L https://foundry.paradigm.xyz | bash`_

### Running the Monitoring Agent

Clone the repository:

git clone https://github.com/Ishwar-Parmar/monitoring-agent

cd monitoring-agent
Build and run the Go application:

go build -o monitor_metrics/main.go
./main

### Running the metrics locally

1. **Start local blockchain network:**
   run in a new terminal`anvil`

2. **Go to monitor_metrics dir in cli** and
   run `go run .`

### Running the metrics using docker

1. `sudo systemctl start docker`
2. `docker-compose build`
3. `docker-compose up`

## Approach Explanation
# Blockchain Monitoring

## Overview

This system monitors the Ethereum blockchain to detect vulnerabilities, threats, and attacks in real-time. It focuses on analyzing specific metrics related to smart contracts' operations, including function calls, emitted events, transaction numbers, and transaction statuses. This comprehensive approach aims to provide early warnings of potential security issues, facilitating swift remediation efforts.

## Metrics Monitored

### All Function Calls for Any Contract Address

- **Justification**: Identifies abnormal patterns indicative of malicious activities, such as denial-of-service attacks or unauthorized access attempts.
- **Real-Time Use Case**: Enables immediate detection of unusual patterns, prompting quick interventions to mitigate potential threats.

### All Events Emitted

- **Justification**: Detects anomalous behaviors, such as unexpected event emissions signaling breaches or exploitations of the contract.
- **Real-Time Use Case**: Alerts administrators to suspicious activities, allowing for rapid response to minimize damage.

### Number of Transactions

- **Justification**: Indicates a contract's popularity and usage, suggesting potential DDoS attacks or loss of trust due to bugs causing transactions to fail.
- **Real-Time Use Case**: Helps detect potential DDoS attacks or other forms of abuse early, enabling proactive measures to maintain service integrity.

### Status of Each Transaction for Any Blocknumber

- **Justification**: Assesses the operational health of a contract by identifying failed transactions, which could indicate logical errors, incorrect inputs, or vulnerability exploits.
- **Real-Time Use Case**: Quickly identifies failed transactions warranting investigation, suggesting systemic issues or attempted attacks exploiting known vulnerabilities.

## Setup and Execution

Before running the system, ensure the following environment variables are set:

- `NODE_URL`: The URL of the Ethereum node to connect to (e.g., Infura, Alchemy, or a local node).
- `ETHERSCAN_API_KEY`: Your Etherscan API key for accessing contract ABIs.

Execute the system by running the compiled binary. Ensure the required environment variables are set beforehand.
