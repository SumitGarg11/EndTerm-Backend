The stream module in Node.js provides a way of handling streaming data.
Streams are objects that let you read data from a source or write data to a destination in a continuous fashion.
There are four types of streams in Node.js: Readable, Writable, Duplex, and Transform.

Here's a basic example of how you can use the stream module to create a Readable stream to read data from 
a file and a Writable stream to write data to another file:

const fs = require('fs');
const stream = require('stream');

// Create a Readable stream to read data from a file
const readableStream = fs.createReadStream('input.txt', 'utf8');

// Create a Writable stream to write data to another file
const writableStream = fs.createWriteStream('output.txt', 'utf8');

// Pipe the data from the Readable stream to the Writable stream
readableStream.pipe(writableStream);

// Handle events on the streams
readableStream.on('data', (chunk) => {
  console.log(`Received ${chunk.length} bytes of data.`);
});

writableStream.on('finish', () => {
  console.log('Data has been written to the file.');
});


// only write 

const fs = require('fs');

// Create a Writable stream to write data to a file
const writableStream = fs.createWriteStream('output.txt', 'utf8');

// Write data to the stream
writableStream.write('Hello, world!\n');
writableStream.write('This is a test.\n');
writableStream.write('Goodbye!\n');

// Close the stream
writableStream.end();

// Handle the 'finish' event
writableStream.on('finish', () => {
  console.log('Data has been written to the file.');
});
