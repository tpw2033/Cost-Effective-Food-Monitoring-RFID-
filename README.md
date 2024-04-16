# Cost-Effective Food Monitoring using RFID tags

This project aims to tackle the ever-growing problem of food being wasted when the expiration date comes and goes without the consumer realizing it. I am providing a brief summary below, but it is best explained through the PowerPoint in the documentation folder, as well as the screenshots below.

The central hub of the project is a computer-based Java interface, which reads in temperature/humidity data from an Arduino Nano. RFID tags are also read from a keyboard-input RFID reader. The interface looks up item data using a UPC API, and grabs the UPC itself and expiration date from the RFID data, in SGTIN+ format. Additionally, emails are sent using SMTP and GMail credentials, notifying users of impending expiration dates.

The Java-based interface inserts/retrieves/modifies data using Firebase, a free-to-use Google tool that also has realtime database support. This realtime database is especially useful for a smartphone app, in which listeners can be utilized to update items added over RFID with near-zero delay. 

The smartphone app was designed in Java using Android Studio, and tested on a OnePlus 9 running Android 14. Here are a few of the major features of the smartphone app:

* User login/signup system, to allow for multiple users to utilize the application, each with their own set of items.
* Item list, getting RFID-based items from the computer interface, as well as manually added items by the user.
* Items can be added manually by scanning UPC barcode, which makes a request to UPC API to retrieve item name and a stock photo to show on the item list.
* Fridge status display with temperature and humidity, and a switchable graph view showing the changes over the last 5 hours.
* AI-generated recipes from items that the user selects. Notes can be optionally entered to fine-tune the recipes (ex. spicy, cold, etc.)

