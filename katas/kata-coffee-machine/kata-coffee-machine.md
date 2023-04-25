# Coffee Machine Kata.
 (Recommended by Lamaar for  Refactoring, Pair Programming)

In this Coffee Machine kata, your task is to write and implement a coffee machine's Logic component.

![CoffeeMachine](https://user-images.githubusercontent.com/88356693/152094581-2533d0e8-01ea-4224-872c-bc8af6edd85e.png)

The coffee machine's Pad will cover taking orders from the customer, and you are free to define the API that the Pad will use to talk to the Logic component. For instance, it could be a simple object or a simple string that contains the order details. Try to think of the simplest approach to meet the requirements.

The Drink Maker component, however, has already been designed and implemented. It is capable of making a tea, a coffee or a hot chocolate. It also has an integrated screen for displaying message. Being hardware people, the software interface they've provided for the Logic component to use is low-level:

```C#
public interface IDrinkMaker
{
   void SendCommand(string command);
}
```

Along with this, they have provided the following brief documentation:

| Command             | Description                                        |
|---------------------|----------------------------------------------------|
| `T:1:1`             | Make 1 tea with 1 sugar and a stick                |
| `H:0:0`             | Make 1 hot chocolate with no sugar and no stick    |
| `C:2:1`             | Make 1 coffee with 2 sugars and a stick            |
| `M:message-content` | Display `message-content` on the integrated screen |

Your job is to ensure that orders are translated for the drink maker based on the requirements given in each iteration below. YAGNI rules in this kata!

This kata is structured in a way to help improve skills in expanding and refactoring an application, so it is important to work through each iteration individually and to not read ahead.

## Iterations

1) First iteration: Making Drinks
2) Second iteration: Going into business
3) Third iteration: Extra hot
4) Fourth iteration: Making money
5) Fifth iteration: Running out

--------------------------------------------------------------------------------------------------------------------------------

### First iteration - Making drinks

The coffee machine can serve 3 type of drinks: tea, coffee and chocolate.

#### Requirements

* The drink maker should receive the correct instructions for coffee, tea or chocolate orders
* The drink maker should be able to receive instructions to add one or two sugars
* When an order contains sugar, the drink maker should add a stir stick

#### Implementation details

At this stage, you should be focused on meeting the requirements with the simplest approach you can. Just be sure to adopt good TDD practices by writing your tests before you start building out your protocol translator logic.

--------------------------------------------------------------------------------------------------------------------------------

### Second iteration - Going into business

The coffee machine is not free anymore! Tea is $4, coffee is $5.50 and chocolate is $6.

#### Requirements

* The drink maker will now only make a drink if enough money is "inserted"
* If not enough money is given, a message should be sent to the drink maker
  * This message should include the amount of money the customer still needs to insert

Remember that the drink maker forwards any message received onto a display screen on the coffee machine for the customer to see.

If a customer inserts too much money, the drink maker will still make the drink according to instructions. We will assume that some other component of the coffee machine will handle giving correct change to the customer, so you do not need to implement any of this functionality yourself. You should only be making sure that drink orders are being fulfilled once the correct amount of money is inserted, and that customers receive a message prompting them to insert the remaining amount of money needed to complete their order.

--------------------------------------------------------------------------------------------------------------------------------

### Third iteration - Extra hot

The machine has been upgraded! The drink maker can now make extra hot drinks and can also receive orders for orange juice. Here are the new protocol commands added to the drink maker's firmware:

| Command  | Description                                         |
|----------|-----------------------------------------------------|
| `O:0:0`  | Make 1 orange juice                                 |
| `Ch:0:0` | Make 1 extra hot coffee with no sugar and no stick  |
| `Hh:1:1` | Make 1 extra hot chocolate with 1 sugar and a stick |
| `Th:2:1` | Make 1 extra hot tea with 2 sugar and a stick       |

You have to update your code to send the correct commands to the drink maker so that customers can order orange juice or their drinks extra hot.

Let us see if your implementation is flexible enough to welcome those changes without too much hassle.

#### Requirements
* Customers should be able to buy an orange juice for $4.50
* Customers should be able to order their coffee, chocolate or tea extra hot

--------------------------------------------------------------------------------------------------------------------------------

### Fourth iteration - Making money

The machine is becoming popular in the office. Management is eager to get daily reports on what is sold and when.

#### Requirements
* Add functionality to generate an up-to-date report for previous sales: how many of each drink was ordered and the total amount of money earned from these transactions

#### Implementation details

The report does not need to be overly complex but should meet the requirements given above. This might mean simply introducing functionality to print the required report information to the console. Go with whatever approach works best for you. As with previous iterations, be sure to follow good TDD practices and write your tests before starting.

--------------------------------------------------------------------------------------------------------------------------------

### Fifth iteration - Running out

The users of the coffee machine are complaining that there is often a shortage of water and/or milk. It takes weeks before the machine is refilled. Your product owner wants you to take advantage of the machine's capabilities by informing the user that there is a shortage, and by sending an email notification to the company so that they can have the machine refilled.

#### Requirements
* When a drink is ordered but can't be fulfilled because of a water/milk shortage, a message should be sent to the coffee machine display to notify the user of the shortage
* The message should also tell them that a notification has been sent to the company so that they can have the machine refilled

#### Implementation details

You can take advantages of the two services implemented by the coffee machine:

```C#
public interface IEmailNotifier
{
    void NotifyMissingDrink(string drink)
}
```

```C#
public interface IBeverageQuantityChecker
{
    bool IsEmpty(string drink)
}
```
 
Add these two services to your project and use mocking to complete the kata.

### References

[Based off the Coffee Machine Kata on GitHub](http://simcap.github.io/coffeemachine/index.html) 
