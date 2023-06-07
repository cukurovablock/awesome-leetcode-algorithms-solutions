# [✅ Double Stack to solve the 🧑🏻‍💻 Min Stack Problem on 🦀 RUST language]()

## 🧩 Complexity

`new()`: This is the constructor method that creates a new instance of `MinStack` by initializing empty vectors for `stack` and `min_stack` using `Vec::new()`.

`push(&mut self, val: i32)`: This method takes an integer value `val` as a parameter and adds it to the top of the `stack` by using the `push` method of the `stack` vector. It also checks if the `min_stack` is empty or if the new value `val` is less than or equal to the current minimum value (`*self.min_stack.last().unwrap()`). If so, it pushes the new value `val` to the `min_stack` as well.

`pop(&mut self)`: This method removes the top element from the `stack` by using the `pop` method of the `stack` vector. It also checks if the removed element is equal to the current minimum value (`*self.min_stack.last().unwrap()`). If so, it removes the minimum value from the `min_stack` as well.

`top(&self) -> i32`: This method returns the value of the top element of the `stack` without removing it. It uses the `last` method of the `stack` vector to get a reference to the last element and then dereferences it with `*` to obtain the value.

`get_min(&self) -> i32`: This method returns the minimum value in the `stack` by accessing the last element of the `min_stack`. It uses the last method of the `min_stack` vector to get a reference to the last element and then dereferences it with `* `to obtain the value.

## 🔐 Code

``` RUST
struct MinStack {
    stack:Vec<i32>,
    min_stack:Vec<i32>
}


/** 
 * `&self` means the method takes an immutable reference.
 * If you need a mutable reference, change it to `&mut self` instead.
 */
impl MinStack {

    fn new() -> Self {
        MinStack { stack: Vec::new(), min_stack: Vec::new() }
    }
    
    fn push(&mut self, val: i32) {
        self.stack.push(val);
        if self.min_stack.is_empty() || val <= *self.min_stack.last().unwrap(){
            self.min_stack.push(val)
        }
    }
    
    fn pop(&mut self) {
        if let Some(x) = self.stack.pop() {
            if x == *self.min_stack.last().unwrap() {
                self.min_stack.pop();
            }
        }
        
    }
    
    fn top(&self) -> i32 {
        *self.stack.last().unwrap()
    }
    
    fn get_min(&self) -> i32 {
        *self.min_stack.last().unwrap()
    }
}
```

