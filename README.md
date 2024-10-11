# FILZIP

## Overview

This project implements Huffman coding, a widely used algorithm for lossless data compression. The algorithm is based on the frequency of occurrence of characters in a text file, enabling more frequent characters to be represented with shorter codes, resulting in overall compression.

## How Huffman Coding Works

1. **Frequency Analysis**: 
   - The first step in Huffman coding is to analyze the input text to determine the frequency of each character. This frequency will dictate the length of the codes assigned to each character.

2. **Building the Huffman Tree**:
   - Each unique character is represented as a leaf node in a binary tree, with the frequency as its weight.
   - The tree is built using a priority queue (or min-heap) where nodes with the lowest frequencies are combined to form a new internal node. This process is repeated until there is only one node left, which becomes the root of the tree.

3. **Assigning Codes**:
   - Once the tree is built, each character is assigned a binary code based on its position in the tree. Moving left corresponds to adding a "0" to the code, and moving right adds a "1". 
   - Characters that are more frequent are closer to the root and thus have shorter codes.

4. **Encoding**:
   - The original text is then encoded by replacing each character with its corresponding Huffman code. The result is a compressed binary representation of the text.

5. **Decoding**:
   - To decode the binary data, the Huffman tree is used again. The process involves traversing the tree based on the bits until reaching a leaf node, which corresponds to the original character.


### Huffman tree for the text "ABCADDAD," 
        [7]
       /   \
     [3]   [4]
     [A]  /   \
         [2]  [2]
        / \   / \
      [B][C][D][ ]
