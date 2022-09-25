# Template

Template is the base of C++ generic programming. A template is the bluepicture or formula of a class or a function.

## Function Template

Suppose that you want to build a function to compare two values, you may need multiple functions for different arguments. For examples,

```cpp
int compare(const string &v1, const string &v2)
{
    if(v1 < v2) return -1;
    if(v2 < v1) return 1;
    return 0;
}

int compare(const int &v1, const int &v2)
{
    if(v1 < v2) return -1;
    if(v2 < v1) return 1;
    return 0;
}
```

The two above functions are almost the same, except the type of arguments. So a better way is to define a generic **function template.**

```cpp
template <typename T>
int compare(const T &v1, const T &v2)
{
    if(v1 < v2) return -1;
    if(v2 < v1) return 1;
    return 0;
}
```

The definition of tempate starts by keyword \`template\`, follows by a template parameter list.

The template parameter list shouldn't be empty, it defines several specific local variables but not initializes them. When we use the template, we indicate(implicitly or explicitly) the template arguments for the parameters, at compiling time, the compilor would instantiate a specific version of function by the template arguments detected.

There may be different instantiations of a function template.

### Type Parameters and Nontype Parameters

Type parameters are defined by keyword `typename or class`, nontype parameters are some specific types. For example,

```cpp
template <unsigned N, unsigned M>
int compare(const char (&p1)[N], const char (&p2)[M])
{
    return strcmp(p1,p2);
}
```







