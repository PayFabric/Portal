# Integration Connectors – Data Transformation

As a merchant, you can now customize the data that integrates with PayFabric to handle complex mapping scenarios. This feature enables you to build and validate expressions using a variety of operators, allowing you to transform data dynamically instead of relying on static variables.

---
## How to Use

| **Step** | **Action** | **Description** |
|-----------|-------------|-----------------|
| **1** | **Open Mapping Page** | Select a desired Data Type from Integration Connectors. |
| **2** | **Edit with the Pencil Icon** | Choose the source data field you want to map. |
| **3** | **Build Expression** | Enter your custom expression using supported operators and values. |
| **4** | **Validate Expression** | Click **Validate** to check for syntax and logical accuracy. |

## Supported Operators

| **Category** | **Operators** | **Usage / Example** |
|---------------|----------------|----------------------|
| **Arithmetic** | `+`, `-`, `*`, `/`, `%` | Perform numeric calculations.<br>Example: `Amount + Tax`, `Value / 2`, `Amount % 10` |
| **Logical** | `&&`, `\|\|`, `!` | Combine or negate Boolean conditions.<br>Example: `IsActive && HasPermission`, `!IsDeleted` |
| **Comparison** | `==`, `!=`, `>`, `<`, `<=`, `>=` | Compare values.<br>Example: `Status == "Active"`, `Amount > 100` |
| **Conditional** | `condition ? value_if_true : value_if_false` | Apply conditional logic.<br>Example: `Amount > 100 ? "High" : "Low"` |
| **String Concatenation** | `+` | Combine text values.<br>Example: `"Invoice-" + invoiceNumber` |
| **Parentheses** | `( )` | Control order of operations.<br>Example: `(Amount + Tax) * Quantity` |
| **Hardcoded Values** | Strings, numbers, booleans | Include fixed values.<br>Example: `"USD"`, `100`, `true` |

---

## Expression Examples

| **Category** | **Example Expression** | **Explanation / Result** |
|---------------|------------------------|---------------------------|
| **Mathematical Operators** | `Amount + Tax` | Adds the tax to the amount. |
|  | `Price * Quantity` | Calculates total price for given quantity. |
|  | `Total - Discount` | Subtracts discount from total. |
|  | `Value / 2` | Divides the value by 2. |
|  | `Amount % 10` | Returns the remainder when dividing amount by 10. |
| **Comparison Operators** | `Amount > 100` | Returns true if amount is greater than 100. |
|  | `Price < 50` | Returns true if price is less than 50. |
|  | `Quantity >= 1` | Returns true if quantity is one or more. |
|  | `Total <= 1000` | Returns true if total is less than or equal to 1000. |
|  | `Status == "Active"` | Returns true if status equals “Active.” |
|  | `Name != "Test"` | Returns true if name is not “Test.” |
| **Boolean Operators** | `IsActive && HasPermission` | Returns true only if both conditions are true. |
|  | `Status == "Active" || Status == "Pending"` | Returns true if status is “Active” or “Pending.” |
|  | `!IsDeleted` | Returns true if the record is not deleted. |
|  | `Amount > 0 && Amount < 1000` | Returns true if amount is between 0 and 1000. |
| **Ternary Operator** | `Amount > 100 ? "High" : "Low"` | Returns “High” if amount > 100, otherwise “Low.” |
|  | `IsActive ? 1 : 0` | Returns 1 if active, 0 if inactive. |
|  | `Status == "Active" ? Amount * 0.1 : 0` | Calculates a 10% value if active, else 0. |
| **Expression Grouping** | `(Amount + Tax) * Quantity` | Groups addition before multiplication for correct order. |
|  | `((Price * Quantity) - Discount) * TaxRate` | Calculates total tax-adjusted value with proper grouping. |

---
