<h1>Lab Report 5:</h1>
<h3><i>Based on Lab Report 3</i></h3>

We didn't cover <code>locate</code> in class, so I figured it could be an interesting command to explore. 

<h2>Default usage:</h2>

```console
zachl@Zachs-MacBook-Air cse12-wi23-pa8-BinarySearchTree-Sorting-starter-main % locate page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/advanced-custom-fields/includes/locations/class-acf-location-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/blog-designer-pack/includes/admin/all-shortcode-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/brute-force-login-protection/includes/settings-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/jetpack/_inc/lib/admin-pages/class-jetpack-about-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/jetpack/_inc/lib/admin-pages/class.jetpack-admin-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/jetpack/_inc/lib/admin-pages/class.jetpack-landing-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/jetpack/_inc/lib/admin-pages/class.jetpack-react-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/jetpack/_inc/lib/admin-pages/class.jetpack-settings-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/jetpack/modules/protect/blocked-login-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/jetpack/modules/sitemaps/sitemap-buffer-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/themes/ksdt_wi23/page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/themes/ksdt_wi23/template-parts/content-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/themes/winter18designs-branch/theme/page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/themes/winter18designs-branch/theme/template-parts/content-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-includes/class-walker-page.php
/Applications/XAMPP/xamppfiles/lib/php/doc/HTML_Progress/examples/generator/htmlpage.php
/Applications/XAMPP/xamppfiles/lib/php/doc/HTML_Progress/examples/monitor/htmlpage.php
/Users/zachl/theme/page.php
/Users/zachl/theme/template-parts/content-page.php
```
The <code>locate</code> command uses a compressed database file containing file paths in order to return every file that matches parts of the specified pattern (that the user has read access to). It should be noted that when first executing <code>locate></code>, a prompt will be given to generate the compressed database file. The database is updated based on a cron job that, by default, runs every 24 hours. A cron job is a scheduled sort of command, in this case specific to macOS.

<h2>Options:</h2>

<h3><code>-l</code></h3>

```console
zachl@Zachs-MacBook-Air cse12-wi23-pa8-BinarySearchTree-Sorting-starter-main % locate -l 5 page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/advanced-custom-fields/includes/locations/class-acf-location-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/blog-designer-pack/includes/admin/all-shortcode-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/brute-force-login-protection/includes/settings-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/jetpack/_inc/lib/admin-pages/class-jetpack-about-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/jetpack/_inc/lib/admin-pages/class.jetpack-admin-page.php
locate: [show only 5 lines]
```

Limits the number files outputted to the argument given following the -l option. This is useful when parsing for common patterns. Alternatively, the command output could be piped to less as follows:

```console
% locate page.php | less
```

Sources used:
https://linuxize.com/post/locate-command-in-linux/

<h3><code>-i</code></h3>

```console
zachl@Zachs-MacBook-Air cse12-wi23-pa8-BinarySearchTree-Sorting-starter-main % locate -i  page.php 
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/advanced-custom-fields/includes/locations/class-acf-location-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/blog-designer-pack/includes/admin/all-shortcode-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/brute-force-login-protection/includes/settings-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/jetpack/_inc/lib/admin-pages/class-jetpack-about-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/jetpack/_inc/lib/admin-pages/class.jetpack-admin-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/jetpack/_inc/lib/admin-pages/class.jetpack-landing-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/jetpack/_inc/lib/admin-pages/class.jetpack-react-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/jetpack/_inc/lib/admin-pages/class.jetpack-settings-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/jetpack/modules/protect/blocked-login-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/jetpack/modules/sitemaps/sitemap-buffer-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/plugins/wp-optimize/vendor/mrclay/minify/lib/Minify/Controller/Page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/themes/ksdt_wi23/page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/themes/ksdt_wi23/template-parts/content-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/themes/winter18designs-branch/theme/page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-content/themes/winter18designs-branch/theme/template-parts/content-page.php
/Applications/XAMPP/xamppfiles/htdocs/wordpress/wp-includes/class-walker-page.php
/Applications/XAMPP/xamppfiles/lib/php/HTML/Progress/generator/HTMLPage.php
/Applications/XAMPP/xamppfiles/lib/php/HTML/QuickForm2/Controller/Page.php
/Applications/XAMPP/xamppfiles/lib/php/doc/HTML_Progress/examples/generator/htmlpage.php
/Applications/XAMPP/xamppfiles/lib/php/doc/HTML_Progress/examples/monitor/htmlpage.php
/Applications/XAMPP/xamppfiles/lib/php/doc/Net_Curl/examples/fetchPage.php
/Users/zachl/theme/page.php
/Users/zachl/theme/template-parts/content-page.php
```

Ignores the case of the pattern, where any character in the pattern is interpreted as upper <b>and</b> lower case. Notice that files named:
<code>page.php</code> and <code>Page.php</code> are both outputted.

Sources used:
https://linuxize.com/post/locate-command-in-linux/

<h3><code>-c</code></h3>

```console
zachl@Zachs-MacBook-Air cse12-wi23-pa8-BinarySearchTree-Sorting-starter-main % locate -i -c  page.php
23
```
Outputs the number of files found matching the pattern inputted. This is helpful as it removes the need to pipe the output of <code>locate</code> out to <code>wc</code> to count the number of files. This less efficient piping method can be seen below:

```console
zachl@Zachs-MacBook-Air cse12-wi23-pa8-BinarySearchTree-Sorting-starter-main % locate -i page.php | wc -l
23
```

Sources used:
https://linuxize.com/post/locate-command-in-linux/

<h3><code>-S</code></h3>

```console
zachl@Zachs-MacBook-Air cse12-wi23-pa8-BinarySearchTree-Sorting-starter-main % locate -S page.php

Database: /var/db/locate.database
Compression: Front: 10.50%, Bigram: 57.52%, Total: 7.37%
Filenames: 2536314, Characters: 387510871, Database size: 28561323
Bigram characters: 12133234, Integers: 274865, 8-Bit characters: 416
```

Prints statistics and information about the compressed database file containing the file paths that are searched when the <code>locate</code> command is executed. This is especially helpful as it outputs the path of the database file, which can be shared as a representation of every file on a machine in a compressed form, which has practical applications, especially pertaining to virtual machines.

Sources used:
https://linuxize.com/post/locate-command-in-linux/

