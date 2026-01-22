---
description: Analyze and reconstruct data structures from decompiled functions
---

# rev-struct

Analyze data structures within the given decompiled function or memory layout.

## Analysis Steps

1. **Memory Access Pattern Analysis**
   - Identify base pointer + offset patterns
   - Track structure member accesses
   - Note array access patterns

2. **Type Reconstruction**
   - Infer field types from operations performed
   - Determine field sizes from access widths
   - Identify pointer vs value fields

3. **Structure Layout**
   - Calculate structure size
   - Determine field offsets
   - Account for alignment and padding

4. **Semantic Analysis**
   - Infer field purposes from usage
   - Identify common structure patterns (linked list, tree, vtable, etc.)
   - Match against known structure signatures

## Output Format

```c
// Reconstructed structure
// Total size: <size> bytes
// Alignment: <alignment>

struct <suggested_name> {
    /* 0x00 */ <type> <field_name>;    // <inferred purpose>
    /* 0x08 */ <type> <field_name>;    // <inferred purpose>
    // ... more fields
};
```

## Common Patterns to Recognize

- **C++ Object**: vtable pointer at offset 0
- **Linked List Node**: next/prev pointers
- **Reference Counted**: refcount field
- **String**: pointer + length or null-terminated buffer
- **Vector/Array**: data pointer + size + capacity

## Usage

User will provide:
- Decompiled pseudocode from IDA/Ghidra/Binary Ninja
- Memory dump with annotations
- Assembly snippets with structure access

Reconstruct the structure definition with explanations.
