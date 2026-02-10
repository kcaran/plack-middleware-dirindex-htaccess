# NAME

Plack::Middleware::DirIndex::Htaccess - Serve default html files for directory URLS. Includes checking of .htaccess file for DirectoryIndex.

# SYNOPSIS

    use Plack::Builder;
    use Plack::App::Directory;

    my $app = Plack::App::Directory->new()->to_app;

    builder {
        enable "DirIndex::Htaccess", root => '.', dir_index => 'index.html';
        $app;
    };

# DESCRIPTION

The Apache web server uses the `DirectoryIndex` directive within
`.htaccess` files to automatically serve a default page
(e.g., `about.html` when a user requests a directory URL like `/about/`).

This Plack middleware provides a lightweight simulation of
Apache's DirectoryIndex functionality for your local Plack environment.
By reading the `DirectoryIndex` from your existing `.htaccess` files,
it ensures that requests to directories resolve to the correct default
file, just as they would on the live server.

If there is no c<DirectoryIndex> directive (or `.htaccess` file), the module will append the value of &lt;dir\_index> (defaults to `index.html`) if the file exists, like Plack::Middleware::DirIndex.

# AUTHOR

Keith Carangelo <kcaran@gmail.com>

# COPYRIGHT & LICENSE

This software is Copyright (c) 2026 by Keith Carangelo.

This is free software, licensed under:

    MIT No Attribution License

MIT No Attribution

Copyright 2026 Keith Carangelo

Permission is hereby granted, free of charge, to any person obtaining a copy of this
software and associated documentation files (the "Software"), to deal in the Software
without restriction, including without limitation the rights to use, copy, modify,
merge, publish, distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED,
INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A
PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
