# Flutterwave Payment

This is a web page that allows users to make payments using the Flutterwave payment gateway. It integrates with the Flutterwave API and provides functionality for currency selection, payment initiation, and OTP validation.

## Prerequisites

To use this payment page, you need the following:

- Web browser with JavaScript enabled
- Internet connection

## Usage

1. Include the required scripts in the `<head>` section of your HTML file:

```html
<script src="https://checkout.flutterwave.com/v3.js"></script>
<script src="https://api.flutterwave.com/v3/otps"></script>
```

2. Add the necessary HTML elements to your page:

```html
<div class="container-fluid">
    <div class="form-group">
        <label for="currencyDropdown">Choose Currency</label>
        <select id="currencyDropdown" class="form-control">
            <option value="" selected disabled>Select Currency</option>
            <!-- Currency list will be populated dynamically -->
        </select>
    </div>

    <button type="button" class="btn btn-primary" onclick="makePayment()">Pay Now</button>
    <button onclick="updateFlutterwaveCurrency()" class="btn btn-primary">Apply Currency</button>
</div>
```

3. Customize the JavaScript code according to your requirements. You can modify the following functions:

- `makePayment()`: This function is triggered when the "Pay Now" button is clicked. It retrieves the selected currency, fetches the currency conversion rate from the ExchangeRate API, calculates the converted amount, and initiates the Flutterwave payment using the FlutterwaveCheckout function.

- `flutterOtp()`: This function sends an OTP (One-Time Password) to the customer using the Flutterwave API. You may need to customize the OTP configuration and provide your own API credentials.

- `validateOtp()`: This function validates the OTP entered by the customer. Again, you may need to modify the OTP validation process and provide your own API credentials.

- `updateFlutterwaveCurrency()`: This function is triggered when the "Apply Currency" button is clicked. It fetches the currency conversion rate for the selected currency and updates the payment amount displayed on the page.

4. Customize the API credentials and other parameters according to your Flutterwave account settings.

5. Deploy the HTML file and open it in a web browser to use the Flutterwave payment functionality.

## Notes

- The currency options in the dropdown list are populated dynamically based on the `flutterwaveCurrencies` variable passed from the database. Make sure to replace this variable with the actual currency list.

- The currency conversion rates are fetched from the ExchangeRate API. You may need to sign up for an API key and replace the API URL in the code with your own key.

- The `public_key` in the FlutterwaveCheckout function should be replaced with your actual Flutterwave public key.

- The redirect URL in the FlutterwaveCheckout function should be updated to the appropriate URL in your application where the payment response will be handled.

- The `meta` object in the FlutterwaveCheckout function contains additional metadata related to the payment. Replace the sample values with your own metadata.

- The `customer` object in the FlutterwaveCheckout function contains customer information. You should replace the sample values with actual customer details.

- The `customizations` object in the FlutterwaveCheckout function allows customization of the payment page. Modify the `title`, `description`, and `logo` values to match your application branding.

## License

This project is licensed under the [MIT License](LICENSE).
