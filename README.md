# Dandi Rizky E-Commerce Design <img src="https://raw.githubusercontent.com/DandiRizkyy/slackmoji/master/emoji/blob/blob-wave-gif.gif" width="50px" height="50px" alt="hello">

---

## High Level Design 📶

---

![Activity Diagram](/assets/activity-diagram.png)

![Given Product ID and Return Product Details](/assets/given-id.png)

In this section, im creating a High Level Design using MVC (Model - View - Controller) Architecture. It explain the flow of the program when given certain ID and returning them in the end. The reason why im using MVC architecture is because it's advantage in scaling into larger applications, dependable and easy to maintain.

### Creating Order 📁

![Create Order](/assets/creating-order.png)

Image above shows the flow of the create order using sequence diagrams.

```
Pseudocode Version 1 :

1. Create function "createOrder()"
2. Inside those function, create new variable "totalProcess" and "paymentMethod" for payment process using paymentAPI.
4. Declare boolean expression for payment method (if else)
5. If the payment successful, return Success. If the payment failed, return PaymentError.
6. Create new function "calculatePrice(basket)" and create an array inside of it.
7. Set totalPrice to 0
8. Do a for loop through each array, add price to totalPrice and substract 1 from each item of product
9. Return the value of totalPrice and updated product.

Pseudocode Version 2 :

function createOrder(){
    let totalProcess = calculatePrice(basket)
    let paymentMethod = usePaymentAPI(totalProcess)

    if (payment.isSuccesfull) {

        return Success
    }
    else {

        return PaymentError
    }
}

calculatePrice(basket){
    let totalPrice = 0
    for each product in basket:
        totalPrice = totalPrice + (product * price)
        product.stock -= 1

        return totalPrice
}

```

### Complexity Analysis 📐

Complexity Analysis for `calculatePrice()` function is $O(n)$, because they have loop and we need to iterate through each of the items inside those array. It means those loop have input of $n$, and n input means the number of operation will grow based on the number of input which is $n$.
