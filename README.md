# minitalk
 ## Project Overview  
 The purpose of this project is to code a small data exchange program using UNIX signals. It serves as an introductory project for the larger UNIX projects that will appear later in the curriculum.
 
## Understanding the Terms

Like many first-time encounters with the topics of 42 projects, the terminology used can be confusing. This guide aims to clarify these terms to help you better understand and successfully complete the project.

### Key Concepts

1. **UNIX Signals**: Signals are a limited form of inter-process communication used in UNIX, Linux, and other POSIX-compliant operating systems. They are used to notify a process that a specific event has occurred.

2. **Data Exchange Program**: In the context of this project, a data exchange program is a system where data is transmitted between two processes. This transmission is managed using UNIX signals.

3. **Processes**: A process is an instance of a running program. In this project, you will be working with at least two processes – a sender and a receiver.

### Project Goals

- **Sender Program**: This program will take a string as input and send it, character by character, to the receiver program using UNIX signals.
- **Receiver Program**: This program will capture the signals sent by the sender, reconstruct the original string, and display it.

### Signals Used

- **SIGUSR1**: A user-defined signal, typically used to represent a binary '0'.
- **SIGUSR2**: Another user-defined signal, typically used to represent a binary '1'.

### Steps to Implement

1. **Set Up Signal Handlers**: Both the sender and receiver need to handle SIGUSR1 and SIGUSR2 signals appropriately.
2. **Convert Data to Binary**: The sender needs to convert each character of the input string into its binary representation.
3. **Send Signals**: The sender will send SIGUSR1 and SIGUSR2 signals to represent binary '0' and '1', respectively.
4. **Reconstruct Data**: The receiver will capture these signals, reconstruct the binary data into characters, and form the original string.

### Example Workflow

1. **Sender Program**:
    - Input: "Hello"
    - Convert "H" to binary: 01001000
    - Send SIGUSR1 for '0' and SIGUSR2 for '1' following the binary representation.
    - Repeat for each character.

2. **Receiver Program**:
    - Capture signals SIGUSR1 and SIGUSR2.
    - Reconstruct the binary sequence.
    - Convert binary back to characters.
    - Output: "Hello"
