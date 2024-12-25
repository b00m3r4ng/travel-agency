# How to Add Dark/Light Mode to Your Website

This guide will help you implement a theme toggle to switch between dark and light modes on your website, changing the color palette based on the user's preference.

## Step 1: Define Color Palettes for Light and Dark Mode

In your CSS file, define two sets of color variables: one for light mode and one for dark mode. These will be used to dynamically change the color scheme.

### Example: Define Color Variables

```css
:root {
  /* Light Mode Colors */
  --light-bg: #ffffff;
  --light-text: #333333;
  --light-primary: #FF6F61;
  --light-secondary: #00B8D4;

  /* Dark Mode Colors */
  --dark-bg: #121212;
  --dark-text: #ffffff;
  --dark-primary: #FF6F61;
  --dark-secondary: #FFDD00;
}

body {
  background-color: var(--light-bg);
  color: var(--light-text);
}

/* You can also specify default styles for your elements */
.header, .footer {
  color: var(--light-primary);
}
```

In this example:

- --light-bg and --dark-bg control the background color for light and dark modes, respectively.
- --light-text and --dark-text control the text color for each mode.
- --light-primary and --dark-primary are used for your primary color, while - --light-secondary and --dark-secondary are for accent colors.

Adding/Altering Button for Toggle

```
<button id="theme-toggle">Switch to Dark Mode</button>
```

Add the JS

```
<script>
  const themeToggle = document.getElementById("theme-toggle");

  // Check if the user has a saved theme preference
  if (localStorage.getItem("theme") === "dark") {
    document.body.classList.add("dark");
    themeToggle.textContent = "Switch to Light Mode";
  } else {
    document.body.classList.remove("dark");
    themeToggle.textContent = "Switch to Dark Mode";
  }

  // Add event listener to the theme toggle button
  themeToggle.addEventListener("click", () => {
    document.body.classList.toggle("dark");
    
    // Save the user's theme preference in local storage
    if (document.body.classList.contains("dark")) {
      themeToggle.textContent = "Switch to Light Mode";
      localStorage.setItem("theme", "dark");
    } else {
      themeToggle.textContent = "Switch to Dark Mode";
      localStorage.removeItem("theme");
    }
  });
</script>
```

Change CSS to include the colors it should display with Dark Mode selected

```
body.dark {
  background-color: var(--dark-bg);
  color: var(--dark-text);
}

body.dark .header, body.dark .footer {
  color: var(--dark-primary);
}

/* You can add more specific styles for other elements */
```