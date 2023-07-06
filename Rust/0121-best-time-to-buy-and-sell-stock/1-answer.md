# [✅ Double Stack to solve the 🧑🏻‍💻 Best Time to Buy and Sell Stock Problem on 🦀 RUST language](#)

## 🧑🏻‍💻 Approach

The function `max_profit` takes a vector of integers `prices` as input and returns an integer representing the maximum profit that can be obtained from buying and selling a stock.

The code begins by initializing two variables, `min_price` and `max_profit`. `min_price` is set to the maximum possible integer value initially, while `max_profit` is set to 0.

The `for` loop iterates through each element `i` in the `prices` vector. Inside the loop, the code checks if the current price `i` is less than the current minimum price `min_price`. If it is, the `min_price` is updated to `i`, indicating that this is the new lowest price encountered so far.

On the other hand, if the current price `i` is not less than the current minimum price, the code proceeds to check if the difference between `i` and `min_price` is greater than the current maximum profit `max_profit`. If it is, the `max_profit` is updated to the new higher profit, representing a better opportunity to sell the stock and maximize the gain.

Once the loop completes, the final value of `max_profit` represents the maximum possible profit that could be achieved by buying the stock at the lowest price and selling it at the highest price.

Finally, the function returns the calculated `max_profit`.

## 🔐 Code

``` rust
impl Solution {
    pub fn max_profit(prices: Vec<i32>) -> i32 {
        let mut count = 0;



    let mut min_price = i32::max_value();
  let mut max_profit = 0;

  for i in prices{
    if i< min_price{
      min_price = i;
    }
    else if  i - min_price> max_profit{
      max_profit = i - min_price;
    }
  }

  return max_profit;

    }
}
```



