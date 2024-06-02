# C_Daily_Code_Review
## I will learn C in a short period of time 
## What i have learned on 2/6/2024
## 1. C++ Output
- **Namespace**
  - Is a region that is used to contain variables, functions, or other user-defined data types that is related to each other.
  - Multiple namespace blocks with the same name are allowed, but the name of the variable inside the namespace must be different from other namespace.
  ``` cpp
    #include <iostream>
  
    const int PI = 10; // Which PI variable do you think it will use, in the namespace or out of namespace? The answer will be inside the namspace
  
    namespace math // I can set the same name for the namespace
    {
      const float PI = 1; // But the name of the variable must be different, other wise it is conflict
      float circleArea(float r)
      {
        return PI * r * r;
      }
    }
    
    namespace math // I can set the same name for the namespace
    {
      const float PI1 = 3; // But the name of the variable must be different, other wise it is conflict
      float circleArea1(float r)
      {
        return PI1 * r * r;
      }
    }
    
    int main()
    {
      std::cout << math::circleArea(12) << "\n";
    }
  ```
- **The reasons why should use ***std::*** instead of define ***using namespace std*** in the header**
  - **std** stands for standard in C++, and this standard library such as (e.g., <iostream>, <vector>, <algorithm>) contain some function that will be used as default or will be developed more in the future
  - But the conflict case happens when one of you programming contain the name of the function that is already define in those library, so it could lead to name conflict.
  - It is okey to use this ***using namespace std*** in the small code, but in the large project => please do not use, because you never want to find bug.
    ```cpp
      #include <iostream>
      
      using namespace std;
      
      void cout()
      {
        std::cout << "I try to make anther cout function";
      }
      
      int main ()
      {
        cout << "Hello word"; // This will be error because you have created th cout() method already => it is naming conflict
        return 0;
      }
    ```
- **Print text**
  ``` cpp 
    #include <iostream>
    
      int main() {
      std::cout << "Hello, World!";
      return 0;
      }
  ```
- **New line**
  ``` cpp 
    #include <iostream>
    
    int main() {
      std::cout << "Hello, World! \n"
      std::cout << "I am learning C++";
      return 0;
    }
  ```
## 2. C++ Condition
  - **If**
    - Use ***if*** to specify a block of code to be executed if the given condtion is true
      ```cpp
        if (condition)
        {
          // block of code to be executed if the condition is true
        }
      ```
  - **else**
    - Use ***else*** to specify a block of code to be excuted if the given condtion is false
      ```cpp
        if(condition)
        {
          // block of code to be executed if the condition is true
        }
        else
        {
          // block of code to be excuted if the condition is false 
        }
      ```    
