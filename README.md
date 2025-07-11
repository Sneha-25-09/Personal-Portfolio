# 💼 Portfolio Contact Form (with Google Sheets + Email Integration)

This project includes a functional contact form on a personal portfolio website. When a user submits the form:

- 📩 Their message is sent to your email (snehawilsonraj@gmail.com)
- 📊 The message is also saved in a connected Google Sheet

---

## ✨ Features

- Interactive contact form with validation
- Google Sheets backend for storing messages
- Email notifications using Google Apps Script
- Fully responsive and mobile-friendly design
- Uses Font Awesome icons and external resume link

---

## 🛠️ Technologies Used

- **HTML/CSS/JavaScript**
- **Font Awesome** (icons)
- **Google Apps Script**
- **Google Sheets** (as backend)
- **Fetch API** (for form submission)

---

## 🚀 Setup Instructions

### 1. 📋 Create a Google Sheet

- Add headers in the first row: `Timestamp`, `Name`, `Email`, `Message`.

### 2. ⚙️ Set up Google Apps Script

- Go to your Google Sheet → `Extensions > Apps Script`.
- Paste the following code:

```javascript
function doPost(e) {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();

  var name = e.parameter.Name;
  var email = e.parameter.Email;
  var message = e.parameter.Message;

  sheet.appendRow([new Date(), name, email, message]);

  MailApp.sendEmail({
    to: "snehawilsonraj@gmail.com",
    subject: "New Message from Portfolio Contact Form",
    htmlBody:
      "<b>Name:</b> " + name + "<br>" +
      "<b>Email:</b> " + email + "<br>" +
      "<b>Message:</b> " + message
  });

  return ContentService.createTextOutput("Success");
}
# 💼 Portfolio Contact Form (with Google Sheets + Email Integration)

This project includes a functional contact form on a personal portfolio website. When a user submits the form:

- 📩 Their message is sent to your email (snehawilsonraj@gmail.com)
- 📊 The message is also saved in a connected Google Sheet

---

## ✨ Features

- Interactive contact form with validation
- Google Sheets backend for storing messages
- Email notifications using Google Apps Script
- Fully responsive and mobile-friendly design
- Uses Font Awesome icons and external resume link

---

## 🛠️ Technologies Used

- **HTML/CSS/JavaScript**
- **Font Awesome** (icons)
- **Google Apps Script**
- **Google Sheets** (as backend)
- **Fetch API** (for form submission)

---

## 🚀 Setup Instructions

### 1. 📋 Create a Google Sheet

- Add headers in the first row: `Timestamp`, `Name`, `Email`, `Message`.

### 2. ⚙️ Set up Google Apps Script

- Go to your Google Sheet → `Extensions > Apps Script`.
- Paste the following code:

```javascript
function doPost(e) {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();

  var name = e.parameter.Name;
  var email = e.parameter.Email;
  var message = e.parameter.Message;

  sheet.appendRow([new Date(), name, email, message]);

  MailApp.sendEmail({
    to: "snehawilsonraj@gmail.com",
    subject: "New Message from Portfolio Contact Form",
    htmlBody:
      "<b>Name:</b> " + name + "<br>" +
      "<b>Email:</b> " + email + "<br>" +
      "<b>Message:</b> " + message
  });

  return ContentService.createTextOutput("Success");
}
