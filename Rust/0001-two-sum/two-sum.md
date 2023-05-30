# Brute Force to solve the Two-Sum Problem on Rust language

## Approach
<!-- Describe your approach to solving the problem. -->
The brute-force approach to solving the two-sum problem involves checking every possible pair of elements in the array and comparing their sum to the target. This can be achieved by using two nested loops, where each loop iterates through all the elements in the array. In each iteration, the current pair of elements is checked to see if their sum is equal to the target. If a match is found, the indices of the elements are stored and returned as the solution. The idea is to go through all the possible combinations of elements and check if any of them add up to the target. It's a straightforward approach that doesn't require any complex algorithms or data structures, making it easy to understand and implement.

## Complexity

- Time complexity:
<!-- Add your time complexity here, e.g. $O(n)$ -->
The time complexity of the brute-force approach for solving the two-sum problem is $O(n^2)$, where n is the size of the input array. This means that the algorithm's performance will be proportional to the square of the size of the array.

In each iteration of the outer loop, the inner loop will also iterate through all the elements in the array. So, the number of operations performed by the algorithm is proportional to the product of the number of iterations of the outer loop and the inner loop. The outer loop iterates n times, and the inner loop iterates $n-1$ times on the first iteration, $n-2$ times on the second iteration, and so on. So, the total number of iterations is $n * (n-1) / 2$, which is equivalent to $n^2/2 - n/2$. This results in a time complexity of $O(n^2)$.

This means that as the size of the array grows, the number of operations performed by the algorithm will increase rapidly, making it inefficient for large arrays.

- Space complexity:
<!-- Add your space complexity here, e.g. $O(n)$ -->
The space complexity of the brute-force approach for solving the two-sum problem is $O(1)$. This means that the amount of memory used by the algorithm is constant and does not depend on the size of the input array.

In this approach, we use two integer variables, `i` and `j`, to store the indices of the elements in the array. These variables are used as pointers to access the elements in the array and do not increase in size as the size of the array grows.

We also use a constant amount of memory to store the answer, which is an array of two integers. This array is dynamically allocated using malloc, and its size does not depend on the size of the input array.

Therefore, the space complexity of the algorithm is $O(1)$, which means that it uses a constant amount of memory, regardless of the size of the input array.

## Code

``` Rust
fn two_sum(a:Vec<i32>, hedefsayi:i32){
    
    let girdi = a.iter();

    for i in girdi.clone().enumerate(){
        for j in girdi.clone().enumerate() {
            if i.0 == j.0{
                break;
            }
            let mut cikti:Vec<i32> = Vec::new();
            if i.1+j.1 == hedefsayi{
                cikti.push(i.0 as i32);
                cikti.push(j.0 as i32);
                println!("{:?}",cikti);

                break;
                
            }
        }
    }   
}   
```
