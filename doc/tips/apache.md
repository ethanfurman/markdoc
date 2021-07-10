# Serving Markdoc Builds With Apache

By default, you should just serve your HTML root out of Apache; that will work very simply. You will need a few options to your `.htaccess` file get the same semantics as the built-in web server (the one which runs when you do `markdoc serve`):

    #!text
    Options +MultiViews
    
    <FilesMatch "\.html$">
      ForceType 'charset=UTF-8'
    </FilesMatch>

The first directive will cause requests for `/directory/filename` to look for `directory/filename.html` in your HTML root, allowing for more natural references between pages in your wiki.
