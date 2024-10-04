---
title: "Problem with using UUIDs as Primary Key in MySQL"
categories: UUID, MySQL
author: "Vidya Bhandary"
meta: "#UUID #PrimaryKey #MySQL"
date: 2024-10-04
---

## Learnings about the problems of using UUID as the primary key

[The Problem with Using a UUID Primary Key in MySQL](https://planetscale.com/blog/the-problem-with-using-a-uuid-primary-key-in-mysql)

**Key takeaways**

a. **Performance Issues**: UUIDs can negatively impact database performance due to their size and randomness, which can lead to increased index fragmentation and slower query performance compared to integer-based keys.

b. **Storage Overhead**: UUIDs require more storage space (16 bytes) than typical integer primary keys (4 or 8 bytes), which can lead to larger index sizes and increased disk usage, especially in large datasets.

c. **Complexity in Data Management**: Using UUIDs complicates data management tasks, such as sorting and generating sequential records, making it harder to perform operations that benefit from ordered keys.

**Alternates**

a. **Binary variant:**
Store UUIDs in a binary format (BINARY(16)) instead of as strings (CHAR(36)).

b. **Ordered UUID:**
Use time-based UUIDs such as version 6 or 7.

c. **Built-in SQL UUID:**
MySQL supports generating UUIDs directly within SQL.

d. **Alternate UUID:**
_Snowflake ID_, _ULID_, _NanoID_

---

**Links** :

- [Types of UUIDs](https://github.com/vidyabhandary/til/blob/master/misc/UUIDTypes.md)
