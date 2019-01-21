# python-sals-shipping

Build a program that will take the weight of a package and determine the cheapest way to ship that package using Sal's Shippers

## Technology used

- `python3`

## What This Application Does

- Use control flow to convert a pricing table into a logic of a program

Here are the given prices:
**Ground Shipping**
| Weight of Package | Price per Pound | Flat Charge |
| ------------- | ------------- | ------------- |
| 2 lb or less | $1.50  | $20.00 |
| Over 2 lb but less than or equal to 6 lb | $3.00  | $20.00 |
| Over 6 lb but less than or equal to 10 lb | $4.00  | $20.00 |
| Over 10 lb | $4.75  | $20.00 |

```
def shipping_cost_ground(weight):
    if weight <= 2:
        price_per_pound = 1.50
    elif weight <= 6:
        price_per_pound = 3.00
    elif weight <= 10:
        price_per_pound = 4.00
    else:
        price_per_pound = 4.75
    return 20 + (price_per_pound * weight)
```

**Drone Shipping**
| Weight of Package | Price per Pound | Flat Charge |
| ------------- | ------------- | ------------- |
| 2 lb or less | $4.50	  | $0.00 |
| Over 2 lb but less than or equal to 6 lb | $9.00  | $0.00 |
| Over 6 lb but less than or equal to 10 lb | $12.00  | $0.00 |
| Over 10 lb | $14.25  | $0.00 |

```
def shipping_cost_drone(weight):
    if weight <= 2:
        price_per_pound = 4.50
    elif weight <= 6:
        price_per_pound = 9.00
    elif weight <= 10:
        price_per_pound = 12.00
    else:
        price_per_pound = 14.25
    return price_per_pound * weight
```

**Premium Ground Shipping**
Flat charge: \$125.00

```
shipping_cost_premium = 125.00
```

Note: The cost of premium ground shipping is assigned to a variable. This does not need to be a function because the price of premium ground shipping does not change with the weight of the package.

- Write a function that take `weight` as a parameter and print out the best shipping method along with the cost

```
def print_cheapest_shipping_method(weight):

    ground = shipping_cost_ground(weight)
    premium = shipping_cost_premium
    drone = shipping_cost_drone(weight)

    if ground < premium and ground < drone:
        method = "standard ground"
        cost = ground
    elif premium < ground and premium < drone:
        method = "premium ground"
        cost = premium
    else:
        method = "drone"
        cost = drone
    print(
        "The cheapest option available is $%.2f with %s shipping."
        % (cost, method)
    )
```
