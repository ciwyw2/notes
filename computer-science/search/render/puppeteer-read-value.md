# Puppeteer 读取元素的值


wp_id: 78
Status: publish
Date: 2019-06-15 15:06:22
Modified: 2020-05-16 10:59:06


<!-- wp:paragraph -->
<p>
如果是 input 元素的话，需要读取 value 值。
</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">const element = await page.$(".panel #video0");
const sourceURL = await page.evaluate(element => element.value, element);
</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>
如果是其他元素的话，需要读取 textContent 值。
</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>
参考这里：
</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><li> <a href="https://github.com/GoogleChrome/puppeteer/issues/3051" target="_blank" rel="noreferrer noopener">https://github.com/GoogleChrome/puppeteer/issues/3051</a>
</li></ol>
<!-- /wp:list -->