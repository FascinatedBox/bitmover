Bitmover
========

A toy cipher program.

Usage: `lily bitmover.lily <key> <value>`

This program contains a handful of simple ciphering mechanisms. `key` is a
comma-separated list of names specifying what ciphers to be used. Cipher names
are case sensitive. Invalid cipher names are silently ignored.

Available ciphers are as follows:

### DecreaseEach

Subtract 1 from every byte. If the byte is 0, it is set to 0xff.

### IncreaseEach

Add 1 to every byte. If the byte is 0xff, it is set to 0.

### PairSwap

This walks through the input from left to right in pairs. Every pair of bytes is
swapped. If there are an odd number of bytes, the last byte is left alone.

### PairXor

This walks the input from left to right in pairs. With `left` as the first byte
in the pair and `right` as the second, this sets `right` to `left ^ right`.

### LeftShiftTotal

This simulates a left shift over the whole of `input`. Upper bits from
right-ward bytes become low bits of left-ward bytes. The first bit of the first
value is sent to the last byte as the last value.

### RightShiftTotal

This simulates a right shift over the whole of `input`. This does the reverse of
the above, moving low bits from left-ward bytes into high bits of right-ward
bytes. The last bit of the last byte carries over to be the high bit of the
first byte.
