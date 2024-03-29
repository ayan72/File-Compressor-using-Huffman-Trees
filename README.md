# File-Compressor-using-Huffman-Trees

Notes and Assumptions:
* The python program util.py has functions that compresses and decompresses 
 files using Huffman coding. The compressor is a command-line program that 
 compresses (encodes) any file with .huf extension. The decompressor is a web
 server that decodes the compressed files and sends it to the browser.

* There are five functions in util.py:
1. read_tree(tree_stream):
  It reads a description of a Huffman tree from the tree stream, and uses the 
  pickle module(load) to get the tree object.The parameter tree_stream is the 
  compressed stream for reading the tree and a huffman tree root is returned.

2. decode_byte(tree, bitreader):
   This functiion reads bits and traverses the tree from the root to a leaf.
   Once a leaf is reached, the value of that leaf is returned. The parameter 
   bitreader is an instance of bitio.BitReader and tree is a huffman tree. The
   function will return next byte of the compressed bit stream.

3. write_tree(tree, tree_stream):
   write_tree writes the Huffman tree to the tree_stream using pickle (dump) 
   module. It has the parameters tree and tree_stream.

4. decompress(compressed, uncompressed):
   It reads a Huffman tree from the compressed stream and then uses the tree to
   decode the stream and write the resulting symbols to our uncompressed stream.
   It has the parameters compressed and uncompressed which are the file streams
   to read and write ,respectively.

5. compress(tree, uncompressed, compressed):
   This function compresses the given file using the Huffman tree. The tree is
   written to the uncompressed stream using write_tree function. Then, the tree 
   is used to encode the file and write it to the compressed stream.
   The parameters of the function are tree, compressed and decompressed.
