redis-counter
=============

redis-counter parse redis rdb file, count deleted keys, other keys and saved keys. Save key value pair into aof files.

Key-value **format** saved in aof files and **hash** strategy for which file current key-value pair go.

The **format** and **hash** strategy can be defined in:
    
```c

/**
 * @brief _format_kv
 * Format a string with key and value, the string is to be dumped in aof file.
 * Define a way to get a aof file number from hashing key.
 * @param key
 * @param key_len
 * @param value
 * @param hashed_key
 * Save hashed aof file number of type int.
 * @return Formatted string of k&v
 */
typedef char * format_kv_handler(void * key, int key_len, long value, void *hashed_key);

```
