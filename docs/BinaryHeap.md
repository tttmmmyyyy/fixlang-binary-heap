# `module BinaryHeap`

This module provides a [binary heap](https://en.wikipedia.org/wiki/Binary_heap) implementation.

# Types and aliases

## `namespace BinaryHeap`

### `type BinaryHeap p e = unbox struct { ...fields... }`

The binary heap.

The first type parameter is the type of the priority object to be used.
The type must implement the `Priority` trait.

The priority objects that prioritize the maximum or minimum value based on comparison with the `LessThan` trait are
provided in this module (`PriorityMaximum` and `PriorityMinimum`).
It is recommended to use the `MaxBinaryHeap` and `MinBinaryHeap` type aliases when using them.

#### field `_d : Std::Array e`

#### field `_p : p`

### `type MaxBinaryHeap = BinaryHeap::BinaryHeap (BinaryHeap::PriorityMaximum e) e`

The maximum binary heap.

### `type MinBinaryHeap = BinaryHeap::BinaryHeap (BinaryHeap::PriorityMinimum e) e`

The minimum binary heap.

### `type PriorityMaximum e = unbox struct { ...fields... }`

Priority object that prioritizes the larger element under comparison by `LessThan`.

### `type PriorityMinimum e = unbox struct { ...fields... }`

Priority object that prioritizes the smaller element under comparison by `LessThan`.

# Traits and aliases

## `namespace BinaryHeap`

### `trait p : Priority`

The trait for priority objects.

#### associated type `Elem p`

The element to be compared.

#### method `compare : BinaryHeap::Priority::Elem p -> BinaryHeap::Priority::Elem p -> p -> Std::Bool`

Compare two elements.

Returns true iff the first element has less priority than the second element.

# Trait implementations

### `impl [e : Std::LessThan] BinaryHeap::PriorityMaximum e : BinaryHeap::Priority`

### `impl [e : Std::LessThan] BinaryHeap::PriorityMinimum e : BinaryHeap::Priority`

# Values

## `namespace BinaryHeap::BinaryHeap`

### `@_d : BinaryHeap::BinaryHeap p e -> Std::Array e`

Retrieves the field `_d` from a value of `BinaryHeap`.

### `@_p : BinaryHeap::BinaryHeap p e -> p`

Retrieves the field `_p` from a value of `BinaryHeap`.

### `_at : Std::I64 -> BinaryHeap::BinaryHeap p e -> e`

### `_set : Std::I64 -> e -> BinaryHeap::BinaryHeap p e -> BinaryHeap::BinaryHeap p e`

### `_to_string : [e : Std::ToString] BinaryHeap::BinaryHeap p e -> Std::String`

### `act__d : [f : Std::Functor] (Std::Array e -> f (Std::Array e)) -> BinaryHeap::BinaryHeap p e -> f (BinaryHeap::BinaryHeap p e)`

Updates a value of `BinaryHeap` by applying a functorial action to field `_d`.

### `act__p : [f : Std::Functor] (p -> f p) -> BinaryHeap::BinaryHeap p e -> f (BinaryHeap::BinaryHeap p e)`

Updates a value of `BinaryHeap` by applying a functorial action to field `_p`.

### `empty : p -> BinaryHeap::BinaryHeap p e`

Create an empty heap.

The first argument is the priority object.

### `get_size : BinaryHeap::BinaryHeap p e -> Std::I64`

Get the size of the heap.

### `get_top : BinaryHeap::BinaryHeap p e -> Std::Option e`

Get the most prioritized element in the heap.

This function returns `none()` if the heap is empty.

This function does not remove the element.

### `mod__d : (Std::Array e -> Std::Array e) -> BinaryHeap::BinaryHeap p e -> BinaryHeap::BinaryHeap p e`

Updates a value of `BinaryHeap` by applying a function to field `_d`.

### `mod__p : (p -> p) -> BinaryHeap::BinaryHeap p e -> BinaryHeap::BinaryHeap p e`

Updates a value of `BinaryHeap` by applying a function to field `_p`.

### `pop : [p : BinaryHeap::Priority, BinaryHeap::Priority::Elem p = e] BinaryHeap::BinaryHeap p e -> BinaryHeap::BinaryHeap p e`

Pop the most prioritized element from the heap.

### `push : [p : BinaryHeap::Priority, BinaryHeap::Priority::Elem p = e] e -> BinaryHeap::BinaryHeap p e -> BinaryHeap::BinaryHeap p e`

Push an element to the heap.

### `set__d : Std::Array e -> BinaryHeap::BinaryHeap p e -> BinaryHeap::BinaryHeap p e`

Updates a value of `BinaryHeap` by setting field `_d` to a specified one.

### `set__p : p -> BinaryHeap::BinaryHeap p e -> BinaryHeap::BinaryHeap p e`

Updates a value of `BinaryHeap` by setting field `_p` to a specified one.

## `namespace BinaryHeap::MaxBinaryHeap`

### `empty : BinaryHeap::BinaryHeap (BinaryHeap::PriorityMaximum e) e`

Create an empty maximum heap.

## `namespace BinaryHeap::MinBinaryHeap`

### `empty : BinaryHeap::BinaryHeap (BinaryHeap::PriorityMinimum e) e`

Create an empty minimum heap.

## `namespace BinaryHeap::Priority`

### `compare : [p : BinaryHeap::Priority] BinaryHeap::Priority::Elem p -> BinaryHeap::Priority::Elem p -> p -> Std::Bool`

Compare two elements.

Returns true iff the first element has less priority than the second element.