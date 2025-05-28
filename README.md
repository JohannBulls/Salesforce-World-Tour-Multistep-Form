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

#### Marketing Cloud

- Do you have Marketing Cloud?
  - If **yes**:
    - Do you feel you are getting the most out of Marketing Cloud?
    - Would you like a specialized team to advise you?
  - If **no**:
    - Do you plan to acquire Marketing Cloud?
      - Yes, right now
      - Yes, in a couple of months
      - Yes, maybe next year
      - No, not at the moment

#### Other Salesforce Clouds

- Do you have another Salesforce cloud?
  - If **yes**: A list of Salesforce clouds is displayed to select the ones the user has:
    - Sales Cloud
    - Service Cloud
    - Experience Cloud
    - Data Cloud
    - Marketing Cloud Account Engagement (Pardot)
    - Field Service
    - Digital Engagement
    - Salesforce Maps
    - Bots de Einstein

#### Services of Interest

- Multiple selection checkboxes including:
  - Salesforce Digital Marketing Agency Services
  - Marketing Cloud Implementation
  - Core Implementation (Sales/Service)
  - Digital Asset Management and Support
  - Advertising Studio Implementation
  - Commerce Cloud Implementation
  - Digital Engagement Implementation
  - Intelligence Advance Implementation
  - Marketing Cloud Account Engagement (Pardot) Implementation
  - Marketing Cloud Engagement Implementation
  - Marketing Cloud Intelligence Implementation
  - Sales Cloud Implementation
  - Service Cloud Implementation
  - Salesforce Training Services
  - Accompaniment / Support

#### Final

- Additional Comments (textarea)
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

## 🧾 Sample JSON Payload Sent to the API

When the form is successfully validated and submitted, it builds a JSON payload like the following:

```json
{
  "firstName": "Johann",
  "lastName": "Amaya",
  "email": "benditaessence@benditaess.com",
  "indicative": "+57",
  "mobilePhone": "3222799262",
  "title": "Vicepresidente",
  "company": "Bendita Essence",
  "industry": "Biotechnology",
  "numberOfEmployees": "51 - 100",
  "hasMarketingCloud": false,
  "getsAdvantageOfMC": null,
  "wantsSpecializedConsulting": null,
  "plansToAcquireMC": "Si, en un par de meses",
  "hasOtherSalesforceClouds": false,
  "otherSalesforceClouds": null,
  "interestedServices": "Servicios de agencia;Implementación marketing;Implementación core;Implementación Advertising Studio;Implementación Commerce Cloud",
  "description": "taastt",
  "utm_source": null,
  "utm_medium": null,
  "utm_campaign": null,
  "leadSource": "Eventos Salesforce Form",
  "campaignName": "Agentforce World Tour 2025 Bogotá"
}
```

This payload is sent to the Salesforce Apex REST API using an access token obtained via OAuth2 credentials.

## 📂 File Structure

```
world-tour-form/
├── bendita_WT.html      # Main multistep form
└── README.md            # This documentation
```

---

## 📌 Credits

Created by Johann Amaya at Bendita Essence for the Agentforce World Tour 2025.


---

## 📄 License

This project is licensed under the **MIT License**. See the LICENSE file for details.
