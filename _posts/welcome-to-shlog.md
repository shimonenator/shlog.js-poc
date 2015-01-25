**Shlog.js** is a proof of concept.

- No server, everything in the browser
- Client-side, JavaScript implemented
- Markdown loving blog.

Let's you host you content on Dropbox, Divshot or any other static host with CORS enabled. We're creating this to dabble with:

- window.fetch
- Promises
- localForage & IndexedDB
- History API
- AppCache
- Marked (Markdown client-side parsing)

posts.json file holds the posts metadata, you can put an absolute link in the content field if you're hosting on Dropbox or another cloud (CORS required).

config.json holds the config data for the blog.

*I'm aware that this code is hacky, no abstractions nor patterns were used, but as I said, this is just a proof that we can have a blog completely on the client side with Dropbox or cloud service as a storage, and business logic on the client-side. Much better than Jekyll, no building and other stuff.*