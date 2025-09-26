# hanifnaoh.com

[![GitHub Pages](https://github.com/HanifNaOH/hanifnaoh.github.io/actions/workflows/gh-pages.yml/badge.svg)](https://github.com/HanifNaOH/hanifnaoh.github.io/actions/workflows/gh-pages.yml)

my personal website

## How to create a new post

```bash
hugo new posts/name-of-my-post/index.md
```

## Host Image

([imgchest.com](https://imgchest.com))

## Using CDN for Featured Images & Large Files

### Why Use External CDN for Images?

- ✅ **Repository Size**: Keeps your main repository lightweight (avoid GitHub's 100MB file limit)
- ✅ **Build Performance**: No local image processing delays during Hugo builds
- ✅ **Global Delivery**: Fast loading through CDN networks worldwide
- ✅ **Large File Support**: Host GIFs, videos, and high-resolution images without constraints
- ✅ **Easy Management**: Update images without rebuilding the entire site

### Featured Images (featureimage)

Add external images as featured images in your article frontmatter:

```yaml
---
title: "My Article Title"
date: 2025-09-26T10:00:00+07:00
draft: false
featureimage: "https://your-cdn.com/path/to/image.gif"
featureimagecaption: "Optional caption for your featured image"
---
```

### Background Images (featureimage for backgrounds)

The same `featureimage` parameter also works for background hero images:

```yaml
---
title: "Article with Background"
featureimage: "https://your-cdn.com/background.jpg"
---
```

### Default Images Configuration

Set default external images in `config/_default/params.toml`:

```toml
# Default images (can be external URLs)
defaultBackgroundImage = "https://your-cdn.com/default-bg.jpg"
defaultFeaturedImage = "https://your-cdn.com/default-featured.jpg" 
defaultSocialImage = "https://your-cdn.com/social-share.png"
```

### Recommended CDN Services

#### Free Options:
1. **[ImgChest.com](https://imgchest.com)** - Current recommendation
2. **[Lorem Picsum](https://picsum.photos/)** - Random placeholder images
   ```
   https://picsum.photos/800/600?random=1
   ```
3. **[Giphy](https://giphy.com)** - Perfect for animated GIFs
   ```
   https://media.giphy.com/media/[ID]/giphy.gif
   ```
4. **[Imgur](https://imgur.com)** - Popular image hosting (up to 200MB)
   ```
   https://i.imgur.com/[ID].gif
   ```
5. **[GitHub Raw URLs](https://github.com)** - Use separate repository for media
   ```
   https://raw.githubusercontent.com/username/media-repo/main/image.gif
   ```

#### Professional Options:
1. **[Cloudinary](https://cloudinary.com)** - Advanced image optimization
2. **[ImageKit](https://imagekit.io)** - Real-time image transformations
3. **[AWS S3 + CloudFront](https://aws.amazon.com)** - Enterprise solution

### Content Images (inside articles)

For images within article content, use Hugo's figure shortcode with external URLs:

```markdown
{{< figure 
    src="https://your-cdn.com/content-image.jpg" 
    alt="Image description" 
    caption="Image caption" 
>}}
```

Or standard markdown syntax:
```markdown
![Alt text](https://your-cdn.com/image.jpg "Image caption")
```

### Image Size Recommendations

- **Featured Images**: 800x600 to 1200x800 pixels
- **Background Images**: 1920x1080 or larger for full coverage
- **Content Images**: 600-1000px width for optimal loading
- **Social Sharing**: 1200x630 pixels (Facebook/Twitter optimal)

### Performance Tips

1. **Use WebP format** when possible for smaller file sizes
2. **Optimize GIFs** - compress before uploading to CDN
3. **Use appropriate dimensions** - don't serve 4K images for thumbnails
4. **Test loading speed** on different devices and connections
5. **Consider lazy loading** for content images (theme handles this automatically)

### Example Implementation

Check out these test articles demonstrating external image usage:
- [External Image Test](/posts/external-image-test-2/)
- [Large GIF Test](/posts/large-gif-external-test/)

### Troubleshooting

**Images not loading?**
- Verify the URL is publicly accessible
- Check for HTTPS (mixed content issues)
- Ensure the CDN allows hotlinking
- Test the direct URL in a browser

**Slow loading?**
- Choose a CDN with good global coverage
- Optimize image file sizes before uploading
- Use appropriate image formats (WebP > JPG > PNG for photos)

## Quick Reference

### Create New Post
```bash
hugo new posts/name-of-my-post/index.md
```

### Add External Featured Image
```yaml
featureimage: "https://your-cdn.com/image.gif"
featureimagecaption: "Image description"
```

### Development Server
```bash
hugo server --buildDrafts
```

### Build for Production
```bash
hugo --minify
```
