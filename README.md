# Sales Summary Web App

## Summary
This static web application fetches data from an updated `data.csv` file (updated with new data from attachments), calculates the total sales amount, and displays it on the webpage titled "Sales Summary 892d05c0". It also includes new features for enhanced data presentation in a Bootstrap table. Bootstrap 5 is loaded from jsdelivr to style the page.

## Setup
To deploy the app on GitHub Pages, follow these steps:
1. Upload your updated `data.csv` file that includes the new data as an attachment.
2. Push all your files to a GitHub repository.
3. Enable GitHub Pages in the repository settings.

## Usage
- Access the static single-page site by visiting the GitHub Pages URL.
- No query parameters or configuration options are needed.
- Key Features:
  - Fetches data from the updated `data.csv` from attachments
  - Calculates and displays the total sales amount
  - Lists each product with its total sales in the Bootstrap table `#product-sales`
  - Ensures `#total-sales` is updated accurately after rendering
  - Utilizes Bootstrap 5 for styling

## Code Explanation
This web app is built using HTML and JavaScript. Key features include:
- Fetching data from the updated `data.csv` file using JavaScript.
- Summing the sales column to calculate the total amount.
- Listing each product with its total sales in the Bootstrap table `#product-sales`.
- Ensuring the `#total-sales` element is accurately updated after rendering.
- Setting the page title to "Sales Summary 892d05c0".
- Loading Bootstrap 5 from jsdelivr for enhanced styling.

## License
This project is licensed under the MIT License.