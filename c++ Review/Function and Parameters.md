# Function and Parameters
## Pass By Value
When you pass by value into a function, a new variable will be created and so modification of the passed-in objects will not happen. This is safe and ensures that there will always be a valid object that is passed in. This method will be slow and less efficient because it will need extra memory to store the copy of the object passed in, especially if the object is very large.

**Example**
```C++
void swap_values(int x, int y) {
   // swaps x and y 
   int temp = x; 
   x = y;    
   y = temp; 
}

int main () {
   int a = 128;
   int b = 225;
 
   swap_values(a, b);
   
   cout << "After swap, a is : " << a << endl;
   cout << "After swap, b is : " << b << endl;
   
   return 0;
}
```
**Will Return**
```
After swap, a is : 128
After swap, b is : 225
```

## Pass By  Pointer
When you pass by pointer into a function, you are passing in the address of the object. This will be allow you to change the original data if you dereference the pointer. This method is more efficient compared to pass by value; however, it is more risky as you can pass in an invalid parameter such as NULL.

**Example**
```C++
void swap_values(int *x, int *y) {
   // swaps x and y
   int temp = *x;
   *x = *y;
   *y = temp;
}

int main () {
   int a = 128;
   int b = 225;
 
   swap_values(&a, &b);
   
   cout << "After swap, a is : " << a << endl;
   cout << "After swap, b is : " << b << endl;
   
   return 0;
}
```
**Will Return**
```
After swap, a is : 225
After swap, b is : 128
```

## Pass By Reference
When you pass by reference into a function, you are passing in another name, or alias, for the object. This means that nothing is actually being copied. Because you passed in the alias, you are able to modify the original object. This is efficient and will always use the same amount of memmory (the size of a pointer) but also risky because you are changing the original value. There will always be a object passed, unless it's NULL in which case, no.

```C++
void swap_values(int &x, int &y) {
   // swaps x and y
   int temp = x;
   x = y;
   y = temp;
}

int main () {
   int a = 128;
   int b = 225;
 
   swap_values(&a, &b);
   
   cout << "After swap, a is : " << a << endl;
   cout << "After swap, b is : " << b << endl;
   
   return 0;
}
```
**Will Return**
```
After swap, a is : 128
After swap, b is : 225
```

## Pass by Const Reference
When you pass by const reference into a function, it is similar to passing by reference. The only change is that the const modifier will prevent you from modifying the original object. Any effort to modify the original object in the function will not compile. This method is very safe, although you still run the risk of passing in an invalid NULL.

**Example**
```C++
void swap_values(const int &a , const int &b) {
   // do things here, but you can not change a or b 
}
```
