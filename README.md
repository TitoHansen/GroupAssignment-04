# NASA Astronomy Picture of the Day Web App

**Final Project for 24S Client-Side JavaScript - 200**  
**ILAC Georgian College**

![Astronomy Picture of the Day](https://apod.nasa.gov/apod/image/2408/M20OriginalLRGBHaO3S2_1024x735.jpg)
![Screenshot of the app](./images/screenshot.png)




## Overview

This project is a web application that displays NASA's Astronomy Picture of the Day (APOD) using the NASA public API. The app features a clean, user-friendly interface inspired by modern web design practices, with a responsive layout and intuitive navigation.

## Features

- **Astronomy Picture of the Day**: Displays the daily image or video provided by NASA's APOD API.
- **Detailed Information**: Includes the title, description, and date of the APOD.
- **Responsive Design**: Works on all devices, including desktops, tablets, and mobile phones.
- **Navigation**: A header with a title aligned to the left and a navigation menu aligned to the right.
- **Footer**: Provides links to the NASA API documentation and credits.

## Technologies Used

- **HTML5**: Structure and content of the web page.
- **CSS3**: Styling, layout, and responsive design.
- **JavaScript**: Fetching and displaying data from the NASA APOD API.
- **NASA APOD API**: Retrieves the Astronomy Picture of the Day and associated metadata.

## Installation

To run this project locally, follow these steps:

1. **Clone the repository**:
    ```bash
    git clone https://github.com/your-username/nasa-apod-app.git
    ```
   
2. **Navigate to the project directory**:
    ```bash
    cd nasa-apod-app
    ```

3. **Open the `index.html` file in your web browser**:
    - You can double-click the `index.html` file to open it in your default web browser.
    - Alternatively, you can use a local web server (e.g., using VSCode Live Server or Python's SimpleHTTPServer).

## How to Use the NASA APOD API

To use the NASA APOD API within this project, follow these steps:

### 1. Get Your API Key

1. Visit the [NASA API Portal](https://api.nasa.gov/).
2. Click on "Sign Up" to create an account if you don't have one.
3. After signing up, log in to your account.
4. Go to the "API Key" section and generate a new API key. This key will be used to authenticate your requests to the NASA APOD API.

### 2. Update the API Key in the Project

1. Open the `script.js` file located in the project directory.
2. Replace the existing API key with your newly generated key:

    ```javascript
    const apiKey = 'YOUR_NEW_API_KEY_HERE';
    ```
   
   Make sure to replace `'YOUR_NEW_API_KEY_HERE'` with the actual API key you received from NASA.

### 3. Make API Calls

The project uses the NASA APOD API to fetch and display the Astronomy Picture of the Day. The `script.js` file contains the necessary code to make an API call:

```javascript
const apiUrl = `https://api.nasa.gov/planetary/apod?api_key=${apiKey}`;

document.addEventListener('DOMContentLoaded', () => {
    fetch(apiUrl)
        .then(response => response.json())
        .then(data => displayApod(data))
        .catch(error => {
            console.error('Error fetching the APOD data:', error);
            document.getElementById('apodContent').innerHTML = `<p>Failed to retrieve data.</p>`;
        });
});
