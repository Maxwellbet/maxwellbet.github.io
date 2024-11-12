<!DOCTYPE html>
<!-- saved from url=(0061)file:///C:/Users/atmic/OneDrive/Desktop/buspass/RTCNOV28.html -->
<html lang="en"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="file:///C:/Users/atmic/OneDrive/Desktop/buspass/styles.css"> 
    <title>Live Clock Overlay on Video</title>
    <style>
        body {
            margin: 0;
            overflow: hidden; /* Hide scrollbars */
            font-family: Arial, sans-serif; 
            margin: 0%; 
            padding: 0;
        }
        .video-container {
            position: relative;
            width: 100%;
            height: 100%;
            /* Optional: Use the below line for a background color while loading */
            background-color: black; /* Fallback or loading background */ 
            max-width: 1200px; 
            margin: 0 auto; 
        }
        video {
            width: 100%;
            height: auto; /* Maintain aspect ratio */
            display: block; /* Remove extra space below video */
        }
        .clock {
            position: absolute;
            bottom: 40%; /* Distance from the bottom */
            transform:100%(auto); /* Center align the clock */
            right: 20%;
            font-size: 8em;
            color: rgb(10, 6, 6); /* Change color as necessary */
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.8); /* Shadow for visibility */
            font-family: 'Arial', sans-serif; /* Use Arial or any sans-serif font */
        }

    </style>       
<div class="video-container">
    <video autoplay="" muted="" loop="">
        <source src="C:\Users\atmic\OneDrive\Desktop\passmp4.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <div class="clock" id="clock">03:22:34 AM</div>
</div>

<script>
    function updateClock() {
        const now = new Date();
        let hours = now.getHours();
        const minutes = String(now.getMinutes()).padStart(2, '0');
        const seconds = String(now.getSeconds()).padStart(2, '0');
        const isAM = hours < 12;

        // Convert to 12-hour format
        hours = hours % 12 || 12; // If hours is 0, set it to 12

        // Format the hour to be 2 digits
        hours = String(hours).padStart(2, '0');

        // Determine AM/PM
        const period = isAM ? 'AM' : 'PM';

        // Display the clock
        document.getElementById('clock').textContent = `${hours}:${minutes}:${seconds} ${period}`;
    }

    setInterval(updateClock, 1000);
    updateClock(); // Initial call to display clock immediately
</script>


</body></html>
