LA BIBLIOTECA — split for fast loading
======================================
BEFORE: biblioteca.html was 6.9 MB — every visitor downloaded all 26 books
        just to see the library. Slow, especially on mobile.

AFTER:  biblioteca.html is 40 KB. It loads instantly and shows the library
        (covers, titles, blurbs). Each book's text lives in its own file under
        biblioteca-books/ and is fetched ONLY when the reader opens that book.

DEPLOY (keep the structure intact):
  biblioteca.html                  <- the library (was 6.9MB, now 40KB)
  biblioteca-books/<slug>.json     <- 26 book files, loaded on demand
  biblioteca-img/covers/*.jpg      <- cover images (unchanged; keep your existing folder)

All 26 books are preserved — nothing was deleted. Sherlock Holmes and Julio
Verne are full collections (they were never empty).

NOTE: this uses fetch(), so it must be served over http/https (Netlify is fine).
Opening biblioteca.html directly from disk (file://) may block the fetch.
