A [Recline][] backend for CouchDB following the [Recline Backend specification][backend].

Part of the [Recline][] suite of data libraries.

[backend]: http://okfnlabs.org/recline/docs/backends.html
[Recline]: http://okfnlabs.org/recline/

## Usage

Get data from the API:

    // queryObj follow Recline query spec
    // http://okfnlabs.org/recline/docs/models.html#query-structure
    var queryObj = {q: 'abc', size: 20, from: 0};
    // 
    var config = {
      db_url: 'url-of-couchdb-instance',
      view_url: 'url-of-the-view'
    };
    recline.Backend.CouchDB.query(queryObj, config)
      .done(function(result) {
        // structure of result is below
        console.log(result);
      });

The result of query has the following form:

    result = {
      hits: // array of Objects
      facets: // facets ...
      total: // total number of results
    }

You can see a more detailed example in examples/multiview/.

## Dependencies

* underscore
* jQuery

## Copyright and License

Copyright 2012 Open Knowledge Foundation and Contributors.

Licensed under the MIT license:

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

