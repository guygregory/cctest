# Simple Calculator Web App

A clean, modern calculator web application designed for deployment to Azure Static Web Apps.

## Features

- Basic arithmetic operations (addition, subtraction, multiplication, division)
- Decimal number support
- Clear and delete functionality
- Keyboard support for all operations
- Responsive design that works on desktop and mobile
- Modern UI with gradient background and smooth animations

## Live Demo

The calculator includes:
- Addition (+)
- Subtraction (-)
- Multiplication (×)
- Division (/)
- Clear (C)
- Delete last character (⌫)
- Decimal point (.)

## Keyboard Shortcuts

- Numbers: `0-9`
- Operators: `+`, `-`, `*`, `/`
- Calculate: `Enter` or `=`
- Clear: `Escape` or `C`
- Delete: `Backspace`

## Local Development

To run the calculator locally:

1. Clone this repository
2. Open `index.html` in a web browser, or
3. Use a simple HTTP server:
   ```bash
   python3 -m http.server 8080
   ```
   Then navigate to `http://localhost:8080`

## Deployment to Azure Static Web Apps

### Option 1: Deploy via Azure Portal

1. Go to [Azure Portal](https://portal.azure.com)
2. Create a new "Static Web App" resource
3. Connect to your GitHub repository
4. Set the build configuration:
   - **App location**: `/` (root)
   - **Api location**: (leave empty)
   - **Output location**: (leave empty)
5. Azure will automatically set up GitHub Actions for CI/CD

### Option 2: Deploy via Azure CLI

```bash
# Install Azure CLI if needed
# https://docs.microsoft.com/en-us/cli/azure/install-azure-cli

# Login to Azure
az login

# Create a resource group (if needed)
az group create --name myResourceGroup --location eastus

# Create the static web app
az staticwebapp create \
  --name my-calculator-app \
  --resource-group myResourceGroup \
  --source https://github.com/YOUR-USERNAME/cctest \
  --location eastus \
  --branch main \
  --app-location "/" \
  --login-with-github
```

### Option 3: Deploy via VS Code Extension

1. Install the "Azure Static Web Apps" extension in VS Code
2. Sign in to Azure
3. Right-click on the project folder
4. Select "Create Static Web App"
5. Follow the prompts

## Project Structure

```
.
├── index.html              # Main HTML file
├── styles.css              # CSS styling
├── script.js               # Calculator logic
├── staticwebapp.config.json # Azure Static Web Apps configuration
└── README.md               # This file
```

## Technologies Used

- HTML5
- CSS3 (with Flexbox and Grid)
- Vanilla JavaScript (no frameworks required)

## Browser Support

Works on all modern browsers:
- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## License

This project is open source and available for use.
