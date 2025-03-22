

---

# 🚀 SynLearn – Blockchain-Powered E-Learning Platform

**SynLearn** is a decentralized e-learning system that combines blockchain-based identity, certification, and quiz management with a React-powered user interface. The platform enables students to take quizzes, receive certifications, and securely store them on the blockchain, ensuring authenticity and immutability.

---

## 📌 Features

- 🎓 User Registration & Login (via Blockchain Smart Contracts)
- 🧠 Multiple Choice Quizzes (MCQs)
- 📄 Certificate Generation with Background Image
- 🧾 Certificate authenticity stored on blockchain
- ⚙️ Smart Contract integration using Truffle + Ganache
- 🌐 React.js Frontend
- 📦 Modular course support (`course_1_meta.js`, `course_1_qcm.js`)

---
## demo:
  
https://github.com/Ankush2201/CodeShasatra_Syndicate/assets/79956433/7a98a98e-08dd-4e87-bc07-b6583b68b0ec


## 🛠️ Tech Stack

- **Frontend**: React.js
- **Blockchain**: Solidity, Truffle
- **Smart Contracts**: Authentication, Course Certification
- **Certificate Generation**: HTML Canvas with background image
- **Local Blockchain**: Ganache (recommended for dev)

---

## 📂 Project Structure

```
SynLearn/
├── client/                   # React frontend
│   ├── public/               # Static assets (images, HTML, course data)
│   ├── src/                  # React source code
│   │   ├── App.js            # Main React component
│   │   ├── config.js         # Smart contract address config
│   │   └── contracts/        # Auto-generated smart contract ABIs
├── build/contract/           # Compiled contract ABIs (e.g. Authentication.json)
├── contracts/                # Solidity smart contracts (*.sol)
├── truffle-config.js         # Truffle setup
```

---

## ⚙️ How to Run Locally

### 📦 1. Install Dependencies

```bash
cd SynLearn
npm install -g truffle
cd client
npm install
```

### 🚀 2. Start Local Blockchain (Ganache Recommended)

Ensure Ganache is running.

### 📜 3. Compile & Deploy Contracts

```bash
cd ..
truffle migrate --reset
```

> This generates `Authentication.json` and `Courses.json` in `build/contract`.

### ⚙️ 4. Configure Contract Addresses

Copy the deployed contract addresses into:
```js
client/src/config.js
```

### 🌐 5. Start the React Frontend

```bash
cd client
npm start
```

Access the platform at: [http://localhost:3000](http://localhost:3000)

---

## 🔐 Smart Contracts Summary

### 🧾 `Authentication.sol`
- Registers new users (`signUp`)
- Stores user details: first name, family name, password (not secure), user type
- Tracks user count (`nbrUsers`)

---

## 🧑‍🏫 Course Content Format

Each course is defined in:
- `course_1_meta.js`: Course title, author, etc.
- `course_1_qcm.js`: Array of questions, answers, and correct choices

These files are placed under:
```
client/public/datas/course_1/
```

---

## 📜 Certificate Generation

When a quiz is completed:
- Certificate is dynamically generated using canvas
- Data includes course name, user name, date, etc.
- A hash or transaction may be used for validation

---

## 📊 UI/UX References

Included:
- `Certification.pptx`
- `Home Page.pptx`

These slide decks provide mockups or design guidance for building the platform interface.

---

## 📄 License

MIT License

---

## 💡 Future Improvements

- Password encryption (currently stored as plain text)
- NFT-based certificates for decentralized proof
- Course creator dashboard
- Admin user roles with special privileges
- Enhanced quiz options (timers, scoring, feedback)

---



