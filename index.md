---
title: Image Communication on Short Waves
author: Martin Bruchanov OK2MNM
---

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>{{ page.title }}</title>
<style>
  :root {
    --max-width: 700px;
    --link-color: #0366d6;
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    line-height: 1.6;
    color: #333;
    background: #fff;
  }
  .home-wrapper {
    max-width: var(--max-width);
    margin: 0 auto;
    padding: 2rem 1rem;
  }
  /* ── Cover ── */
  .cover {
    text-align: center;
    padding: 3rem 0 2rem;
    border-bottom: 3px double #ccc;
    margin-bottom: 2rem;
  }
  .cover h1 {
    font-size: 2.4rem;
    margin-bottom: 0.5rem;
    line-height: 1.3;
  }
  .cover .subtitle {
    font-size: 1.2rem;
    color: #666;
    margin-bottom: 0.3rem;
  }
  .cover .author {
    font-size: 1.1rem;
    color: #444;
    margin-top: 2rem;
  }
  /* ── Actions ── */
  .actions {
    display: flex;
    justify-content: center;
    gap: 1.5rem;
    margin: 2rem 0;
    flex-wrap: wrap;
  }
  .actions a {
    display: inline-block;
    padding: 0.7rem 1.5rem;
    background: #0366d6;
    color: #fff;
    text-decoration: none;
    border-radius: 6px;
    font-weight: 500;
    font-size: 1.05rem;
    transition: background 0.2s;
  }
  .actions a:hover { background: #0250a3; }
  /* ── TOC ── */
  h2 {
    font-size: 1.5rem;
    margin: 1.5rem 0 1rem;
    border-bottom: 1px solid #eee;
    padding-bottom: 0.3rem;
  }
  .toc-list {
    list-style: none;
    counter-reset: chapter;
  }
  .toc-list li {
    counter-increment: chapter;
    border-bottom: 1px solid #f0f0f0;
    padding: 0.5rem 0;
  }
  .toc-list li a {
    color: var(--link-color);
    text-decoration: none;
    font-size: 1.05rem;
  }
  .toc-list li a:hover { text-decoration: underline; }
  .chapter-num {
    color: #999;
    font-size: 0.85rem;
    margin-right: 0.5rem;
  }
  .chapter-num::before {
    content: "Ch." counter(chapter) " ";
  }
</style>
</head>
<body>
<div class="home-wrapper">

  <div class="cover">
    <h1>Image Communication<br>on Short Waves</h1>
    <p class="subtitle">SSTV Handbook</p>
    <p class="author"><strong>Author:</strong> Martin Bruchanov OK2MNM</p>
  </div>

  <div class="actions">
    <a href="{{ site.baseurl }}/fullbook.html">📖 Read Full Book</a>
    <a href="{{ site.baseurl }}/chapters/preface/">▶ Start Reading</a>
  </div>

  <h2 id="toc">Table of Contents</h2>

  <ol class="toc-list">
{% for ch in site.data.chapters %}
    <li><a href="{{ site.baseurl }}/chapters/{{ ch.slug }}/"><span class="chapter-num"></span>{{ ch.title }}</a></li>
{% endfor %}
  </ol>

</div>
</body>
</html>


