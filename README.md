# 🔐 Password Authentication System

A simple **command-line password authentication system built with Python**.

This project demonstrates basic concepts of **user registration, password hashing, password strength checking, and login authentication**. Instead of storing passwords directly, the program stores their **SHA-256 hash values**.

---

## ✨ Features

* 👤 User registration
* 🔑 Password hashing using SHA-256
* 🔐 Login authentication
* 💪 Password strength checking
* 📝 Username and password validation
* 🖥️ Simple command-line interface
* 🚪 Exit option

---

## 🛠️ Technologies Used

* **Python 3**
* **hashlib** — for SHA-256 password hashing

The project does not require any external Python packages.

---

## 📁 Project Structure

Password-Authentication/
│
├── main.py
└── README.md
```

---

## ⚙️ Requirements

Make sure **Python 3** is installed.

Check your Python version:

```bash
python --version
```

or:

```bash
python3 --version
```

No additional packages are required because `hashlib` is included with Python.

---

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone https://github.com/namankarna0/Password-Authentication.git
```

### 2. Enter the project directory

```bash
cd Password-Authentication
```

### 3. Run the program

```bash
python main.py
```

On some Linux systems:

```bash
python3 main.py
```

---

## 🖥️ Menu

When the program starts, it displays:

```text
1.Register
2.Login
3.Check Password Strength
4.Exit

Enter your choice:
```

### 1️⃣ Register

Allows a new user to create an account.

Example:

```text
Enter username: naman
Enter password: Password@123

Password Strength: Strong Password
User Registration successful!
```

The password is converted into a SHA-256 hash before being stored.

---

### 2️⃣ Login

Allows a registered user to authenticate.

Example:

```text
Enter username: naman
Enter password: Password@123

Login successful!
```

If the credentials are incorrect:

```text
Invalid username or password.
```

---

### 3️⃣ Check Password Strength

Allows the user to check the strength of a password without registering.

The program checks whether the password contains:

* At least 8 characters
* A number
* An uppercase letter
* A special character

---

## 💪 Password Strength

The program assigns points based on four conditions.

| Requirement                  | Point |
| ---------------------------- | ----: |
| At least 8 characters        |    +1 |
| Contains a digit             |    +1 |
| Contains an uppercase letter |    +1 |
| Contains a special character |    +1 |

### Strength Levels

| Score | Result               |
| ----: | -------------------- |
|     4 | 💪 Strong Password   |
|     3 | 🟡 Moderate Password |
|   0–2 | 🔴 Weak Password     |

### Example

```text
Password: Password@123
```

It satisfies all four requirements:

```text
✓ 8+ characters
✓ Contains numbers
✓ Contains uppercase letter
✓ Contains special character

Password Strength: Strong Password
```

---

## 🔐 Password Hashing

The project uses Python's built-in `hashlib` module to generate a **SHA-256 hash**:

```python
def hash_password(password):
    return hashlib.sha256(password.encode()).hexdigest()
```

For example, instead of storing:

```text
Password@123
```

the program stores a SHA-256 hash.

During login, the entered password is hashed again and compared with the stored hash.

```text
Entered Password
       ↓
   SHA-256 Hash
       ↓
Compare with Stored Hash
       ↓
 ┌─────┴─────┐
Match      No Match
 ↓             ↓
Login       Invalid
Success     Credentials
```

---

## 🧠 Concepts Demonstrated

This project helps demonstrate several important Python and cybersecurity concepts:

* Python functions
* Dictionaries
* User input
* Conditional statements
* Loops
* String manipulation
* List/character checking
* Password validation
* Cryptographic hashing
* Authentication logic
* SHA-256
* Basic cybersecurity practices

---

## ⚠️ Security Note

This project is intended for **learning purposes** and should not be used as a production authentication system.

Although SHA-256 is a secure cryptographic hash function, **plain SHA-256 is not recommended for storing real user passwords**. Production applications should use password-specific hashing algorithms such as **Argon2, bcrypt, or scrypt**, together with unique salts and appropriate security controls.

Also, the current program stores users only in memory:

```python
users = {}
```

Therefore, all registered users are lost when the program exits.

---

## 🔮 Future Improvements

Possible improvements include:

* 💾 Store users in a database
* 🔐 Use Argon2/bcrypt/scrypt for password storage
* 🧂 Add unique password salts
* 👤 Prevent duplicate usernames
* 🔄 Add password reset functionality
* 🔒 Hide password input using `getpass`
* 🚫 Add login attempt limits
* 📊 Add stronger password rules
* 🗃️ Store authentication data securely
* 📝 Add logging
* 🖥️ Create a graphical user interface

---

## 📸 Example

```text
================================
      PASSWORD AUTHENTICATION
================================

1.Register
2.Login
3.Check Password Strength
4.Exit

Enter your choice: 1

Enter username: user123
Enter password: Hello@123

Password Strength: Strong Password
User Registration successful!
```

---

## 👨‍💻 Author

**Naman Karna**

A beginner-friendly Python project created to practice **authentication, password hashing, and cybersecurity concepts**.

---

## 📄 License

This project is intended for **educational and personal use**.
