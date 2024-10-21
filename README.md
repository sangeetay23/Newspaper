## News App Documentation

This documentation outlines the structure and functionality of the News App, a simple web application that fetches and displays news articles from NewsAPI.org.

**Structure:**

- **index.html:** Main HTML file that defines the structure of the application.
- **styles.css:** Contains all the styles for the HTML elements, creating the visual appearance of the app.
- **script.js:** Contains the JavaScript logic for fetching and displaying news articles, handling user interaction, and managing the dynamic content.

**index.html:**

- **`<!DOCTYPE html>`:** Declares the document as HTML5.
- **`<html lang="en">`:** Root element of the HTML document, specifying English as the language.
- **`<head>`:** Contains meta information about the HTML document, including:
    - **`<meta charset="UTF-8">`:** Specifies UTF-8 as the character encoding for the document.
    - **`<meta name="viewport" content="width=device-width, initial-scale=1.0">`:** Sets the viewport meta tag, ensuring the webpage scales appropriately on different devices.
    - **`<title>News App</title>`:** Defines the title that appears in the browser tab.
    - **`<link rel="stylesheet" href="styles.css">`:** Links the stylesheet to the HTML document.
    - **`<script src="script.js" defer>`:** Links the JavaScript file to the HTML document, using `defer` attribute to ensure the script is executed after the DOM is fully parsed.
- **`<body>`:** Contains the visible content of the HTML document:
    - **`<nav>`:** Navigation bar at the top of the page:
        - **`.main-nav`:** Container for navigation elements, using `flex` class for layout.
        - **`<a href="" class="company-logo">`:** Link to the company logo.
        - **`.nav-links`:** Container for the navigation links.
        - **`<ul class="flex">`:** Unordered list containing navigation links.
        - **`<li class="hover-link nav-item" id="..." onClick="...">`:** List items for different news categories, with hover effects and onclick event handler.
        - **`.search-bar`:** Container for the search bar.
        - **`<input type="text" class="news-input" id="..." placeholder="...">`:** Text input for searching news articles.
        - **`<button class="search-button" id="...">Search</button>`:** Button to trigger the search.
    - **`<main>`:** Main content area of the page:
        - **`.cards-container`:** Container for the news cards.
    - **`<template id="template-news-card">`:** HTML template for each news card, used for cloning and filling data.
        - **`.card`:** Container for each news card, with hover effects.
        - **`.card-header`:** Container for the image of the news article.
        - **`.card-content`:** Container for the title, source, and description of the news article.

**styles.css:**

- **General Styles:**
    - Resets default padding and margin for all elements.
    - Sets box-sizing to border-box.
    - Defines root variables for color schemes.
    - Sets font family for the body.
    - Styles paragraphs and links.
    - Defines flex class for layout.
    - Styles the container for page elements.
- **Navigation Bar Styles:**
    - Styles the navigation bar with background color, box shadow, position, and z-index.
    - Styles the main navigation container using flexbox.
    - Styles the company logo and navigation links.
    - Applies hover effects to navigation links.
    - Styles the active navigation link.
    - Styles the search bar elements.
- **Main Content Styles:**
    - Styles the main content area, including padding and margin.
    - Styles the cards container using flexbox.
    - Styles individual news cards with box shadow, border radius, cursor, background color, and hover effects.
    - Styles the header and content sections of each news card.

**script.js:**

- **`API_KEY` and `url`:** Defines the API key and base URL for fetching news articles.
- **`fetchNews(query)`:** Function to fetch news articles based on the provided query.
    - Uses `fetch` API to make a request to the NewsAPI endpoint.
    - Parses the response as JSON and calls `bindData` function with the articles.
- **`bindData(articles)`:** Function to bind the fetched news articles to the HTML template.
    - Clears the content of the cards container.
    - Iterates through each article and:
        - Creates a clone of the news card template.
        - Calls `fillDataInCard` function to fill the card with article data.
        - Appends the cloned card to the cards container.
- **`fillDataInCard(cardClone, article)`:** Function to fill the cloned card with article data.
    - Sets the image source, title, source, and description of the card.
    - Formats the published date and sets it on the card.
    - Adds an onclick event listener to the card to open the article URL in a new tab.
- **`onNavItemClick(id)`:** Function to handle navigation link clicks.
    - Fetches news articles based on the clicked category.
    - Updates the active navigation link.
- **`searchButton` and `searchText`:** Selects the search button and text input elements.
- **`searchButton.addEventListener("click", ...)`:** Adds a click event listener to the search button.
    - Fetches news articles based on the search query.
    - Removes the active class from the previous navigation link.


**Functionality:**

- **Fetching and Displaying News:**
    - The app fetches news articles from NewsAPI.org based on a specified query.
    - The fetched articles are displayed as cards with image, title, source, and description.
- **Navigation:**
    - The navigation bar allows users to browse news articles by category.
    - Clicking a category link fetches and displays articles for that category.
- **Search:**
    - Users can search for news articles by typing a keyword in the search bar and clicking the search button.
- **Card Interaction:**
    - Clicking on a news card opens the full article in a new tab.

**Explanation:**

- The app uses asynchronous JavaScript with `async/await` syntax for handling network requests.
- It utilizes the NewsAPI.org API to fetch news articles.
- It uses HTML templates for efficient data rendering.
- The app dynamically updates the content based on user interaction (navigation clicks and search).


**Further Improvements:**

- **Pagination:** Implement pagination to handle large datasets.
- **Error Handling:** Add error handling to handle API errors and network failures.
- **Filtering:** Allow users to filter news articles by date, source, etc.
- **Mobile Responsiveness:** Optimize the layout and functionality for mobile devices.

**Notes:**

- Remember to obtain your own API key from NewsAPI.org and replace `API_KEY` with your actual key.
- You can modify the categories and queries used in the code to suit your needs.
- The `defer` attribute in the `<script>` tag ensures that the JavaScript code is executed after the HTML document is fully parsed, preventing potential issues with DOM manipulation.
