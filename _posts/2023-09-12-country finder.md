---
toc: true
comments: false
layout: post
title: Country Information 
type: tangibles
courses: { compsci: {week: 3} }
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Country Information</title>
    <style>
        /* Add some basic CSS for styling */
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        #country-info {
            max-width: 600px;
            margin: 0 auto;
        }
    </style>
</head>
<body>
    <h1>Country Information</h1>
    <p>Type the name of a country:</p>
    <input type="text" id="country-input">
    <button onclick="fetchCountryInfo()">Search</button>
    <div id="country-info"></div>

    <script>
        async function fetchCountryInfo() {
            const countryInput = document.getElementById('country-input').value;
            const countryInfoContainer = document.getElementById('country-info');
            countryInfoContainer.innerHTML = ''; // Clear previous results

            try {
                // Fetch all country data from the REST Countries API
                const response = await fetch('https://restcountries.com/v3.1/all');
                const allCountriesData = await response.json();

                // Find the country matching the input name
                const countryData = allCountriesData.find(country =>
                    country.name.common.toLowerCase() === countryInput.toLowerCase()
                );

                if (countryData) {
                    // Display country information
                    const countryName = countryData.name.common;
                    const countryCapital = countryData.capital?.[0] || 'N/A';
                    const countryPopulation = countryData.population?.toLocaleString() || 'N/A';
                    const countryRegion = countryData.region || 'N/A';
                    const countryInfoHTML = `
                        <h2>${countryName}</h2>
                        <p>Capital: ${countryCapital}</p>
                        <p>Population: ${countryPopulation}</p>
                        <p>Region: ${countryRegion}</p>
                    `;
                    countryInfoContainer.innerHTML = countryInfoHTML;
                } else {
                    countryInfoContainer.innerHTML = '<p>Country not found.</p>';
                }
            } catch (error) {
                console.error('Error fetching country information:', error);
                countryInfoContainer.innerHTML = '<p>An error occurred.</p>';
            }
        }
    </script>
</body>
</html>
