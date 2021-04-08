# 1. Performance

## 1.1. Improve client side performance

### 1.1.1. Critical render path

:::important **Website load lifecycle - Aka. Critical render path**

1. **Client**: `GET website_url`
2. **Server**: Processes the request and returns the result as `HTML` via HTTP
3. **Client**: Reads the response and browser create the `DOM structure.`
4. **Client**: It encounters `stylesheets tag` and loads the `CSS styles`
5. **Client**: Encounters `javascript tag` and loads the `JS script`
6. **Client**: Executes the script
7. **Client**: `Render three` is created which `combines the HTML, CSS and JS` and constructs `the layout`
8. **Client**: Browser based on layout `displayes/paints the website`

:::

Guidelines:

- Send `CSS` asap
- Scripts block page rendering (bottom of the html | exception being Google Analytics)
- CSS is render-blocking (blocking the render three) To fix:
  - Only load whatever is needed.
    - Using the `internal` or `inline` styles for specific non reusable cases to get performance.
  - Above the fold loading `lazy loading css`

**Example:**

```js
const stylesheets = (src) => {
    // stylesheets is a custom function to add link tag to head
}

window.onload(stylesheets('src'))
```

- Media attributes
- Less specificity (reduce the style specificity calculation)
- `JS` is the most critical part, due to its abillity to effect DOM and CSS.
  - JS is `parser blocking`. It stops the parsing process when executing and/or loading.
  - `<script>` -> parse blocker
  - `<script async>` -> loads script async then only blocks parsing when loading. `Used for Tracking and Google Analytics scripts`. For core functionalities.
  - `<script defer>` -> wait until everything is parsed then execute.Good for scripts that would effect the critical render path. For all non essential JS functionalities.
  - [Script Tag - async & defer](https://stackoverflow.com/questions/10808109/script-tag-async-defer)

- [prefetching](https://css-tricks.com/prefetching-preloading-prebrowsing/)

### 1.1.2. Optimized code

### 1.1.3. PWA

## 1.2. Improve transfer path (Network performance)

For every website you need to send a `request` to get the website content.

`HTTP/3`: [HTTP/3](https://blog.cloudflare.com/http3-the-past-present-and-future/)

### 1.2.1. Minimize files

How to reduce **the size of the files**?

- **Minimize text**
  - JS, CSS, HTML
  - You do that with different minifiers
  - `UglifyJS` for JS
  - Part of the build process (`Webpack`)
- **Minimize images**
  - Most common way to slow down a website.
  - Image file formats
    - `JPG` -> Complex images, with loads of colors, no transparency
    - `PNG` -> Reduce the color count, smaller than JPG, good for logos
    - `GIF` -> Reducing the color count to 255, alows transparency, animations
    - `SVG` -> Customisable, simplistic with few colors, icons|logos|illustrations
  - Image compression
    - `PNG -> TinyPNG` [TinyPNG](https://tinypng.com/)
    - `JPG -> JPEG-optimizer` [JPEG-optimizer](http://www.jpeg-optimizer.com/)
    - Drop the JPEG image quality 30-60%
  - Set Image size based on size it will be displayed (NextJS build-in Image)
  - Display different sized images for different backgrounds with `Media queries`.
  
```css
/* *.css */

@media screen and (max-width: 768px) {
    background: url('small_image.jpg')
    /* .... Small image for phones */
}
@media screen and (min-width: 768px) {
    background: url('large_image.jpg')
    /* .... Large image for bigger devices */
}

```

- Use CDNs like `imigx` [imigix](https://www.imgix.com/)
- Remove Image `metadata` [exif](http://www.viewexifdata.com/)
  
### 1.2.2. Minimize delivery

Reduce the **travelling frequency** (Reduce the number of HTTP requests).

Use lightweight libraries. Be vary of 'what/size of' libraries you import.

Number of files browser can gather varies from browser to browser. [Max parallel http connections in a browser?](https://stackoverflow.com/questions/985431/max-parallel-http-connections-in-a-browser)

Network tab have features to tune you connection speed (slow 3G, 4G,...).

`Bundle` -> combining files into one (ex `Webpack`)

## 1.3. Improve server side performance (Backend processing)

### 1.3.1. CDNs

### 1.3.2. Caching

### 1.3.3. Load Balancing

### 1.3.4. DB Scaling

### 1.3.5. GZIP

## Extras

`PageSpeed Insights` [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/)

`WebPageTest` [WebPageTest](https://www.webpagetest.org/)
