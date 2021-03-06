---
title: 'LocalFileSystemSync'
notes:
  - 'Out of date; feature discontinued. See http://www.w3.org/TR/file-system-api/.'
readiness: 'Out of Date'
standardization_status: 'W3C Working Draft'
summary: "The LocalFileSystemSync interface of the File System API gives you access to a sandboxed file system. It is intended to be used with WebWorkers. The methods are implemented by worker objects.\n"
tags:
  - API_Objects
  - API
  - FileSystemAPI
uri: apis/filesystem/LocalFileSystemSync

---
## Summary

The LocalFileSystemSync interface of the File System API gives you access to a sandboxed file system. It is intended to be used with WebWorkers. The methods are implemented by worker objects.

**Out of date; feature discontinued. See [http://www.w3.org/TR/file-system-api](http://www.w3.org/TR/file-system-api/).**

## Properties

*No properties.*

## Methods

[requestFileSystemSync](/apis/filesystem/LocalFileSystemSync/requestFileSystemSync)
:   Requests a file system where data should be stored. You access a sandboxed file system by requesting a LocalFileSystemSync object from within a web worker using this global method, window.requestFileSystemSync().

    **Out of date; feature discontinued. See [http://www.w3.org/TR/file-system-api](http://www.w3.org/TR/file-system-api/).**

[resolveLocalFileSystemSyncURL](/apis/filesystem/LocalFileSystemSync/resolveLocalFileSystemSyncURL)
:   Allows the user to look up the Entry for a file or directory referred to by a local URL.

    **Out of date; feature discontinued. See [http://www.w3.org/TR/file-system-api](http://www.w3.org/TR/file-system-api/).**

## Events

*No events.*

## Related specifications

[W3C File API: Directories and System Specification](http://dev.w3.org/2009/dap/file-system/pub/FileSystem/)
:   W3C Working Draft
