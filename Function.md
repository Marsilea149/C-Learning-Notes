In C++, when the ref-sign (&) is used before the function name in the declaration of a function it is associated with the return value of the function and means that the function will return by reference.

    int& foo(); // Function will return an int by reference.
When not used within a declaration context, putting the ref-sign before a function name results in calling the address-of operator returning the address of the function. This can be used to e.g. create a pointer to a function.

    // Some function.
    int sum(int a, int b) {
        return a + b;
    }

    int main() {
        // Declare type func_ptr_t as pointer to function of type int(int, int).
        using func_ptr_t = std::add_pointer<int(int, int)>::type;

        func_ptr_t func = &sum; // Declare func as pointer to sum using address-of.
        int sum = func(1, 2);   // Initialize variable sum with return value of func.
    }
    
In C, the only use of & is for the address-of operator. References does not exist in the C language.
