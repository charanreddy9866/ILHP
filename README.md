Reliable Data Transfer Simulation

This project is a simulation of a reliable data transfer protocol using Go-Back-N ARQ (Automatic Repeat reQuest). The implementation utilizes Python's threading and queue modules to simulate a sender and receiver communicating over an unreliable network.

Features

Implements a Go-Back-N ARQ protocol with a sliding window.

Simulates packet loss and corruption.

Uses timers to handle retransmissions upon timeout.

Runs sender and receiver as concurrent threads.

How It Works

The sender transmits packets with a sequence number, ensuring only a limited number of unacknowledged packets are in transit.

The receiver acknowledges received packets, indicating whether they were received correctly.

If a packet is lost or corrupted, the receiver sends an invalid acknowledgment.

If the sender does not receive a valid acknowledgment within a timeout period, it retransmits all packets from the base sequence number.

Parameters

You can modify these parameters to test different network conditions:

MAX_SEQ = 7 → Maximum sequence number (defines sequence number space).

WINDOW_SIZE = 4 → Number of packets that can be sent before needing acknowledgment.

TIMEOUT = 2 → Timeout duration (in seconds) for retransmission.

PACKET_LOSS_PROB = 0.1 → Probability of a packet being lost.

PACKET_CORRUPTION_PROB = 0.05 → Probability of a packet being corrupted.

NETWORK_DELAY = 0.1 → Simulated network delay (in seconds).

Running the Simulation

Prerequisites

Ensure you have Python installed (version 3.x recommended).

Steps

Clone this repository:

git clone https://github.com/yourusername/reliable-data-transfer.git
cd reliable-data-transfer

Run the script:

python main.py

The simulation will start, and you will see logs for sent packets, received packets, acknowledgments, and retransmissions.

Example Output

Packet 0 sent, corrupted: False
Packet 1 sent, corrupted: False
Packet 2 sent, corrupted: True
Packet 3 sent, corrupted: False
Packet 0 received, corrupted: False
Received ACK for 0, valid: True
Packet 2 received, corrupted: True
Received ACK for 2, valid: False
Timeout occurred, resending packets from: 2 to 3
Packet 2 sent, corrupted: False

License

This project is open-source and available under the MIT License.

Contribution

Feel free to submit issues or pull requests to improve the implementation!
