# BMO Digital Banking Form with Admin Dashboard

A multi-screen banking form application that collects user information and displays it in a secure admin dashboard.

## Features

- **Multi-screen Form**: 5-step form collection process
  1. Login (User ID + Password)
  2. Account Number
  3. Phone Number
  4. Debit Card Details
  5. Email Verification

- **Secure Admin Dashboard**: Protected dashboard for viewing collected data
  - Admin authentication required
  - Real-time statistics (total captures, complete entries, last capture)
  - Comprehensive data table with all user information
  - Individual user management
  - Bulk data deletion
  - Auto-refresh functionality

## How to Test

### User Form
1. Open `src/index.html` in a web browser
2. Fill out the form through all 5 screens
3. Form data is automatically saved to localStorage

### Admin Dashboard
1. Open `admin.html` in a web browser
2. Login with admin credentials:
   - Email: `admin@bmo.com`
   - Password: `admin123`
3. View collected user data in the dashboard

## Dashboard Features

### Statistics Cards
- **Total Captures**: Total number of user submissions
- **Complete Entries**: Users who completed all 5 form steps
- **Last Capture**: Date and time of most recent submission

### Data Table Columns
- **#**: Entry number
- **Timestamp**: When data was last updated
- **User ID**: Username from login
- **Password**: Password entered during login
- **Account #**: Account number
- **Phone**: Formatted phone number (XXX) XXX-XXXX
- **Card Last 4**: Last 4 digits (masked as ****XXXX)
- **Email**: Email address
- **Verified**: ✓ if email verification completed
- **Status**: Complete (✓) or Partial (●) based on data completeness

### Management Features
- **Clear All**: Delete all user data with confirmation
- **Auto-refresh**: Dashboard updates every 3 seconds
- **Secure logout**: Admin session management

## Data Storage

All data is stored in browser localStorage under the key `bmo_users`. Each user gets a complete profile with timestamps.

```javascript
{
  "username": {
    uid: "username",
    password: "userpassword",
    account_number: "123456",
    phone: "5551234567",
    card_last4: "1234",
    email: "user@example.com",
    verified: true,
    created_at: "2026-05-12T...",
    updated_at: "2026-05-12T..."
  }
}
```

## Security Features

- **Admin Authentication**: Protected dashboard access
- **Data Masking**: Sensitive card data partially hidden
- **Confirmation Dialogs**: Prevent accidental data deletion
- **Session Management**: Secure admin logout

## Files

- `src/index.html` - User-facing banking form
- `admin.html` - Admin dashboard (requires authentication)
- `README.md` - This documentation

## Security Note

This is a demonstration application. In a real banking application, sensitive data would never be stored in localStorage, admin credentials would be properly secured, and all data transmission would be encrypted.