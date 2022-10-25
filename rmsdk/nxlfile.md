[Home](..\Home.md)

# [RMSDK](rmsdk.md) -> [Format](format.md) -> NXLFile #

## 1. Namespace

```cpp
namespace RMSDK::NXLFMT;
```

## 2. Const and Enumerate

### 2.1 enum FileError

Define error code used by NXLFile classes.

## 3. Structs

N/A

## 4. Classes

### 4.1 class TokenId

```cpp
class TokenId;
```

**Variables**

| variable | type | description |
|-|-|-|
| id | std::vector<uint8_t> | token's id, must be 16 bytes |
| level | uint32_t | token's id maintainence level, default is zero |

**Functions**

| prototype | return | description |
|-|-|-|
| TokenId() | N/A | default constructor |
| TokenId(const std::vector<uint8_t>&, const uint32_t) | N/A | copy constructor |
| empty() | bool | is token id empty? |
| clear() | void | clear token id |
| getId() | const std::vector<uint8_t>& | get token id |
| getLevel() | uint32_t | get token level |

### 4.2 class Token

```cpp
class Token : public TokenId;
```

**Variables**

| variable | type | description |
|-|-|-|
| key | std::vector<uint8_t> | token's id, must be 32 bytes |

**Functions**

| prototype | return | description |
|-|-|-|
| Token() | N/A | default constructor |
| Token(const std::vector<uint8_t>&, const uint32_t, const std::vector<uint8_t>&) | N/A | cconstructor |
| Token(const Token&) | N/A | copy constructor |
| empty() | bool | is token empty? |
| clear() | void | clear token |
| getId() | const std::vector<uint8_t>& | get token id |
| getLevel() | uint32_t | get token level |
| getKey() | const std::vector<uint8_t>& | get token key |

### 4.3 class Header

```cpp
class Header : public NXL_HEADER2;
```

**Variables**

| variable | type | description |
|-|-|-|
| | | |

**Functions**

| prototype | return | description |
|-|-|-|
| Header() | N/A | default constructor |
| ~Header | N/A | deconstructor |
| validate() | FileError | validate NXL header |
| init() | FileError | initialize header |
| findSection() | NXL_SECTION2* | find section by given name |

### 4.4 class File

```cpp
class File;
```

**Variables**

| variable | type | description |
|-|-|-|
| | | |

**Functions**

| prototype | return | description |
|-|-|-|
| File() | N/A | default constructor |
| ~File | N/A | deconstructor |
| good() | bool | is file in good condition? |
| opened() | bool | is file opened? |
| getError() | FileError | get operation error |
| validate() | bool | static; validate given file |
| create() | bool | create a new file |
| open() | bool | open an existing file |
| close() | void | close file object |