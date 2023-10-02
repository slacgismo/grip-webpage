---
layout: page
cover: 'assets/images/orange.jpg'
navigation: True
title:  "Contact | GRIP"
date:   2023-07-20 11:59:00 -0700
logo: 'assets/images/arras.png'
current: about
---

# Contact Us
<body>
    <p>Have questions or feedback? Contact us using the form below:</p>

    <form action="process_form.php" method="POST">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" required><br><br>

        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required><br><br>

        <label for="message">Message:</label><br>
        <textarea id="message" name="message" rows="4" required></textarea><br><br>

        <input type="submit" value="Submit">
    </form>
</body>
