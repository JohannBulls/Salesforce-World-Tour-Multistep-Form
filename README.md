# Salesforce World Tour Multistep Form

This project is a responsive, multistep HTML form built for the Salesforce World Tour event. It is designed to collect lead information, validate inputs (including corporate email and phone numbers), manage visibility of conditional questions, and submit the data to a Salesforce Apex REST API.

## 🚀 Technologies Used

- **HTML5**
- **Bootstrap 5.3.3**
- **JavaScript (Vanilla)**
- **intl-tel-input 18.1.1**
- **Google reCAPTCHA**
- **Salesforce Apex REST API**

## 📦 Features

- Multistep user flow (3 steps)
- Responsive design with Bootstrap
- International phone validation
- Corporate email validation (blocks personal domains)
- Conditional questions based on user responses
- Dynamic checkbox generation for services and cloud options
- Google reCAPTCHA integration
- Real-time validation feedback
- Form data submission with Salesforce token authentication

---

## 🧭 How to Use

### 1. Clone the Repository

```bash
git clone https://github.com/JohannBulls/Salesforce-World-Tour-Multistep-Form.git
cd world-tour-form
```

### 2. Open the HTML File

You can open `bendita_WT.html` directly in your browser:

```bash
open bendita_WT.html
```

> Make sure you have internet access to load CDN assets like Bootstrap and intl-tel-input.

---

## 🧪 Form Flow

### Step 1: Basic Information

- First Name
- Last Name
- Email (must be a corporate email)
- Mobile Phone (with country code validation)

### Step 2: Company Information

- Company name
- Industry (select from list)
- Job Title
- Number of Employees

### Step 3: Salesforce Usage

- Do you have Marketing Cloud?
  - If **yes**: Questions about its use and need for consulting
  - If **no**: Ask if you plan to acquire it
- Do you use other Salesforce Clouds?
  - If **yes**: Show checkbox list to select them
- Services of interest (multiple selections)
- Additional Comments
- Google reCAPTCHA

---

## 🛡️ Validation & Security

- Phone input validated using `intl-tel-input`
- reCAPTCHA to avoid spam submissions
- Personal email domains (like Gmail, Yahoo) are blocked
- Conditional required fields
- Full client-side form validation before submission

---

## 🔐 Salesforce Integration

This form includes **Salesforce OAuth token request** and submits payload via `fetch` to a custom Apex REST API.

> ⚠️ **Important:** Hardcoded credentials (client ID, secret, username, password+token) are included in this example **for demo purposes only**. Never expose these in production. Use a server-side proxy or secure integration instead.

---

## 📂 File Structure

```
world-tour-form/
├── bendita_WT.html      # Main multistep form
└── README.md            # This documentation
```

---

## 📌 Credits

Created by Johann Amaya at Bendita ESS for the Agentforce World Tour 2025.

---

## 🧼 TODO

- [ ] Move Salesforce credentials to a secure backend service
- [ ] Add multilingual support (ES/EN)
- [ ] Log analytics events on each step

---

## 📄 License

This project is licensed under the **MIT License**. See the LICENSE file for details.
