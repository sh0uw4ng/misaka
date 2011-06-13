Pantyshot
=========

A Python binding for [Upskirt][1].

 [1]: https://github.com/tanoku/upskirt


Documentation can be found at: http://pantyshot.61924.nl/


Installation
------------

    python setup.py install


Usage
-----

    import pantyshot

    pantyshot.html('Hello, world!')

With extensions and render flags.

    import pantyshot as p

    p.html(
        'Hello, world!',
        p.EXT_AUTOLINK | p.EXT_TABLES,
        p.HTML_EXPAND_TABS
    )

In combination with `functools.partial`.

    import functools
    import pantyshot as p

    markdown = functools.partial(
        p.html,
        extensions=p.EXT_AUTOLINK | p.EXT_TABLES,
        render_flags=p.HTML_EXPAND_TABS
    )
    markdown('Awesome!')

Or generate a table of contents.

    pantyshot.toc('''
    # Header one

    Some text here.

    ## Header two

    Some more text
    ''')


Extensions & render flags
-------------------------

Extensions:

    EXT_AUTOLINK
    EXT_LAX_HTML_BLOCKS
    EXT_TABLES
    EXT_NO_INTRA_EMPHASIS
    EXT_STRIKETHROUGH
    EXT_FENCED_CODE
    EXT_SPACE_HEADERS

Render flags:

    HTML_GITHUB_BLOCKCODE
    HTML_SKIP_HTML
    HTML_SKIP_STYLE
    HTML_HARD_WRAP
    HTML_TOC
    HTML_SKIP_LINKS
    HTML_SAFELINK
    HTML_SKIP_IMAGES
    HTML_EXPAND_TABS
    HTML_USE_XHTML
    HTML_SMARTYPANTS
