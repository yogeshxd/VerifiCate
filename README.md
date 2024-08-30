# VeriFicate

![GitHub](https://img.shields.io/github/last-commit/yogeshxd/VerifiCate)

## Introduction

This project provides a Blockchain based solution for generating and verifying digital certificates. The certificate information (uid, candidate_name, course_name, org_name, ipfs_hash) is stored on the blockchain. First, the certificate pdf is generated and stored onto IPFS using Pinata service. Then, the IPFS hash obtained is stored on the blockchain along with other information.

The system comprises of 2 main entities:
- **Institute**: Responsible for generating and issuing certificates. Has the functionality to generate and view certificates.

- **Verifier**: Responsible for verifying certificates. Has the functionality to verify certificates by either uploading a certificate pdf or by inputting the certificate id.

---
## Installation & Demo
[![VerifiCate](https://github.com/yogeshxd/VerifiCate/blob/main/image.png)](https://youtu.be/SMqs-b8zWM8?feature=shared)

## Features

- **Smart Contract:** Utilizes a Solidity smart contract to manage and store certificate details on the Ethereum blockchain.
- **IPFS Integration:** Stores certificate PDFs on IPFS via Pinata for decentralized and secure file storage.
- **Firebase Authentication:** Uses Firebase for authentication.
- **Streamlit App:** Provides a user-friendly interface for generating and verifying certificates.

---

## Getting Started

Clone the repository using the command:
```sh
git clone https://github.com/yogeshxd/VerifiCate
```

---

### Prerequisites

- **Node version >= 16.20.0**  
Truffle requires node version 16 or higher. The node version on my machine on which I tested this project was 16.20.0. You can try a lower node version (>=16.0).

- **Python version >= 3.9.10**  
    Python version 3.9.10 or higher is recommended but other versions may also work.

- **Globally installed packages for Truffle and Ganache-cli**  

    ```sh
    npm install -g truffle
    ```
    ```sh
    npm install -g ganache-cli
    ```

- **Python packages**  
    In the project's root directory, exececute the command:
    ```sh
    pip install -r application/requirements.txt
    ```
    It is recommended to create a virtual environment and then install the requirements and run the streamlit application in that virtual environment.

- **Firebase project setup**  
    Create a project on [Firebase Console](https://console.firebase.google.com/). This will be used to setup an authentication service in the project. Enable email/password sign in method under Authentication in the Build section.
    Go to project settings. Add new app. Note the following details in a .env file inside the project's root directory.
    ```sh
    FIREBASE_API_KEY
    FIREBASE_AUTH_DOMAIN
    FIREBASE_DATABASE_URL (Set this to "")
    FIREBASE_PROJECT_ID
    FIREBASE_STORAGE_BUCKET
    FIREBASE_MESSAGING_SENDER_ID
    FIREBASE_APP_ID
    ```

- **Pinata account setup**  
    Create an account on [Pinata](https://app.pinata.cloud/). Go to the API keys section and generate a new key. Note the API key and secret key in .env file.

- **.env file**  
    Finally your .env file should contain the following things:

    ```sh
    PINATA_API_KEY = "<Your Pinata API key>"
    PINATA_API_SECRET = "<Your Pinata Secret Key>"
    FIREBASE_API_KEY = "<Your Firebase API key>"
    FIREBASE_AUTH_DOMAIN = "<Your Firebase auth domain>"
    FIREBASE_DATABASE_URL = ""
    FIREBASE_PROJECT_ID = "<Your Firebase project id>"
    FIREBASE_STORAGE_BUCKET = "<Your Firebase Storage Bucket>"
    FIREBASE_MESSAGING_SENDER_ID = "<Your Firebase messaging sender id>"
    FIREBASE_APP_ID = "<Your Firebase app id>"
    institute_email = "institute@gmail.com" # Feel free to modify this
    institute_password = "123456" # Feel free to modify this
    ```
    Note: This institute email and password in the .env file will be used to login as Institute inside the app.

### Running the project

1. Open a terminal anywhere and start the Ganache blockchain.
    ```
    ganache-cli -h 127.0.0.1 -p 8545
    ```

2. Open a new terminal in the project's root directory and execute the following command to compile and deploy the smart contracts.
    ```sh
    truffle migrate
    ```

3. Change the working directory to application directory inside the project's root directory.
    ```sh
    cd application
    ```

4. Launch the streamlit app.
    ```sh
    streamlit run app.py
    ```

5. You can now view the app on your browser running on [localhost:8501](https:localhost:8501).

6. To stop the application, press Ctrl+C.

---

## License

This project is licensed under the MIT license. See the [LICENSE](https://github.com/yogeshxd/VerifiCate/blob/main/LICENSE) file for more details.

---
