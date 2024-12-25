# How to Embed a Google Map with a Marker in Northern Virginia

Follow these steps to add a Google Map with a marker pointing to Northern Virginia on your website.

## Step 1: Get Your Google Maps API Key

1. Go to the [Google Cloud Console](https://console.cloud.google.com/).
2. Create a new project if you don't already have one.
3. Enable the **Google Maps JavaScript API**.
4. Navigate to **APIs & Services > Credentials**.
5. Click **Create Credentials**, then select **API Key**.
6. Copy your API key to use in the next step.

## Step 2: Add the Google Maps HTML and Script

Copy the following code into your HTML file.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Google Map - Northern VA</title>
  <style>
    /* Set the size of the map */
    #map {
      height: 400px;
      width: 100%;
    }
  </style>
</head>
<body>

  <h3>Map of Northern Virginia</h3>
  <div id="map"></div>

  <script>
    function initMap() {
      // Northern Virginia coordinates (Arlington, VA as an example)
      const northernVA = { lat: 38.907, lng: -77.0365 };  // Latitude and Longitude for Northern VA

      // Create a map centered at Northern Virginia
      const map = new google.maps.Map(document.getElementById("map"), {
        zoom: 10, // Set the zoom level
        center: northernVA, // Set the center of the map
      });

      // Add a marker at Northern Virginia
      const marker = new google.maps.Marker({
        position: northernVA,
        map: map,
        title: "Northern Virginia",
      });
    }
  </script>

  <!-- Include the Google Maps API with your API key -->
  <script
    src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=initMap&v=weekly"
    async
  ></script>

</body>
</html>```
