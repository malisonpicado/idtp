# Indexed Data Transfer Protocol (IDTP)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17239894.svg)](https://doi.org/10.5281/zenodo.17239894)


## Introduction

The **Indexed Data Transfer Protocol (IDTP)** introduces a new paradigm for IoT data management by organizing system information as a set of uniquely indexed variables, enabling precise and efficient read/write operations. Unlike traditional transmission-focused protocols, IDTP emphasizes persistence and reliability by maintaining the latest state of each variable and instantly synchronizing updates across all connected devices. This indexed, modular approach ensures real-time communication, minimizes unnecessary data transfer, and provides robust scalability for complex IoT ecosystems.

---

## Protocol Overview

IDTP is based on reading and writing a set of system variables, where each variable is uniquely identified by an index.

Formally, the system is defined as:

$$
V = \\{V_0, V_1, V_2, ..., V_n\\}
$$

Where **V** is a set of variables arranged as a matrix of *N* columns and 1 row, with indices starting at 0. Each variable has an assigned data type, which can vary depending on the access mode configured on the server. Variables can be linked to one or more devices that depend on them, enabling efficient system management and control. Whenever a variable value is updated, the new value is instantly transmitted to all dependent devices. Clients receive updates for all variables in real time, ensuring complete system synchronization.

---

## Version & Status

**Current Specification:** `v0.4.0-beta`  
**Protocol Version Byte (Wire):** `0x00`

> ⚠️ **Note:** This is a beta release.  
> Message format, handshake behavior, and other details may change before `v1.0.0`.  
> Implementations should be considered experimental.

---

## License

This project uses a **custom permissive license**.

**Summary:**
- ✅ Anyone can freely use, implement, modify, or distribute this specification.  
- ✅ Commercial and non-commercial use are allowed without royalties.  
- 🙏 Attribution to the original author is appreciated (but not required).  
- ⚠️ Provided **"as is"**, without any warranty or liability.  

See [LICENSE.md](./LICENSE.md) for full text.

---

## Changelog

### v0.4.0-beta (2025-10-05)

**Changes**: 

1. (+) Added Parameter Indexing
2. Modified Byte 2 of the persistent connection request. Bit 3 declares the optional use of parameter indexing.
3. Changed how device requests are processed based on the parameter indexing option.
4. Better description for the index length of a variable.
5. Added response code: "Parameter indexing enabled, but no parameters were declared".

---

## Contributing

Contributions, proposals, and discussions are welcome!  
Please open issues or pull requests to suggest changes or report problems.  
Future feature proposals may be added under a `proposals/` folder for review before inclusion.
