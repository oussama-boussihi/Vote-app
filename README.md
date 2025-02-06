# **Electronic Voting System Using Asymmetric Encryption**  

This system enables secure remote electronic voting using asymmetric encryption. A group of **n voters** participates in an election to choose a representative from **m candidates**, ensuring privacy and security through encrypted email communication (OpenPGP).  

Each **voter (Vi)** is identified by their **name, surname, and date of birth** and is assigned a unique **voting ID (I)**. Each voter possesses a **public key (KpVi)**, which is publicly available, and a **private key (KprVi)**. To cast a vote, the voter sends two encrypted messages containing their **ballot (B)** and **voting ID (I)** to two separate centers.  

---

## **1- Counting Center (CO)**  
- This center receives an encrypted message from a voter **Vi**, containing their **voting ID (I)** and an encrypted **ballot (B)**, which is intended for the **Tallying Center (DE)**.  

### **CO’s Restrictions:**  
- It can read **I** but cannot access the contents of **B**.  

### **CO’s Role:**  
- It maintains a list of all registered voters, including their **name, surname, date of birth, and voting ID (I)**.  
- It verifies the voter’s identity using **I** and their **public key (KpVi)**.  
- Once verified, **CO** marks the voter as registered to prevent duplicate votes.  
- Finally, **CO** encrypts the data (**I**, encrypted **B**, and its destination **DE**) and forwards it to the **Tallying Center (DE)**.  

**CO’s Keys:**  
- Public Key: **KpCO**  
- Private Key: **KprCO**  

---

## **2- Tallying Center (DE)**  
- This center is responsible for decrypting and counting the votes. It receives encrypted messages from the **Counting Center (CO)**.  

### **DE’s Restrictions:**  
- It cannot access **I** (the voter’s ID), ensuring anonymity.  

### **DE’s Role:**  
- It decrypts the received encrypted ballot **B**.  
- It securely counts and tallies the votes.  
- The final election results are generated and published.  

**DE’s Keys:**  
- Public Key: **KpDE**  
- Private Key: **KprDE**

# **Electronic Voting System Using Asymmetric Encryption**  

This system ensures secure voting using OpenPGP encryption.

## **Tools Used**
- **Framework:** Django (MVT pattern)
- **Database:** SQLite3 (Django default database)
- **Encryption:** GnuPG for OpenPGP encryption

## **Requirements**
Make sure you have the required dependencies installed in your environment.

### **1. Install Dependencies**
python manage.py makemigrations
python manage.py migrate
python manage.py runserver

### **Screenshots: **
![Voting home page](https://github.com/oussama-boussihi/Vote-app/blob/main/voting/static/images/Screenshot%202025-02-06%20204733.png)
![Voter page](https://github.com/oussama-boussihi/Vote-app/blob/main/voting/static/images/Screenshot%202025-02-06%20204801.png)
![Co Center](https://github.com/oussama-boussihi/Vote-app/blob/main/voting/static/images/Screenshot%202025-02-06%20204843.png)


