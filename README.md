# Enum17 - A C++17 reflective Enum

Reflection in C++ has always been a tricky issue. If one has an enum, it is generally not possible for the program to know the number of possible enum constants nor the name of the enum constants without vendor specific macros or functions. There have been many tricks to mitigate the lack of reflection, including appending a `SIZE` enum constant at the end or creating a mapping array to match the enum values with the corresponding name. However, this is generally tedious and error prone.

This lightweight and header-only library solves this issue by packaging various generated enum properties with the enum itself. This process is automatic and performed at compilation time. By doing computations at compilation time, their runtime overhead is avoided and the convenience is introduced at a low cost.

This is done with C++ macro expansions, where one can obtain the string used to define the macro. With `std::string_view` and `constexpr`, the processing of the string is done at compilation time to generate the aforementioned mapping and other enum attributes.

## Examples

> Coming soon

## Highlights

- Specification of the underlying type of the enum.
- Obtaining the number of parameters by `Enum::size()`.
- Return the name of the constant by `Enum::to_string()` or with the `<<` operator.
- Convert to the enum by `Enum::from_string()`.
- Implicit conversion to and from the underlying type.
- Direct initialisation from the enum constants specified.
- Supports enum constants having the same value.
  - `Enum::size()` returns the number of unique values.
  - `Enum::to_string()` returns the string with the names of all the enum constants joined together. The joining string can be customised.
  - `Enum::num_raw_params` returns the number of constants specified, including duplicates.
