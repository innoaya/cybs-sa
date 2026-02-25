# CyberSource Secure Acceptance - Standalone HTML Tester

A standalone, single-page HTML application for testing CyberSource Secure Acceptance integration without requiring a backend server.

## Features

- ✅ **No Backend Required** - Pure client-side HTML/JavaScript implementation
- 🔐 **Secure Signature Generation** - Uses Web Crypto API for HMAC-SHA256
- 🎨 **Modern UI** - Beautiful, responsive interface
- ⚡ **Instant Testing** - Enter credentials and test immediately
- 🔧 **Configurable** - Support for both test and production environments

## How to Use

### Step 1: Open the File
Simply open `index.html` in any modern web browser (Chrome, Firefox, Safari, Edge).

### Step 2: Enter CyberSource Credentials
Fill in the required fields:
- **Access Key**: Your CyberSource access key
- **Profile ID**: Your Secure Acceptance profile ID
- **Secret Key**: Your CyberSource secret key
- **Submit URL**: Choose between Test or Production server

### Step 3: Configure Test Data
- Enter billing information (pre-filled with sample data)
- Set transaction amount and currency
- Choose transaction type (Sale or Authorization)

### Step 4: Test
Click the **"Test Payment"** button. If your credentials are correct, you'll be redirected to the CyberSource payment page.

## Configuration Details

### Environment URLs
- **Test Server**: `https://testsecureacceptance.cybersource.com/pay`
- **Production Server**: `https://secureacceptance.cybersource.com/pay`

### Default Test Values
- Amount: 100 MMK
- Currency: MMK (Myanmar Kyat)
- Country: MM (Myanmar)
- Transaction Type: Sale

## How It Works

1. User enters credentials and transaction details
2. Application generates a unique transaction UUID
3. Creates a signed data string with all required fields
4. Generates HMAC-SHA256 signature using the secret key
5. Submits the form to CyberSource Secure Acceptance
6. User is redirected to CyberSource payment page

## Browser Requirements

- Modern browser with Web Crypto API support
- JavaScript enabled
- No additional dependencies or installations required

## Security Notes

- The secret key is only used client-side for signature generation
- No data is stored or transmitted to third parties
- All processing happens in your browser
- Secret key input is masked for security

## Comparison with Backend Version

| Feature | Backend (Node.js) | This HTML Version |
|---------|------------------|-------------------|
| Setup | Requires Node.js, npm install | Open HTML file |
| Configuration | .env file | UI form |
| Testing | Start server, visit URL | Open file directly |
| Dependencies | Express, dotenv, etc. | None |
| Flexibility | Fixed config | Dynamic config |

## Troubleshooting

**Payment doesn't redirect?**
- Verify your Access Key, Profile ID, and Secret Key are correct
- Check that you're using the correct Submit URL (Test vs Production)
- Ensure your Secure Acceptance profile is properly configured in CyberSource

**Getting errors?**
- Check browser console for detailed error messages
- Verify all required fields are filled
- Ensure browser supports Web Crypto API

## License

This is a testing tool for CyberSource Secure Acceptance integration.
