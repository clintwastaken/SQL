# SQL assignment 1
Explorer Mode

1. How many users are there?
    select count (id) from users

2. What are the 5 most expensive items?
    select * from items order by price asc limit 5 offset 95

3. a. What’s the cheapest book?
        select * from items where category = "Books" order by price asc limit 1

    b. Does that change for "category is exactly 'book'" versus "category contains 'book'"?
        ?   ?   ?

4. a. Who lives at "6439 Zetta Hills, Willmouth, WY"? 
        select * from addresses join users on addresses.user_id = users.id where street = "6439 Zetta Hills"

    b. Do they have another address?
        select * from addresses join users on addresses.user_id = users.id where user_id = 40

5. Correct Virginie Mitchell's address to "New York, NY, 10108".
    update addresses set city = "New York" , zip = 10108 where id = 41

6. How much would it cost to buy one of each tool?
    select sum (price) as "Cost for one of each" from items where category = "Tools"

7. How many total items did we sell?
    select sum (quantity) as "Total units ordered" from orders

8. How much was spent on books?
    select sum(price) from items join orders on items.id = orders.item_id where category = "Books"


9. Simulate buying an item by inserting a User for yourself and an Order for that User.
    insert a user - 
    insert into users values (51, "Clinton", "Wessinger", "clint@email.com")

    insert an order for that user - 
    insert into orders values (378, 51, 8, 5, CURRENT_TIMESTAMP)


Adventurer Mode

1. a. What item was ordered most often? 
        select * from orders join items on orders.item_id = items.id where quantity > 9

    b. Grossed the most money?

2. What user spent the most?

3. What were the top 3 highest grossing categories?
