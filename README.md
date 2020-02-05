<h1 align="center">
  <br>
  <a href="https://raw.githubusercontent.com/wajeehanwar/Huffman-Encoding-Text-Compressor"><img src="https://raw.githubusercontent.com/wajeehanwar/Huffman-Encoding-Compressor/master/images/icon.jpeg" alt="Compress Icon" width="150"></a>
  <br>
  Huffman Encoding Compressor
  <br>
</h1>

<h4 align="center">A text file compressor based on the histogramic Huffman encoding</h4>

<p align="center">
<a href="#overview">Overview</a> •
<a href="#nuances">Nuances</a> •
  <a href="#how-to-use">How To Use</a> •
  <a href="#download">Download</a> •
  <a href="#credits">Credits</a> •
  <a href="#license">License</a>
</p>

## Overview

The purpose of this program is to reduce the space required to store/transfer a text file without any loss of data.

The strategy is to reduce the typical space required for each character of the text (8 bits/character). This is done by calculating the frequencies of each character, then creating a Huffman Binary Tree, allowing us to allocate each character with a unique prefix code, with more frequent characters using the least bits.

We are able to store more frequent characters using significantly less than the typical 8 bits by storing the character as the unique prefix code. Thus the compressed file is saved as an encoding table (original file characteristics including the frequency of each character) and a stream of prefix codes corresponding to the original order of characters.

For uncompressing the file, the Huffman Binary Tree is recreated from the character frequencies and the process is reversed to give us the original document.

## Nuances

Customized:

- Command line arguments.
- Uncompressed filename.
- Encoding table write/read:
  - The first four bytes are the length of the input file
  - The next byte is the number of different characters in the file, which is 76 for Hamlet.txt
  - The next 380 bytes are the frequency table, where each of the 76 characters uses five bytes

## Sample

The file used to test the program is Hamlet.txt, which can be found in the test folder of the repository.

> The original file is 196848 bytes.
>
> The compressed file, Hamlet.txt.huf, was 111024 bytes.
>
> The uncompressed file, Hamlet2.txt, was 196848 bytes. This is the same
> as the original file.

This is a **46.3%** reduction in filesize.

## How To Use

Requires installation of [Java](https://java.com/en/download/help/download_options.xml). To compile and run this application from your command line:

```bash
# To compile program.
$ javac HCompressor.java
```

```bash
# To compress text file to filename.txt.huf
$ java HCompressor -h filename.txt
```

```bash
# To uncompress the filename.txt.huf file to filename2.txt
$ java HCompressor -i filename.txt.huf
```

## Download

You can [download](https://github.com//wajeehanwar/Huffman-Encoding-Text-Compressor) here.

## Credits

This software was developed using the following:

- Java

## License

MIT

---

> GitHub [@wajeehanwar](https://github.com/wajeehanwar)
