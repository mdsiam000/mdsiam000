<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WhatsApp Messaging App</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            text-align: center;
            margin-top: 50px;
        }
        .container {
            background-color: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            display: inline-block;
        }
        h1 {
            color: #25D366;
        }
        input, textarea {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            background-color: #25D366;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        button:hover {
            background-color: #1ebe57;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>Send WhatsApp Message</h1>

        <form id="whatsappForm">
            <label for="phone">Phone Number (with country code):</label>
            <input type="text" id="phone" placeholder="e.g., +8801XXXXXXXXX" required>

            <label for="message">Your Message:</label>
            <textarea id="message" rows="5" placeholder="Enter your message here" required></textarea>

            <button type="submit">Send Message</button>
        </form>
    </div>

    <script>
        document.getElementById('whatsappForm').addEventListener('submit', function (event) {
            event.preventDefault();
            var phone = document.getElementById('phone').value;
            var message = document.getElementById('message').value;
            
            // WhatsApp URL construction
            var whatsappUrl = 'https://api.whatsapp.com/send?phone=' + encodeURIComponent(phone) + '&text=' + encodeURIComponent(message);
            
            // Redirecting to WhatsApp with the user input
            window.open(whatsappUrl, '_blank');
        });
    </script>

</body>
</html>
