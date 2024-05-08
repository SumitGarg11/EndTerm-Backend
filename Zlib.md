In the context of Node.js and many other programming environments, 
`zlib` is a library that provides support for data compression and decompression using the zlib compression algorithm.
The zlib algorithm is a widely used compression algorithm that provides a good balance between compression ratio and speed.

`deflate` and `inflate` are functions provided by the zlib library for compressing and decompressing data, respectively. 
Here's a brief overview of each:

- `deflate`: This function takes input data and compresses it using the zlib compression algorithm.
-  It produces a compressed output that is typically smaller in size than the original input.
-   The `deflate` function has various options for configuring the compression level and other parameters
-    to trade off between compression ratio and speed.

- `inflate`: This function takes compressed data and decompresses it back to its original form.
-  It reverses the compression process performed by the `deflate` function, reconstructing the original input data.

These functions are commonly used in scenarios where data needs to be transmitted or stored efficiently,
as compression can reduce the amount of data that needs to be transferred or stored.


const zlib = require('zlib');
const data  = "Bhoom bhoom chal chal ja ja rhe";
// compresed data 
zlib.gzip(data,(err,compressedData)=>{
    if(err){
        console.log("Error compressing data : ",err);
        return;
    }
    console.log(compressedData.toString());
    // decompressed the data 
    zlib.gunzip(compressedData,(err,decompressedData)=>{
        if(err){
            console.log('Error decompressing data ',err);
            return;
        }
        console.log('Decompressed data: ',decompressedData.toString());
    })

})




