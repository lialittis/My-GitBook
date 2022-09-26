# Preparation

To constuct your own tiny STL, you may need to create a self namespace and type traits to realize generic programming in C++.

By extending `type_traits` of C++ STL, you could get the basic type traits and those you want to define by yourself.

```cpp
#include <type_traits>

namespace mystl
{
/* helper struct */
template <typename T, T v>
struct m_integral_constant  // a struct template(specific type trait) to set value by given typename
{
    static constexpr T value = v;
};

template <bool b>  // nontype parameter
using m_bool_constant = m_integral_constant<bool, b>;

typedef m_bool_constant<true> m_true_type;
typedef m_bool_constant<false> m_false_type;

/* type traits */
// is_pair
template <typename T1, typename T2>
struct pair;

template <typename T>
struct is_pair : mystl::m_false_type {};  // initialization list

template <typename T1, typename T2>
struct is_pair<mystl::pair<T1,T2>> : mystl::m_true_type {}; // initialization list
}
```

