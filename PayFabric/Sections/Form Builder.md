# Form Builder Elements
Welcome to Form Builder! Form Builder allows you to create customizable payment forms that can be shared with customers through a direct link. Forms can collect customer information, display products, apply discounts, calculate taxes, and securely accept payments.

This guide covers the basics of creating and customizing a payment form while highlighting key rules to ensure calculations work correctly.


# Choosing Form Template

### Simple Form Template 

Use the Simple Form Template when you only need to collect a payment amount from the customer.

The form includes:

- Company Information
- Customer Information
- Amount
<img width="640" height="370" alt="image" src="https://github.com/user-attachments/assets/a8140f95-0a52-427d-b1fd-d2eb9530ca1a" />

### Itemized Form Template

Use the Itemized Form Template when you need to sell products or services with itemized pricing.

In addition to the fields included in the Simple Form Template, the Itemized Form Template also includes:

- Product Details
- Subtotal
- Tax
- Discount
- Total
<img width="640" height="459" alt="image" src="https://github.com/user-attachments/assets/e6d075c7-d9f7-4dbe-b312-6b8c52f5fb98" />


## Understanding the Default Form

When creating a new form, the selected template is preconfigured with common fields to help you get started.

### Company Information

This section displays:

- Company Logo
- Company Name
- Form Description

Use this area to let customers know what the form is for and who they are submitting payment to.

### Customer Information

By default, the form includes:

- First Name
- Last Name
- Email Address
- Phone Number

You can mark any of these fields as required and add additional fields as needed.

### Amount (Simple Form Template Only)

Allows the customer to enter or view the custom payment amount.

### Product Details (Itemized Form Template Only)

This section contains an Item group used to display products and pricing information.

**NOTE:** Select an existing item to automatically populate the product details.

### Payment Information (Itemized Form Template Only)

The following values are calculated automatically based on the selected items:

- Subtotal
- Total Tax
- Discount
- Total

**IMPORTANT: **Product Details, Subtotal, Tax, Discount, and Total are linked to the payment calculation engine. Do not separate or modify these components.


## Customize Your Form

To add or modify content:

1. Drag an element from the **Left Panel** onto the canvas.
2. Select the element on the canvas.
3. Configure its properties in the **Settings Panel **on the right of the canvas.
4. Save your changes.

### Basic Elements

The following elements can be added to any form template:

- Text
- Headings
- HTML
- Spacers
- Dividers

Use these elements to provide instructions, organize content, and customize the layout of your form.

#### Setting Up Discounts (Itemized Form Template Only)

1. Select the **Discount** field in the form.
<img width="418" height="84" alt="image" src="https://github.com/user-attachments/assets/ddacb2f1-dc94-4134-82ce-891a3dd8208b" />

2. In the **Settings Panel**, choose the discount type.
<img width="640" height="39" alt="image" src="https://github.com/user-attachments/assets/7cf622ce-6842-4b53-aef0-d54b38174912" />

3. Enter the discount value.
<img width="306" height="523" alt="image" src="https://github.com/user-attachments/assets/fea1963b-cf61-4def-a2a3-5c8602eb0eab" />

| Discount Type | Description | Example |
| --- | --- | --- |
| Percentage | Applies a percentage discount to the order subtotal. | Entering **10** applies a **10% discount.** |
| Fixed Amount | Applies a flat dollar amount discount to the order. | Entering **10** applies a **$10.00 discount.** |

## Test Your Form

Before publishing your form, use **Preview** mode to verify the form display.

Confirm that:

- Required fields behave as expected.
- The form displays as intended.
- The input amount can be entered successfully (Simple Form Template only).
- Products display correctly (Itemized Form Template only).
- Payment calculations are accurate (Itemized Form Template only).

