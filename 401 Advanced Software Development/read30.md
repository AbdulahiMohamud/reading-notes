## HashTable

- Hash is the result of taking a string and converting it into a value for security or other reasons/
- Think of the indexes of the hashtable like a buckets that you organize datat into
- Collisions are when you have more than one key in the same location

- Big O time complexity and is O(1) that allows access to faster than an array
due to precise location created by the hash function based on an items key.

- Hash code is taking the key and turning it into an integer
- Hashtable are created from an array  which has a size of 1024
- Each index of the array contains buckets
- Load factor of a hash table is the
When you have less buckets there is a hire likelihood there will be collisions
- If there are more buckets there is less of a chance that there will be a collision,
but you will have a lot of empty space.
- Add() sends key to getHask (); get an index; check if it exists add bew kay value to the data, and if not add the key value pair to an index
- Find() take the key and goes to the specific location; goes through bucket to see if it can be found
- Contain () takes a key returns a boolean if it can find the key in the has table
- GetHash() conducts the has and returns the index of the array of where the key value will be

## What is a HashTable Data Structure

- Chaining a way to take care of collisions in a hash table
- If there is a collision  you can chain within the index a linked list
- This will allow you to keep the key value pairs that are related in the index

## Basics of Hash Tables

- THe main purpose of a Hash table is to distribute entries uniformly across an array
- Two main steps. An element needs to be converted into a integer using the hash function
- The element is stored that way it can be retrieved

#### Separate Chaining

- Separate Chaining or open hashing is a technique to deal with collisions
- It chains a linked to list when a multiple key value pairs need to be added to the bucket

#### Linear Probing

- Linear probing open addressing or closed hashing is another technique to deal with collisoins
- Instead of using a linked list like in Separate  chaining it uses arrays

#### Quadratic Probing

- similar to linear probing it has different intervals between entry slots

#### Double Hashing

- similar to linear probing but is has a different interval between probes

> ## Reference and Citation

> Joshua McCluskey
