# LibCompressVanilla

This is a backported version of the TBC LibCompress. 

I added a few methods:
- LibCompress:TableToString(t)
- LibCompress:StringToTable(t)
- LibCompress:StringSplit(del, table) -- Will return a table

The LZW compression is not working, and I can't figure really out why.
The Huffman compression is working fine.

Usage:
local libc = LibStub:GetLibrary("LibCompress")

local uncompressed = "Hey! I'd like to be compressed"
local compressed = libc:CompressHuffman(uncompressed)
uncompressed = libc:DecompressHuffman(compressed)

local table = {
  [1] => {
    ["test"] => 123
  },
  [2] => 3
}

local uncompressed = libc:TableToString(table)

Returns "1>{,test>123,},2>3,"

I AM NOT THE AUTHOR OF THIS ADDON!
