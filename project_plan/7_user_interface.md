## 🎨 7. User Interface & Widgets Specification

These standard Lego block widget configurations are saved inside the agent package.

### Widget 1: `org_details_form`
*   **Type:** `form`
*   **Theme Token Default:** `indigo`
*   **Layout JSON Structure:**
```json
// app/ui/widgets/org_details_form.json
{
  "type": "container",
  "props": {
    "className": "flex flex-col gap-4 p-4 bg-white rounded-lg shadow-md border border-indigo-100"
  },
  "children": [
    {
      "type": "input",
      "props": {
        "name": "org_name",
        "label": "Organization Legal Name",
        "placeholder": "Apex Innovations",
        "inputType": "text",
        "required": true
      }
    },
    {
      "type": "input",
      "props": {
        "name": "org_description",
        "label": "Brief Description",
        "placeholder": "Robotic research and development",
        "inputType": "text",
        "multiline": true,
        "required": true
      }
    },
    {
      "type": "input",
      "props": {
        "name": "org_email",
        "label": "Organization Email",
        "placeholder": "info@apex.com",
        "inputType": "text",
        "required": true
      }
    },
    {
      "type": "input",
      "props": {
        "name": "org_phone",
        "label": "Organization Phone",
        "placeholder": "555-0199",
        "inputType": "text",
        "required": true
      }
    },
    {
      "type": "select",
      "props": {
        "name": "user_position",
        "label": "Your Position/Title in Organization",
        "options": [
          {"label": "President", "value": "President"},
          {"label": "CEO", "value": "CEO"},
          {"label": "CFO", "value": "CFO"},
          {"label": "IT Manager", "value": "IT Manager"}
        ],
        "required": true
      }
    },
    {
      "type": "button",
      "props": {
        "label": "Submit Details",
        "actionUrl": "agent://submit_org_details",
        "styling": {
          "colorTheme": "indigo"
        }
      }
    }
  ]
}
```

---

### Widget 2: `mobile_input_widget`
*   **Type:** `form`
*   **Theme Token Default:** `slate`
*   **Layout JSON Structure:**
```json
// app/ui/widgets/mobile_input_widget.json
{
  "type": "container",
  "props": {
    "className": "flex flex-col gap-2 p-4 bg-white rounded-lg border border-slate-200"
  },
  "children": [
    {
      "type": "input",
      "props": {
        "name": "mobile_number",
        "label": "Personal Contact Mobile Number",
        "placeholder": "555-0199",
        "inputType": "text",
        "required": true
      }
    },
    {
      "type": "button",
      "props": {
        "label": "Check Account",
        "actionUrl": "agent://submit_mobile",
        "styling": {
          "colorTheme": "slate"
        }
      }
    }
  ]
}
```

---

### Widget 3: `otp_verify_widget`
*   **Type:** `form`
*   **Theme Token Default:** `blue`
*   **Layout JSON Structure:**
```json
// app/ui/widgets/otp_verify_widget.json
{
  "type": "container",
  "props": {
    "className": "flex flex-col gap-2 p-4 bg-white rounded-lg border border-blue-200"
  },
  "children": [
    {
      "type": "input",
      "props": {
        "name": "otp_code",
        "label": "Enter 6-digit Verification Code",
        "placeholder": "123456",
        "inputType": "text",
        "required": true
      }
    },
    {
      "type": "button",
      "props": {
        "label": "Verify OTP",
        "actionUrl": "agent://submit_otp",
        "styling": {
          "colorTheme": "blue"
        }
      }
    }
  ]
}
```

---

### Widget 4: `personal_details_widget`
*   **Type:** `form`
*   **Theme Token Default:** `pink`
*   **Layout JSON Structure:**
```json
// app/ui/widgets/personal_details_widget.json
{
  "type": "container",
  "props": {
    "className": "flex flex-col gap-4 p-4 bg-white rounded-lg border border-pink-100"
  },
  "children": [
    {
      "type": "input",
      "props": {
        "name": "full_name",
        "label": "Contact Person Full Name",
        "placeholder": "Alex Doe",
        "inputType": "text",
        "required": true
      }
    },
    {
      "type": "input",
      "props": {
        "name": "email_address",
        "label": "Contact Email Address",
        "placeholder": "alex@apex.com",
        "inputType": "text",
        "required": true
      }
    },
    {
      "type": "button",
      "props": {
        "label": "Submit Contact Details",
        "actionUrl": "agent://submit_personal",
        "styling": {
          "colorTheme": "pink"
        }
      }
    }
  ]
}
```

---

### Widget 5: `org_summary_card`
*   **Type:** `detail-card`
*   **Theme Token Default:** `green`
*   **Layout JSON Structure:**
```json
// app/ui/widgets/org_summary_card.json
{
  "type": "container",
  "props": {
    "className": "p-4 bg-green-50 rounded-lg border border-green-200 flex flex-col gap-3"
  },
  "children": [
    {
      "type": "text",
      "props": {
        "text": "Organization Summary Card",
        "className": "text-lg font-bold text-green-800"
      }
    },
    {
      "type": "container",
      "props": {
        "className": "grid grid-cols-2 gap-x-4 gap-y-2"
      },
      "children": [
        {
          "type": "container",
          "props": { "className": "flex flex-col" },
          "children": [
            { "type": "text", "props": { "text": "Legal Name", "className": "text-xs text-slate-500 font-medium" } },
            { "type": "text", "props": { "text": "{{summary_name}}", "className": "text-sm text-slate-800 font-semibold" } }
          ]
        },
        {
          "type": "container",
          "props": { "className": "flex flex-col" },
          "children": [
            { "type": "text", "props": { "text": "Description", "className": "text-xs text-slate-500 font-medium" } },
            { "type": "text", "props": { "text": "{{summary_description}}", "className": "text-sm text-slate-800 font-semibold" } }
          ]
        },
        {
          "type": "container",
          "props": { "className": "flex flex-col" },
          "children": [
            { "type": "text", "props": { "text": "Org Email", "className": "text-xs text-slate-500 font-medium" } },
            { "type": "text", "props": { "text": "{{summary_email}}", "className": "text-sm text-slate-800 font-semibold" } }
          ]
        },
        {
          "type": "container",
          "props": { "className": "flex flex-col" },
          "children": [
            { "type": "text", "props": { "text": "Org Phone", "className": "text-xs text-slate-500 font-medium" } },
            { "type": "text", "props": { "text": "{{summary_phone}}", "className": "text-sm text-slate-800 font-semibold" } }
          ]
        }
      ]
    }
  ]
}
```
