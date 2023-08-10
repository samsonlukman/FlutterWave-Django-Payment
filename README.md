# FlutterWave-Django-Payment Documentation

## Table of Contents
1. [Introduction](#introduction)
2. [Service MultiPayment](#service-multipayment)
3. [Single Payment](#single-payment)
4. [MultiPayment MultiCurrency](#multipayment-multicurrency)
5. [Dependencies](#dependencies)

## 1. Introduction <a name="introduction"></a>
The **FlutterWave-Django-Payment** project provides developers with a set of HTML-based payment forms that integrate with Flutterwave's payment gateway. These forms enable seamless and secure digital transactions, allowing developers to accept payments for various services, items, or products on their websites.

The project includes three HTML payment forms, each designed to cater to specific use cases:

1. **Service MultiPayment**: This form enables developers to set the cost of their services in one currency, while users can pay using any currency, thus overcoming digital payment restrictions.

2. **Single Payment**: Designed for e-commerce websites, this form allows developers to list items in multiple currencies. Users can then pay for one item at a time using their preferred currency.

3. **MultiPayment MultiCurrency**: This form is tailored for e-commerce websites that offer multiple items in various currencies. Users can select items and pay for them collectively using a card payment method.

In this documentation, we will provide detailed explanations and usage instructions for each of these payment forms.

## 2. Service MultiPayment <a name="service-multipayment"></a>
**Purpose:** The **Service MultiPayment** form is designed to address scenarios where developers offer services with a fixed cost. This form enables developers to set the service cost in a single currency, while users can choose to pay for the service in any currency supported by Flutterwave.

**How to Use:**

1. Embed the provided HTML code within your web application.
2. Replace the placeholder values in the code:
   - Replace `"YOUR_PUBLIC_KEY"` and `"YOUR_SECRET_KEY"` with your actual Flutterwave public and secret keys.
   - Replace `"YOUR_KEY_HERE"` with your ExchangeRate API key.
   - Adjust any other placeholders as needed to customize the form.
3. When a user clicks the "Click to pay" button, a payment modal will appear.
4. Users can select their preferred payment currency from the dropdown list.
5. Click the "Apply Currency" button to update the payment amount in the selected currency.
6. After applying the currency, users can click the "Pay Now" button to initiate the payment process.
7. The user will be prompted to complete the payment using available payment options.

## 3. Single Payment <a name="single-payment"></a>
**Purpose:** The **Single Payment** form is suitable for e-commerce websites that offer individual items for sale in multiple currencies. Users can select an item, choose their preferred payment currency, and complete the payment for the selected item.

**How to Use:**

1. Integrate the provided HTML code into your e-commerce website.
2. Replace the placeholder values in the code:
   - Replace `"YOUR_PUBLIC_KEY"` and `"YOUR_SECRET_KEY"` with your actual Flutterwave public and secret keys.
   - Replace `"YOUR_KEY_HERE"` with your ExchangeRate API key.
   - Adjust any other placeholders to align with your website's structure and data.
3. When a user clicks the "Click to pay" button, the payment modal will appear.
4. Users can select the currency from the dropdown list and apply it to update the displayed payment amount.
5. After applying the currency, users can click the "Pay Now" button to proceed to payment.
6. Users will be directed to complete the payment process using the provided payment options.

## 4. MultiPayment MultiCurrency <a name="multipayment-multicurrency"></a>
**Purpose:** The **MultiPayment MultiCurrency** form is tailored for e-commerce websites that offer multiple items for purchase, each listed in different currencies. Users can add items to their cart, choose their preferred payment currency, and complete a collective payment for the selected items.

**How to Use:**

1. Embed the provided HTML code into your e-commerce website.
2. Replace the placeholder values in the code:
   - Replace `"YOUR_PUBLIC_KEY"` and `"YOUR_SECRET_KEY"` with your actual Flutterwave public and secret keys.
   - Replace `"YOUR_KEY_HERE"` with your ExchangeRate API key.
   - Adjust any other placeholders as necessary to integrate with your website's functionality.
3. Users can browse items and select their preferred payment currency from the dropdown list.
4. Click the "Apply Currency" button to update the cart's total amounts in the selected currency.
5. Users can then add items to the cart and see the total amounts for different currencies.
6. After selecting items and currency, users can click the "Pay Now" button to initiate payment.
7. Users will be directed to complete the payment using available options, providing a seamless checkout experience.

## 5. Dependencies <a name="dependencies"></a>
The **FlutterWave-Django-Payment** project requires the following dependencies:

- [Flutterwave Checkout Library](https://checkout.flutterwave.com/v3.js): Used to handle the payment checkout process.
- [Flutterwave OTP Library](https://api.flutterwave.com/v3/otps): Used to handle OTP (One-Time Password) validation for added security.

Developers must obtain their Flutterwave public and secret keys, as well as an ExchangeRate API key, to successfully integrate these forms into their websites.

---

By utilizing the **FlutterWave-Django-Payment** project, developers can seamlessly integrate payment functionalities into their websites for various use cases, enhancing user experience and enabling secure and convenient transactions.

## License

This project is licensed under the [MIT License](LICENSE).