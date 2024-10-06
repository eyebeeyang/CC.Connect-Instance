# All About Connecting to an Instance (Work In Progress pa po)
An **EC2 instance** is a virtual server in Amazon's Elastic Compute Cloud (EC2) that provides scalable compute capacity. It allows users to run applications, host websites, or perform any kind of computation in the cloud without the need for physical hardware. The instance operates much like a physical computer, but it's managed and provisioned from the AWS platform. EC2 instances come with different configurations of CPU, memory, storage, and networking capacity, making them customizable for various workloads.

### Why do we connect to an instance?
Connecting to an instance allows an access to a server in the cloud, allowing administrators and developers to manage, configure, and maintain the infrastructure remotely. By connecting, we can install and update software, troubleshoot issues, and monitor performance. It ensures that cloud-hosted services are secure and functions efficiently.

## Secure Shell (SSH)
EC2 supports different methods for connecting to instances using SSH, including direct connections using an SSH client or browser-based SSH connections using EC2 Instance Connect. SSH is widely used for securely connecting to remote servers, particularly Linux-based systems. Additionally, every connection attempt via SSH is logged, making it easier to audit and track who accessed the instance. This is especially important in environments with multiple users and instances.

### What is Key-pair?
A **key pair** is a set of two cryptographic keys—a **public key** and a **private key**—that work together to secure access to your Amazon EC2 instance. It consists of:

![keypair](https://github.com/user-attachments/assets/085613dc-ceab-451e-a9ca-9098cb4d2bbf)


**Public Key** - stored on the EC2 instance and can be shared publicly

**Private Key** - stored seccurely on your computer, ensuring that only authorize users can connect to the EC2 environment

These two keys work together to encrypt and decrypt data, enabling secure, password-free access to servers.



### SSH and Key-Pair: Relationship? HAHAHA
SSH (Secure Shell) uses public-key cryptography, a method of encryption that relies on two mathematically linked keys, known as a key pair: a public key (shareable) and a private key (secret). In SSH, two separate key pairs are involved—user key pair (client) and host key pair (server)—each with its own public and private key. This dual setup enhances mutual authentication and ensures a secure SSH connection between the client and server.

How the Key Pairs Work in SSH
User Key Pair (Client-Side Authentication):

Private Key: Held securely by the user on their local machine and never shared. This key is used to prove the user’s identity.
Public Key: Placed on the SSH server in the ~/.ssh/authorized_keys file, allowing the server to recognize and trust the client.
Host Key Pair (Server-Side Authentication):

Private Key: Generated and stored securely on the SSH server. Users generally don’t interact with this key directly.
Public Key: Provided to users when they first connect to the server. SSH clients store this public key and use it to verify the server’s identity in future sessions.
How the Key Pairs Work Together in SSH Authentication
Mutual Authentication: Both the server and client verify each other’s identity through these key pairs. When the client connects, it authenticates using the server's public key (stored locally after the first connection) and its own private key. The server verifies the client’s public key against its authorized_keys file.

Secure Connection: If both verifications pass, the connection is established securely, and data exchanged over SSH is encrypted.

Key Pair Security Benefits in SSH
No Passwords in Transit: Only the public keys are shared, protecting against interception.
Enhanced Trust: Users know they’re connecting to the right server, and servers know they’re connecting to authorized clients.
Encryption and Authentication: SSH uses the key pairs to encrypt the session and verify both sides, ensuring privacy and security.

## 4 Method of Connecting to an Instance
There are 4 ways of connecting to an instance. Amazon EC2 offers various methods for connecting to instances depending on the operating system of the instance and the user's needs. Each of these ways has distinct use cases, security mechanisms, and platform compatibility.
1. **EC2 Instance Connect**
2. **SSH Client**
3. **Remote Desktop Protocol (RDP)**
4. **Session Manager**

In this workshop, let us discuss the first three ways to connect to an instance.

## Method 1: EC2 Instance Connect
Connecting via **EC2 Instance Connect** is a feature that enables a secure connection to your Linux instances over SSH. EC2 Instance Connect allows you to connect to your instance directly through your browser. It refers to the feature in Amazon Web Services (AWS) that enables users to connect to their EC2 instances using SSH through the AWS Management Console, without the need for a standalone SSH client. It allows you to use AWS Identity and Access Management (IAM) policies and users to control SSH access without needing to share or manage SSH keys. 

**Prerequisites for installing and using EC2 Instance Connect:**

*1. Install EC2 Instance Connect
2. Ensure network connectivity
3. Allow inbound SSH traffic
4. Grant permissions
5. Install an SSH client on your local computer
6. Meet username requirements*
    
## Method 2: SSH Client
Connecting to an instance through **SSH Client** involves using encryption and key-pair authentication when connectung to EC2 Linux instances. This method enables us to associate with **key pair**.


## Method 3: Remote Desktop Protocol (RDP)
**Remote Desktop Protocol (RDP)** enables multiple users to connect to a window instances. Users can have separate sessions on the same server, allowing them to run different applications, access different files, and have their own desktop environments without interfering with each other’s work.

**Prerequisite for Connecting Instance using RDP**

**Install an RDP client** - allows to connect to and interact with a remote Windows instance
