# Medical-Survey
The Medical Survey is a Power Platform application built with Power Apps, connected to a SharePoint list to streamline patient survey management and data collection.

This README provides an overview of the app’s features and functionality.
## Features
The Medical Survey App consists of multiple screens that provide a comprehensive survey management solution.

This demo version represents a simplified application, whereas the original solution is part of a broader system connecting multiple survey apps within a medical hospital.

With this app, users can:
✅ Add new surveys for patients
✅ Manage already completed surveys
✅ Prevent duplicate entries and redirect users to the editing section

#### 🟢 Loading Screen:
- Loads all essential app styles as global variables (OnVisible property).
- A timer ensures that all global variables are properly loaded before navigating to the Home Screen.

#### 🏠  Screen 1 'Home Screen':
- Central navigation panel → Allows users to select the survey type. In this demo, only the "Health Habits" survey is available.
- Left navigation panel → Navigate to "Complete Another Survey" (in the full version: access different applications and visits). Directly access "View and Edit Surveys" for managing existing surveys.
- Right panel → Displays real-time statistics: Number of registered patients (= Number of completed surveys).
#### 👤 Screen I Basic
- Users register a new patient by entering Patient Name and Patient ID (both required). If the Patient ID does not exist in SharePoint → The user can proceed. If the Patient ID already exists → The user cannot proceed and sees a message: "The survey for this patient has already been completed! Please go to the 'Review and Edit Surveys' tab."
- Upon clicking "→" (Next button):
- The Patient ID is stored as a global variable for use in the next screens.
- A progress indicator at the bottom shows how many steps remain.
#### 📋 Screen II and III 
- Various input methods:
✅ Text fields
✅ Radio buttons
✅ Dropdowns
✅ Combo boxes (for multiple selections)
- Top section displays the current patient ID (from the global variable).

#### ✅ Screen IV (Submit Survey)
- The user provides the final answers and clicks "Send the Answers".
What happens next?
1️⃣ The responses are saved to the SharePoint list.
2️⃣ All input fields are reset.
3️⃣ A confirmation message appears.
4️⃣ The user is redirected to the Home Screen.
If an error occurs, the app displays a message prompting the user to contact an administrator.
Progress indicator at the bottom shows survey completion status.
#### ❌ User Can Cancel the Survey at Any Step
- Clicking the "X" button redirects to a confirmation screen: "Returning to the main screen will result in data loss. Do you want to cancel the survey?"
- If the user chooses to cancel:
- The survey progress is reset.
- The patient is not added to the SharePoint list.
- The app navigates back to the Home Screen.
#### Screen Edit and View Surveys
- If a survey already exists for a patient, the user can edit the form here.
- Left panel (Gallery) → Displays all existing surveys with a search function (by Patient Name or ID).
- Right panel → Shows survey responses for the selected patient.
- Top section → Users can Edit, Submit changes, or Navigate to the Home Screen.
When a user submits an edit, the app updates the SharePoint list with:
✅ The edited answers
✅ The user’s credentials (who made the change)
✅ The modification date

### 🚀 Summary
The Medical Survey App streamlines patient survey management with:
✅ Easy patient registration
✅ Survey navigation with progress tracking
✅ Duplicate entry prevention
✅ Survey editing and history tracking

This demo provides a basic implementation, while the full version integrates with multiple survey applications for a hospital-wide solution.
