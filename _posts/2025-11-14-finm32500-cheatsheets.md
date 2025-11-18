---
layout: post
description: FINM 32500
categories: [finm32500, cheatsheets, fall25, markdown]
title: Computing for Finance in Python
use-math: true
toc: true
---

## Object-Oriented Programming

- **Polymorphism**: Multiple objects with the same method name, can use them the same way
    - Accomplished using duck-typing (no inheritance) or inheritance (use same base class)
    - **Abstract Base Class (ABC)**: A base class that defines what methods the children must have, cannot be instantiated directly and uses `@abstractmethod` decorators
- Classes can inherit from more than one parent class, conflicting method names are resolved using the **Method Resolution Order (MRO)**
- `@property` turns a method into an attribute, can define a setter, getter, and deleter without having to add a new attribute

### Design Patterns

- **Creational Patterns**: Control how objects are created
    - *Factory*: Create objects by passing in an identifier of which object you want, abstracts away the logic to instantiate
    - *Singleton*: Ensures that a class has only one instance
        - Implemented using the `__new__` operator which creates and returns an instance; return the class instance if it already exists
    - *Builder*: Constructs objects step by step, adding on attributes and methods as requested
- **Structural Patterns**: Define relationships between components
    - *Decorator*: Add behavior to a class or function without modifying it
        - Add parameters to a decorator by creating a decorator factory which adds another function on top of the decorator
    - *Adapter*: Convert one interface into another
    - *Composite*: Treat individual objects and groups uniformly
- **Behavioral Patterns**: Manage communication and control flow between objects
    - *Strategy*: Enapsualtes interchangeable algorithms
    - *Observer*: Notifies dependent objects (subscribers) of state changes
        - Objects subscribe to the observer, and the server notifies them of changes to the state
    - *Command*: Encapusales requests as objects
    - *Iterator*: Access elements one at a time
        - Implemented using `__iter__` and `__next__` 
    - *Generator*: Uses `yield` to produce values one at a time

## Parallel Computing
- A **process** has its own memory space, CPU context, execution flow, and resources; each Python process has its own, separate interpreter
    - Each process runs independently from each other and cannot interact with each other unless using shared memory or TCP
- A **thread** is a part of a process, can run multiple threads that all execute concurrently
    - Use the same memory space as the process and are more lightweight, but have issues due to the **Global Interpreter Lock (GIL)** in Python, meaning that only one thread can truly run at a time
- Threads are better for system responsiveness and handling multiple tasks at the same time that don't need to be done concurrently, while processes are better for true parallelism
    - Threads are also good for when tasks spend time waiting, such as for network requests or database queries
- **Context switching**: When the CPU switches from one task to another; requires multiple saves and loads of states
    - Threads context switch more often and faster but risk race conditions

## Inter-Process Communication/Networking

- **IPC** allows processes to exchange data and communicate
    - Leads to modular design, parallelism, and resource/time management
- Types of IPC
    - *Pipes*: One-way stream between processes, used for parent-child communication
    - *Named pipes*: Like pipes but can be accessed by unrelated processes
    - *Message queues*: Send/receive messages using a queue, used for asynchronous messaging
    - *Shared memory*: Multiple processes use the same memory region, best for high-speed data sharing
        - Requires synchronization (due to race conditions and data overwriting) and is difficult to debug
    - *Socket*: Network-based communication through TCP/IP, best used for remote or cross-platform communication
    - *Signals*: Notifications between processes, used for interrupts, shutdowns, or alerts

### Networking
- Data exchange over wireless connections
- **Host**: Device connected to a network
- **Protocol**: Rules for communication
- **Packet**: A chunk of data sent across the network
- **IP Address**: Unique identifier for a device
- **Port**: An endpoint for specific services
- **Open Systems Interconnection (OSI) model**: Breaks networking into 7 layers, giving each layer a role in data transmission
    1. Physical
        - Transmits raw binary data over physical forms (eleectrical, optical, radio)
        - Defines hardware specifications for cables, connectors, etc.
        - Key characteristics include bandwidth, latency, attenuation, interference, propagation speed, cost, security, flexibility, distance limit
        - Includes ethernet cables and radio signals
    2. Data Link
        - Packages raw bits into frames for transmission and handles local delivery between devices
        - Manages MAC addressing, error detection, and access control ()
        - Includes ethernet and Wi-Fi
    3. Network
        - Handles logical addressing (IP address)
        - Determines best path for data to travel and enables *internetworking* (connecting networks together)
        - Breaks data into packets
        - Includes IP and routers
    4. Transport
        - Manages communication between devices and ensures complete, ordered, error-free delivery of data
        - Includes TCP (connection-oriented) and UDP (connectionless) services
            - TCP guarantees delivery, order, and error-checking and has flow control but is slower; used for web browsing, email, file transfer
            - UDP has no guarantees but is much faster; used for streaming, gaming, or VoIP (Voice over IP)
    5. Session
        - Handles logical sessions between applications
        - Coordinates dialogue control and supports checkpointing and recovering in long-running data exchanges
        - Includes RPC, VoIP setup and teardown
    6. Presentation
        - Converts data into an understandable format for applications, encrypting and decrypting data
        - Optimizes bandwidth usage using compression and ensures data interoperability
        - Includes JSON formatting, JPEG/MP3 encoding
    7. Application
        - Provides network services directly to applications, enabling data exchange, browsing, messaging, file transfer
        - Defines protocols for different tasks
        - Includes HTTP, FTP, DNS
- A **socket** enables communication between processes through writing code at Layer 7; the OS and network handles layers 1-6
    - Can choose either TCP or UDP
- *Client-server architecture*: A server listens for requests and sends data to its clients 
    - Multi-client servers must use parallelism to handle clients, like threading or multiprocessing