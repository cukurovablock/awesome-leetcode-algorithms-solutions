# [✅ Double Stack to solve the 🧑🏻‍💻 Min Stack Problem on 🦀 RUST language]()

## 🧑🏻‍💻 Approach

`new()`: This is the constructor method that creates a new instance of `MinStack` by initializing an empty `Vec` using `Vec::new()`.

`push(&mut self, val: i32)`: This method takes an integer value `val` as a parameter and adds it to the top of the stack by using the `push` method of the underlying `Vec`.

`pop(&mut self)`: This method removes the top element from the stack by using the `pop` method of the underlying `Vec`.

`top(&self) -> i32`: This method returns the value of the top element of the stack without removing it. It uses the `last` method of the `Vec` to get a reference to the last element and then dereferences it with `*` to obtain the value.

`get_min(&self) -> i32`: This method returns the minimum value in the stack. It uses the `iter` method of the `Vec` to create an iterator over the elements, and then calls the `min` method to find the minimum value. The minimum value is obtained by calling `unwrap` on the result, assuming that the stack is not empty.

## 🔐 Code

``` RUST
#[derive(Debug)]
struct MinStack {
    stack:Vec<i32>

}
/** 
 * `&self` means the method takes an immutable reference.
 * If you need a mutable reference, change it to `&mut self` instead.
 */
impl MinStack {

    fn new() -> Self {
        MinStack { stack: Vec::new() }
    }
    
    fn push(&mut self, val: i32) {
        self.stack.push(val);
        
    }
    
    fn pop(&mut self) {
        self.stack.pop();
        
    }
    
    fn top(&self) -> i32 {
        *self.stack.last().unwrap()
    }
    
    fn get_min(&self) -> i32 {
        *self.stack.iter().min().unwrap()
    }
}
```

