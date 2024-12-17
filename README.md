# Resource Calendar Access Manager

A Google Apps Script solution specifically designed to manage access permissions for **Google Resource Calendars** (such as meeting rooms, equipment, or other bookable resources) through a Google Spreadsheet interface.

## ⚠️ Important Note

This script is specifically designed for **Resource Calendars** only. It will not work with:
- Personal Google Calendars
- Regular shared calendars
- User calendars

To use this script, you must have Resource Calendars set up in your Google Workspace environment. These are typically:
- Conference rooms
- Meeting spaces
- Equipment calendars
- Other bookable resources

## 🌟 Features

- Bulk add users to multiple resource calendars with specified access roles
- Bulk remove users from resource calendars
- User-friendly interface with custom menu
- Real-time status updates
- Progress tracking
- Error handling and reporting

## 📋 Prerequisites

1. Google Workspace account (formerly G Suite) with admin access
2. Properly configured Resource Calendars in Google Workspace
3. Access to Google Calendar and Google Sheets
4. Appropriate permissions to modify resource calendar access settings

## 🚀 Installation

1. Create a new Google Spreadsheet
2. Go to Extensions > Apps Script
3. Copy and paste the provided script code into the Apps Script editor
4. Enable required Google Services:
   - Click on the '+' next to 'Services' in the left sidebar
   - Add the following services:
     - **Calendar API** (Required for calendar operations)
     - **Admin Directory API** (Required for resource management)
   - Click 'Add' for each service
5. Save the project
6. Refresh your spreadsheet - you should see a new menu item "📅 Calendar Access"

## 🔐 Required Google Services

This script requires the following Google Services to be enabled in the Apps Script project:

1. **Calendar API**
   - Used for managing calendar access and permissions
   - Handles all calendar-related operations

2. **Admin Directory API**
   - Used for resource calendar management
   - Required for proper resource identification and access

If these services are not enabled, the script will not function properly and may return errors.

## 📝 Spreadsheet Setup

### Required Columns
- **Column A**: Resource Calendar IDs
- **Column B**: Email Addresses
- **Column C**: Roles (for adding users only)
- **Column D**: Status Updates (automatically populated)

### Header Row
The first row should contain headers:
- A1: "Calendar ID"
- B1: "Email"
- C1: "Role"
- D1: "Status"

## 🎯 Available Roles

- `reader`: Can view resource calendar details
- `freeBusyReader`: Can only see free/busy status
- `writer`: Can modify resource calendar events
- `owner`: Full access to resource calendar settings

## 🔧 Usage

1. Fill in the spreadsheet with your data:
   - Column A: Enter the Resource Calendar IDs
   - Column B: Enter user email addresses
   - Column C: Enter desired roles (for adding users)

2. Use the "📅 Calendar Access" menu to:
   - 🔑 Add Users to Calendars
   - 🗑️ Remove Users from Calendars
   - ℹ️ Show Instructions

3. Monitor the status updates in Column D

## 📍 Finding Resource Calendar IDs

1. Open Google Calendar
2. Go to your resource calendar settings
3. Scroll down to "Integrate calendar"
4. Look for "Calendar ID" - it should be in the format: 
   `your-organization.com_XXXXXXXXXXXXXXXXXXXXXXXX@resource.calendar.google.com`

## ⚠️ Important Notes

- The script ONLY works with Resource Calendars
- The script processes each email address with each resource calendar ID
- Empty rows are automatically skipped
- Status updates appear in real-time in Column D
- The script includes automatic retry logic for different calendar types
- Rate limiting is implemented to prevent API quota issues

## 🔍 Error Handling

- The script validates inputs before processing
- Errors are clearly displayed in Column D with red background
- Successful operations are marked with green background
- Informational messages use a neutral background

## 🔒 Security Notes

- This script requires authorization to:
  - Access and modify Google Calendar resources
  - Access and modify Google Sheets
  - Access Admin Directory API
- No sensitive information is stored in the script
- Authorization is handled through Google's OAuth2 system
- Users must have appropriate Google Workspace permissions to use this script
- Email notifications for calendar changes are disabled by default


## 🤝 Contributing

Feel free to submit issues and enhancement requests!

## 🙏 Acknowledgments

- Google Apps Script documentation
- Google Calendar API
