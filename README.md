# E-Commerce-Automation
### Requirements:

App URL: https://v0-ecommerce-feature-flow.vercel.app/

* Part 1: Testing Plan
Write at least 10 test cases describing key user actions related to adding products to the cart and completing checkout. Each should specify expected user behavior and outcomes.

* Part 2: Automated Playwright Test
Choose one test case from Part 1 and implement it as an end-to-end test using cypress. The test must run at desktop resolution.

* Part 3: Delivery Requirements
Create a GitHub repository containing your Playwright automation project.
Implement a CI workflow in GitHub Actions named Regression Pipeline, triggered manually via workflow_dispatch, that runs your Playwright tests.
Integrate a test reporting tool (e.g., Allure Report or another of your choice) into your automation repo.
The CI pipeline must generate and output the test report as part of the workflow.
Expectations
Test cases should focus on key user flows, emphasizing outcomes over implementation details.
The automated test should be robust and reflect real user behavior.
The CI setup should allow manual test runs and clearly present test report results.]

# Solution:

## 📋 Test Cases for Cart & Checkout Flow

| Test Case ID | Description                          | Steps                                                                 | Expected Outcome                                                                 |
|--------------|--------------------------------------|-----------------------------------------------------------------------|---------------------------------------------------------------------------------|
| TC-01        | Add single product to cart           | 1. Navigate to product listing<br>2. Click "Add to Cart"<br>3. Open cart | - Cart count increases by 1<br>- Product appears with correct details           |
| TC-02        | Add multiple products to cart        | 1. Add 3 different products                                           | - Cart count shows 3 items<br>- All products listed                             |
| TC-03        | Remove product from cart             | 1. Add product<br>2. Remove it                                         | - Cart count decreases by 1<br>- Product removed                                |
| TC-04        | Update product quantity              | 1. Add product<br>2. Increase quantity to 2                           | - Cart total shows 2 items<br>- Subtotal recalculated                           |
| TC-05        | Validate empty cart state            | 1. Open empty cart                                                    | - "Your cart is empty" message displayed                                        |
| TC-06        | Apply valid discount coupon          | 1. Add product<br>2. Apply "SAVE10" coupon                            | - Discount applied<br>- Total updated correctly                                 |
| TC-07        | Checkout with valid payment          | 1. Complete checkout with valid info                                  | - Order confirmation shown<br>- Success email received                          |
| TC-08        | Checkout with invalid payment        | 1. Enter invalid card details                                         | - "Invalid payment details" error displayed                                     |
| TC-09        | Persist cart after refresh           | 1. Add items<br>2. Refresh page                                       | - Cart retains all items                                                        |
| TC-10        | Out-of-stock product behavior        | 1. Attempt to add out-of-stock product                                | - "Out of stock" message shown<br>- Add to Cart button disabled                 |

