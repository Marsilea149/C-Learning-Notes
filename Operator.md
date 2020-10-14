To overload multiply operator:


- Multiplication by a scalar on the right 
Inside of the class, create a member function for that:

    template <typename T>
    Matrix<T> operator*(T scalar) {
        return matrix * scalar;
    }


- Multiplication by a scalar on the left 

You'll need a non-member function for that:

    template <typename T>
    Matrix<T> operator*(T scalar, Matrix<T> const & matrix) {
        return matrix * scalar;
    }
Non-member operator overloads allow you to specify any type on either side, while member overloads always get the object on the left-hand side.
