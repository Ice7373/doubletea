# doubletea
Tea app
// Helper function to fetch data from an API
async function fetchData(url) {
    try {
        const response = await fetch(url);
        if (!response.ok) {
            throw new Error(`HTTP error! Status: ${response.status}`);
        }
        const data = await response.json();
        return data;
    } catch (error) {
        console.error('Error fetching data:', error);
        return null;
    }
}

// Example usage of the helper function
async function main() {
    const apiURL = 'https://jsonplaceholder.typicode.com/posts';
    const data = await fetchData(apiURL);
    if (data) {
        console.log('Fetched Data:', data);
    }
}

// Call the main function
main();
