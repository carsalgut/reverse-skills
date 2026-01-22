---
description: Analyze function symbols from binaries, libraries, or decompiled code
---

# rev-symbol

Analyze the given function symbol for reverse engineering purposes.

## Analysis Steps

1. **Symbol Identification**
   - Parse the symbol name (mangled or demangled)
   - Identify the calling convention
   - Determine the symbol type (function, variable, vtable, etc.)

2. **Name Demangling**
   - If C++ mangled name, demangle to readable format
   - Extract namespace, class, and function name
   - Identify template parameters if present

3. **Signature Analysis**
   - Analyze parameter types and return type
   - Identify pointer levels and references
   - Note any const/volatile qualifiers

4. **Context Inference**
   - Guess the purpose based on naming conventions
   - Identify common patterns (getter/setter, constructor/destructor, etc.)
   - Suggest related symbols that might exist

## Output Format

Provide analysis in the following structure:

```
Symbol: <original symbol>
Demangled: <demangled name if applicable>
Type: <function/variable/vtable/etc>
Return Type: <return type>
Parameters: <parameter list with types>
Calling Convention: <cdecl/stdcall/fastcall/thiscall/etc>
Namespace/Class: <if applicable>
Purpose: <inferred purpose>
Related Symbols: <suggested related symbols>
```

## Usage

User will provide a symbol like:
- `_ZN5boost6system14error_categoryD2Ev`
- `sub_140001234`
- `?GetInstance@Singleton@@SAPEAV1@XZ`

Analyze and explain the symbol in detail.
