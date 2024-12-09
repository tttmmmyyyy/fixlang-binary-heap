# `module Test`

# Types and aliases

## `namespace Test`

### `type TargetPriority = unbox struct { ...fields... }`

Priority that prioritizes the value close to the target.

#### field `target : Std::I64`

# Traits and aliases

# Trait implementations

### `impl Test::TargetPriority : BinaryHeap::Priority`

# Values

## `namespace Test`

### `test : Std::IO ()`

### `test_common : Std::IO ()`

### `test_dynamic_priority : Std::IO ()`

### `test_maximum : Std::IO ()`

### `test_minimum : Std::IO ()`

## `namespace Test::TargetPriority`

### `@target : Test::TargetPriority -> Std::I64`

Retrieves the field `target` from a value of `TargetPriority`.

### `act_target : [f : Std::Functor] (Std::I64 -> f Std::I64) -> Test::TargetPriority -> f Test::TargetPriority`

Updates a value of `TargetPriority` by applying a functorial action to field `target`.

### `mod_target : (Std::I64 -> Std::I64) -> Test::TargetPriority -> Test::TargetPriority`

Updates a value of `TargetPriority` by applying a function to field `target`.

### `set_target : Std::I64 -> Test::TargetPriority -> Test::TargetPriority`

Updates a value of `TargetPriority` by setting field `target` to a specified one.