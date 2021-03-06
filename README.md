tarball-extract-improve
===============
> This is a forked project from [tarball-extract](https://github.com/matsieftw/tarball-extract), changing the outdated `wget` package to `node-wget-promise`.

A simple tarball download and extraction lib for node.

## Install

    npm install tarball-extract-improve

## method: extractTarball(sourceFile, destination, callback)
Extracts a tar file using **node-tar**. If the file ends in a **.tgz** or a **tar.gz** gzip will be used to deflate it before passing the stream to tar.

    var tarball = require('tarball-extract-improve')
    tarball.extractTarball('/tmp/test.tar', '/tmp/test', function(err){
      if(err) console.log(err)
    })

## method: extractTarballDownload(url, downloadFile, destination, options, callback)
Download a tarball from a **url** and automatically extract it. 

    var tarball = require('tarball-extract-improve')
    url = 'http://example.com/testfile.tar.gz'
    tarball.extractTarballDownload(url , '/tmp/testfile.tar.gz', '/tmp/testfile', {}, function(err, result) {
      console.log(err, result)
    })

When the download is complete the callback is passed (err, info).

    { url: 'http://example.com/testfile.tar.gz',
      downloadFile: '/tmp/testfile.tar.gz',
      destination: '/tmp/testfile' }

