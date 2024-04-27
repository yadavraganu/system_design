# Hash Join

- Suitable for large/medium size tables/input
- Requires at least one equi join
- Supports all joins (left/right/semi/anti)
- It uses hash functions (input-> hash function-> hashed output)
- It consists of two phases (Build & Probe)
- Needs memory

## Build Phase : 
- For each row in table 1 calculate hash value of equi join columns
- Store row in a hash table, use calculated hash as key

## Probe Phase:
- For each row in table 2, calculate hash value of equi join columns
- Check if hash matches in hash table, then check actual key columns as well (because hash can also match due to hash collision)
- Output hash match

## Memory & Spilling:
- Query optimizer guesses memory required
- Smaller table is build table
- Yet If memory is not sufficient in build phase
   - Hash buckets get written to disk
- If memory is not sufficient in probe phase
   - If target hash bucket is on disk, write probe row to disk as well
   - After in memory probing for batch is over, load spilled rows to memory
   - Recreate hash table & do the normal hash join
- Redo process if run out of memory again