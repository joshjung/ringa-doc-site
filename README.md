# ringa-doc-site

This project will be a Ringa-based ES6 SPA template that has two commands:

# Generate Site Index

    npm run doc:generate site.json
    
This reads in a `site.json` file that *might* look something like this:

    {
      "application": {
        "title": "RingaJS Documentation",
        "subTitle": "Your happy friend for enterprise state and asynchronous management."
        ...
      },
      "site": {
        "home": {
          "title": "Home",
          "subTitle": "The home page",
          "subNav": {
            "heading": {
              "file": "src/home/Heading.md"
            },
            "content": {
              "file": "src/home/Content.md"
            }
          }
        },
        "gettingStarted": {
          "title": "RingaJS Getting Started",
          "subTitle": "The Hello World of RingaJS",
          "subNav": {
            "heading": {
              "file": "src/gettingStarted/Heading.md"
            },
            "content": {
              "file": "src/gettingStarted/Content.md"
            },
            "demo": {
              "file": "src/gettingStarted/Demo.md"
            }
          }
        }
        ...
      }
    }

When the file is read, three things are done:

1. JSON file is checked for integrity
2. Every `.md` file is read in and indexed using a Trie that is output to a `site-index.json` file.
3. Any custom processing of Markdown is done.

# Run Site

    npm run doc:serve
    
Starts up a server on port `:4000` that runs a Ringa-based SPA that reads in the `site.json` and the `site-index.json`
and uses this to build out React components that work seamlessly together to create a site that is completely
searchable in the browser.

