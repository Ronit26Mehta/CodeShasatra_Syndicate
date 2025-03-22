

---

# 🚀 SynLearn – Blockchain-Powered E-Learning Platform

**SynLearn** is a next-generation, decentralized e-learning platform designed to revolutionize online learning. By integrating blockchain technology, SynLearn ensures secure identity management, tamper-proof certification, and reliable quiz assessments—all through a modern, React-powered interface.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Demo](#demo)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Project Structure](#project-structure)
- [Installation & Setup](#installation--setup)
- [Smart Contracts](#smart-contracts)
- [Course Content Format](#course-content-format)
- [Certificate Generation](#certificate-generation)
- [UI/UX References](#uiux-references)
- [License](#license)
- [Contributing](#contributing)
- [Future Improvements](#future-improvements)
- [Acknowledgments](#acknowledgments)

---

## Overview

SynLearn is built to bridge the gap between traditional e-learning and modern decentralized systems. By leveraging blockchain, it not only provides an intuitive and engaging user interface but also guarantees that every certificate and user credential is securely stored and verifiable. Whether you're a student eager to learn or an educator focused on delivering quality content, SynLearn offers a transparent, secure, and flexible platform.

---



## Features

- **Decentralized Authentication**: Secure user registration and login powered by blockchain smart contracts.
- **Interactive Quizzes**: Dynamic multiple-choice quizzes (MCQs) that provide immediate feedback.
- **Dynamic Certificate Generation**: Real-time certificate creation using HTML Canvas with a customizable background image.
- **Blockchain Verification**: Certificates and user data are recorded on the blockchain for immutability and transparency.
- **Modular Course Support**: Courses are defined in separate metadata and quiz files (`course_1_meta.js` and `course_1_qcm.js`), enabling easy updates and scalability.
- **Smart Contract Integration**: Seamless connection between the React frontend and smart contracts deployed using Truffle and Ganache.

---

## Demo

Experience SynLearn in action by viewing our demo video:

[Demo on GitHub](https://github.com/Ankush2201/CodeShasatra_Syndicate/assets/79956433/7a98a98e-08dd-4e87-bc07-b6583b68b0ec)

---
## system design  : 
  1. workflow:
     
  ![image](https://github.com/user-attachments/assets/540ad7bf-b8e5-4f24-8af7-428ac1e64194)
  
  2. components  design:

   ![image](https://github.com/user-attachments/assets/550ff561-1d67-4f38-9687-354e4a75ee56)

 3. activity diagram:

  ![image](https://github.com/user-attachments/assets/697d7a79-372d-4f21-9962-42f4426f1e90)

4. depolyement diagram:

 ![image](https://github.com/user-attachments/assets/0cd06a9f-ea38-4ceb-834f-88104f15b81c)

 
    

 
## Tech Stack

- **Frontend**: 
  - **React.js**: For building a dynamic and responsive user interface.
- **Blockchain**:
  - **Solidity**: The language used to write secure smart contracts.
  - **Truffle**: A development framework for testing and deploying smart contracts.
  - **Ganache**: A personal Ethereum blockchain used for local development and testing.
- **Smart Contracts**: 
  - **Authentication**: Handles user registration, login, and data storage.
  - **Course Certification**: Manages course completion records and certificate issuance.
- **Certificate Generation**:
  - **HTML Canvas**: Dynamically generates certificates with personalized user data and course details.

---

## Architecture

SynLearn's architecture is modular and comprises several key components:

- **Frontend (React.js)**: The user interface is crafted using React, managing the user experience, state, and interactions.
- **Smart Contracts (Solidity)**: Core business logic and data persistence are managed by smart contracts ensuring that all actions (e.g., user registration, certificate issuance) are immutable.
- **Blockchain (Ganache/Ethereum)**: Deployed smart contracts operate on a blockchain network, ensuring decentralized data storage.
- **Certificate Generation (HTML Canvas)**: Utilizes HTML Canvas to create visually appealing, dynamic certificates that reflect course completions.

---

## Project Structure

The project is organized as follows:

```
SynLearn/
├── client/                   # React frontend
│   ├── public/               # Static assets (images, HTML, course data)
│   ├── src/                  # React source code
│   │   ├── App.js            # Main React component
│   │   ├── config.js         # Configuration file for smart contract addresses
│   │   └── contracts/        # Auto-generated smart contract ABIs
├── build/contract/           # Compiled contract ABIs (e.g., Authentication.json)
├── contracts/                # Solidity smart contracts (*.sol)
├── truffle-config.js         # Truffle configuration for deployment
```

Each folder is purposefully structured to separate the frontend logic, blockchain contracts, and compiled artifacts, making the project easier to navigate and maintain.

---

## Installation & Setup

### Prerequisites

- **Node.js** and **npm**: Ensure you have Node.js installed.
- **Truffle**: Install globally using npm.
- **Ganache**: A local blockchain emulator for Ethereum development.

### Step-by-Step Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/Ankush2201/CodeShasatra_Syndicate.git
   cd SynLearn
   ```

2. **Install Global Dependencies**

   ```bash
   npm install -g truffle
   ```

3. **Install Client Dependencies**

   ```bash
   cd client
   npm install
   ```

4. **Start Local Blockchain**

   Launch Ganache (or your preferred local blockchain) to simulate the blockchain network.

5. **Compile and Deploy Smart Contracts**

   From the project root, execute:
   
   ```bash
   cd ..
   truffle migrate --reset
   ```

   This step compiles the Solidity contracts and deploys them, generating artifacts in the `build/contract` directory.

6. **Configure Contract Addresses**

   Update `client/src/config.js` with the addresses of the deployed contracts.

7. **Run the React Application**

   Start the client application:
   
   ```bash
   cd client
   npm start
   ```

   Open your browser at [http://localhost:3000](http://localhost:3000) to access the platform.

---

## Smart Contracts

### Authentication.sol

- **Purpose**: Manages user registrations and logins.
- **Key Functions**:
  - `signUp`: Registers new users by storing personal details (first name, family name, password, and user type).
  - `nbrUsers`: Tracks the total number of registered users.

### Courses.sol (Course Certification)

- **Purpose**: Records course completions and certificate issuance.
- **Key Functions**:
  - Stores course completion data on the blockchain.
  - Generates a unique certificate record, ensuring that every issued certificate is verifiable.

The smart contracts ensure that all critical user interactions and course records are secure and immutable.

---

## Course Content Format

Courses in SynLearn are structured to allow easy scalability and modular updates:

- **course_1_meta.js**: Contains essential course metadata including title, author, description, and other related details.
- **course_1_qcm.js**: An array of quiz questions, each with multiple-choice answers and an indicator for the correct answer.

These files reside in:

```
client/public/datas/course_1/
```

This structure supports the addition of new courses without impacting the core functionality of the platform.

---

## Certificate Generation

Certificate generation in SynLearn is dynamic and visually appealing:

- **HTML Canvas**: Utilizes the HTML Canvas API to create certificates on-the-fly.
- **Customizable Templates**: Certificates include a background image, course name, user details, and date.
- **Blockchain Integration**: Each certificate can be associated with a unique hash or transaction ID, ensuring it can be validated against blockchain records.

This process guarantees that every certificate is both unique and verifiable.

---

## UI/UX References

The design of SynLearn is supported by detailed mockups and design references:

- **Certification.pptx**: Contains visual mockups for the certificate generation process.
- **Home Page.pptx**: Provides design guidelines for the homepage and overall user experience.

These assets ensure that the platform remains user-friendly and aesthetically consistent.

---

## License

This project is licensed under the MIT License. For more details, please see the [LICENSE](LICENSE) file.

---

## Contributing

We welcome contributions from developers and the community! To contribute:

1. **Fork the Repository**: Create your own copy of the project.
2. **Create a New Branch**: Develop your feature or bug fix on a new branch.
3. **Commit Your Changes**: Write clear, concise commit messages.
4. **Open a Pull Request**: Describe your changes and submit a pull request for review.

For additional guidelines, please refer to our [CONTRIBUTING.md](CONTRIBUTING.md).

---

## Future Improvements

- **Enhanced Security**: Implement password encryption and other security measures to protect user data.
- **NFT-Based Certificates**: Transition to using non-fungible tokens (NFTs) for a more robust certificate validation system.
- **Course Creator Dashboard**: Develop a dashboard for educators to create, manage, and monitor courses.
- **Admin Roles**: Introduce administrator functionalities for managing users and overseeing content.
- **Advanced Quiz Features**: Add features like timed quizzes, advanced scoring systems, and detailed feedback to enhance the learning experience.

---

## Acknowledgments

Special thanks to all contributors and the open-source communities behind Ethereum, Solidity, React, Truffle, and Ganache. Your continued support and innovation drive this project forward.


