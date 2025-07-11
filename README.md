
---

## 🧩 Technologies Used

- HTML5 + CSS3 (grid layout, styling)
- Vanilla JavaScript (for form submission)
- Google Apps Script (UI handling + data processing)
- Google Sheets (as the data store)

---

## 🧠 How It Works

### 1. `onOpen()`  
Automatically adds a **custom menu** item called `Register Complain` with a sub-option `Entry Form` when the spreadsheet is opened.

### 2. `showForm()`  
Loads and displays the `BookingForm.html` in a modal dialog sized at 1500x650 pixels.

### 3. `submitForm(data)`  
Receives submitted form data from the front-end and inserts it into the first available empty row in the `Data_Base` sheet.

If no empty row is found, it appends the data to the next row after the last entry.

### 4. `BookingForm.html`  
Styled two-column form with fields such as:

- 📞 Customer Info: Name, Mobile, Alternate Mobile, Address, City, State
- 🏪 Dealer & Distributor Info: Name, Contact Number
- ⚙️ Appliance Details: Model, Brand, Category, Capacity, Serial No.
- 📅 Invoice Info: Invoice Date, Call Type, Remarks, Charges
- 📝 Remarks & Service Category

All fields are captured and passed as a JavaScript object using `google.script.run.submitForm(formData);`.

---

## 📋 Example Use Case

1. User opens Google Sheet.
2. Clicks `Register Complain` → `Entry Form`
3. Fills out the form and clicks **Submit Booking**
4. Data is logged into the `Data_Base` sheet like this:

| Timestamp | Name | Mobile | Alt Mobile | Pincode | City | ... |
|-----------|------|--------|------------|---------|------|-----|
| `2025-07-11 14:35` | John | 9876543210 | ... | ... | ... | ... |

---

## 📎 Requirements

- Google Account
- Google Sheet with a sheet named `Data_Base`
- Google Apps Script project with:
  - `BookingForm.html`
  - `Code.gs`

---

## 🚀 Setup Instructions

1. Open your Google Sheet.
2. Go to **Extensions → Apps Script**.
3. Add the `BookingForm.html` and `Code.gs` files.
4. Save and reload the sheet.
5. Use the **Register Complain → Entry Form** menu to open the form.

---

## 💡 Customization Tips

- Add email confirmation with `MailApp.sendEmail()`
- Add validations in `submitForm()` for duplicate phone numbers
- Log submissions in a different sheet (e.g., `Log_Sheet`)
- Trigger follow-ups or reminders using `Triggers`

---

## 🔒 Data Security

- Data is saved securely in the Google Sheet.
- No external APIs or servers used.
- You control access via Google Sheet sharing permissions.

---

## 📞 Contact

**Developer:** Satanand
**Email:** satanand74@gmail.com
Feel free to reach out for improvements, suggestions, or collaborations.

## 🔗 Some Usefull links
- BookingForm.html
- CRM.xlsx
- Code.gs (https://github.com/Satanand-Ken/GsheetCRM/blob/main/Code.gs)
