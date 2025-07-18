# BinaryHeap

Defined in binary-heap@0.1.1

This module provides a [binary heap](https://en.wikipedia.org/wiki/Binary_heap) implementation.

## Values

### namespace BinaryHeap::BinaryHeap

#### empty

Type: `p -> BinaryHeap::BinaryHeap p e`

Create an empty heap.

The first argument is the priority object.

#### get_size

Type: `BinaryHeap::BinaryHeap p e -> Std::I64`

Get the size of the heap.

#### get_top

Type: `BinaryHeap::BinaryHeap p e -> Std::Option e`

Get the most prioritized element in the heap.

This function returns `none()` if the heap is empty.

This function does not remove the element.

#### pop

Type: `[p : BinaryHeap::Priority, BinaryHeap::Priority::Elem p = e] BinaryHeap::BinaryHeap p e -> BinaryHeap::BinaryHeap p e`

Pop the most prioritized element from the heap.

#### push

Type: `[p : BinaryHeap::Priority, BinaryHeap::Priority::Elem p = e] e -> BinaryHeap::BinaryHeap p e -> BinaryHeap::BinaryHeap p e`

Push an element to the heap.

### namespace BinaryHeap::MaxBinaryHeap

#### empty

Type: `BinaryHeap::MaxBinaryHeap e`

Create an empty maximum heap.

### namespace BinaryHeap::MinBinaryHeap

#### empty

Type: `BinaryHeap::MinBinaryHeap e`

Create an empty minimum heap.

### namespace BinaryHeap::Priority

#### compare

Type: `[p : BinaryHeap::Priority] BinaryHeap::Priority::Elem p -> BinaryHeap::Priority::Elem p -> p -> Std::Bool`

Compare two elements.

Returns true iff the first element has less priority than the second element.

## Types and aliases

### namespace BinaryHeap

#### BinaryHeap

Defined as: `type BinaryHeap p e = unbox struct { ...fields... }`

The binary heap.

The first type parameter is the type of the priority object to be used.
The type must implement the `Priority` trait.

The priority objects that prioritize the maximum or minimum value based on comparison with the `LessThan` trait are
provided in this module (`PriorityMaximum` and `PriorityMinimum`).
It is recommended to use the `MaxBinaryHeap` and `MinBinaryHeap` type aliases when using them.

##### field `_d`

Type: `Std::Array e`

##### field `_p`

Type: `p`

#### MaxBinaryHeap

Defined as: `type MaxBinaryHeap e = BinaryHeap::BinaryHeap (BinaryHeap::PriorityMaximum e) e`

The maximum binary heap.

#### MinBinaryHeap

Defined as: `type MinBinaryHeap e = BinaryHeap::BinaryHeap (BinaryHeap::PriorityMinimum e) e`

The minimum binary heap.

#### PriorityMaximum

Defined as: `type PriorityMaximum e = unbox struct { ...fields... }`

Priority object that prioritizes the larger element under comparison by `LessThan`.

#### PriorityMinimum

Defined as: `type PriorityMinimum e = unbox struct { ...fields... }`

Priority object that prioritizes the smaller element under comparison by `LessThan`.

## Traits and aliases

### namespace BinaryHeap

#### trait `p : Priority`

The trait for priority objects.

##### type `Elem`

Defined as: `Elem p`

The element to be compared.

##### method `compare`

Type: `BinaryHeap::Priority::Elem p -> BinaryHeap::Priority::Elem p -> p -> Std::Bool`

Compare two elements.

Returns true iff the first element has less priority than the second element.

## Trait implementations

### impl `[e : Std::LessThan] BinaryHeap::PriorityMaximum e : BinaryHeap::Priority`

### impl `[e : Std::LessThan] BinaryHeap::PriorityMinimum e : BinaryHeap::Priority`