# FlutterWave-Django-Payment
Documentation for accepting multiple currencies and payments with Flutterwave with Django

Overview
This documentation provides a detailed explanation of the Flutterwave payment integration code provided. The code is written in HTML, JavaScript, and utilizes the Flutterwave API for processing payments.

HTML Structure
The HTML structure of the code is as follows:

html
Copy code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flutterwave Payment</title>
    <script src="https://checkout.flutterwave.com/v3.js"></script>
    <script src="https://api.flutterwave.com/v3/otps"></script>
</head>
<body>
</body>
...
</html>
The <head> section includes the necessary meta tags and defines the title of the page. It also imports the Flutterwave JavaScript library using two <script> tags.

Payment Form
Within the HTML structure, there is a payment form represented by a <div> element with the class "container-fluid". This form allows users to select a currency and initiate a payment.

html
Copy code
<div class="container-fluid">
    <div class="form-group">
        <label for="currencyDropdown">Choose Currency</label>
        <select id="currencyDropdown" class="form-control">
            <option value="" selected disabled>Select Currency</option>
            {% for currency in flutterwaveCurrencies %}
                <option value="{{ currency }}">{{ currency }}</option>
            {% endfor %}
        </select>
    </div>
    
    <button type="button" class="btn btn-primary" onclick="makePayment()">Pay Now</button>
    <button onclick="updateFlutterwaveCurrency()" class="btn btn-primary">Apply Currency</button>
</div>
The form consists of a dropdown menu (<select>) where users can choose a currency. The available currency options are populated dynamically from the flutterwaveCurrencies variable. Two buttons are provided: "Pay Now" and "Apply Currency." The "Pay Now" button triggers the makePayment() function, while the "Apply Currency" button triggers the updateFlutterwaveCurrency() function.

JavaScript Functions
The code includes several JavaScript functions that handle payment processing and currency conversion.

makePayment()
This function is called when the "Pay Now" button is clicked. It retrieves the selected currency from the dropdown menu, fetches the currency conversion rate, and initiates the Flutterwave payment checkout process.

flutterOtp()
This function is responsible for sending an OTP (One-Time Password) to the user's email or phone number. It makes an HTTP POST request to the Flutterwave API's /v3/otps endpoint to generate the OTP.

validateOtp()
This function validates the OTP entered by the user. It makes an HTTP POST request to the Flutterwave API's /v3/otps/:reference/validate endpoint with the OTP entered by the user.

updateFlutterwaveCurrency()
This function is triggered when the "Apply Currency" button is clicked. It retrieves the selected currency from the dropdown menu, fetches the currency conversion rate, and updates the payment amount on the page accordingly.

Integration with Flutterwave APIs
The code integrates with the Flutterwave APIs for payment processing and OTP generation/validation.

Flutterwave Checkout
The makePayment() function uses the FlutterwaveCheckout function from the Flutterwave JavaScript library to initiate the payment checkout process. It sets various parameters such as the public key, transaction reference, amount, currency, payment options, redirect URL, customer details, and customizations.

Flutterwave OTP APIs
The flutterOtp() and validateOtp() functions interact with the Flutterwave OTP APIs. flutterOtp() sends a request to generate an OTP, while validateOtp() sends a request to validate the OTP entered by the user.

Additional Notes
The code uses template variables (e.g., {{ listing.price.bid }}, {{ user.email }}, {{ user.username }}, {{ listing.id }}, {{ listing.currency }}) to populate dynamic values. These variables should be replaced with actual values from the application or backend.
The code relies on external dependencies such as the Flutterwave JavaScript library and the ExchangeRate API. Make sure these dependencies are available and properly integrated into your project.
Please note that this documentation provides an overview of the code structure and functionality. To fully integrate the code into your project, you may need to make additional modifications and handle backend integration for processing payments and validating OTPs.
