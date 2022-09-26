# Type Traits

## What is Type Traits

From its name, we could understand it as the features of type. Basically, it is used to avoid code explosure, even in generic programming.&#x20;

`is_bool`, `is_integer`, `is_void`, etc. are templated structs, they contains a static const bool value to indicate one specific type's traits. We could use `my_type_trait::value` to check its trait.

For example,

```cpp
template <typename T>
struct is_swapable{
    static const bool value = false;
};

template <>
struct is_swapable<unsigned short>{
    static const bool value = true;
};

template <>
struct is_swapable<short>{
    static const bool value = true;
};

...
```

By `is_swapable<T>::value`, we could check if this type is swapable.

This is how Type Traits work, and in STL of C++, it offers a lot of type traits to evit developers doing this _dirty_ work.



## How  to use Type Traits in C++ STL



By including `type_traits` header file, we could access all pre-defined type traits.





