# 🤖 How to Create a Telegram Bot and Send Messages Using PHP

This guide will walk you through the entire process of creating a Telegram bot using [BotFather](https://t.me/botfather) and sending a message to a user using a simple PHP script.

---

## 🚀 Step-by-Step Guide

### 1. Create Your Bot
1. Open Telegram and search for **[BotFather](https://t.me/botfather)**.
2. Click the **Start** button.
3. Click or type **/newbot**.
4. Enter a name for your bot. Example: `CMSBotTest`
5. Enter a unique username ending in `Bot`. Example: `CMSBot`
6. BotFather will return a **Bot Token**. Copy and save it — you'll need it to send messages.

---

### 2. Get Your Chat ID
1. Open Telegram and search for **[userinfobot](https://t.me/userinfobot)**.
2. Click **Start** and it will respond with your **user ID** (this is your chat ID). Copy and save it.

---

### 3. Start a Chat with Your Bot
1. Search for your new bot by the username you created (`@CMSBot`).
2. Click **Start** to activate the conversation.

---

## 💻 PHP Script to Send a Message

Now that you have your bot token and chat ID, use the following PHP script to send a message:

```php
<?php
$botToken = ""; // Replace with your bot token
$chatId = ""; // Replace with your actual chat ID
$message = "Hello This bot Made By Hasan Raza";

// Telegram API URL
$url = "https://api.telegram.org/bot$botToken/sendMessage";

// Set POST fields
$data = [
    'chat_id' => $chatId,
    'text' => $message,
    'parse_mode' => 'HTML' // Optional: Use 'Markdown' or 'HTML'
];

// Send message using cURL
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, $url);
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $data);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

$response = curl_exec($ch);

// Check for cURL errors
if(curl_errno($ch)) {
    echo 'cURL Error: ' . curl_error($ch);
} else {
    echo "Telegram Response: " . $response;
}

curl_close($ch);
?>
                       
# telegram-alert-bot
telegram-alert-bot  telegram-bot-php  php-telegram-message  alert-bot-with-php  telegram-bot-notifier   telegram-bot-by-hasan  php-send-telegram  telegram-bot-guide
