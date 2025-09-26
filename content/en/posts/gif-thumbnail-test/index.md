---
title: "Heavy GIF Thumbnail Test"
date: 2025-09-26T10:00:00Z
draft: false
description: "Testing heavy GIF thumbnail functionality in Blowfish theme"
tags: ["test", "gif", "thumbnail", "heavy", "performance"]
categories: ["testing"]
---

# Heavy GIF Thumbnail Test Post

This is a test post to verify that **heavy GIF thumbnails** (7.6MB+) work correctly in the Blowfish theme and how Hugo processes large image files.

The post should display a large animated GIF as its thumbnail in:

- Homepage article cards
- Post listing pages  
- Social media sharing (Open Graph)

## Test Details

- **Theme**: Blowfish
- **Image Processing**: Currently set to `disableImageOptimization = false`
- **GIF File Size**: ~7.6 MB (large test file)
- **Expected Behavior**: Hugo should process and optimize the large GIF for web usage
- **File Name**: `featured.gif` (following Blowfish naming convention)

## Performance Test

This test will help determine:

1. How Hugo handles large GIF files during build process
2. Whether image optimization significantly reduces file size
3. If thumbnails load efficiently despite large source file
4. Processing time impact during site generation

## Content

This is test content for the heavy GIF thumbnail test. The important aspect is analyzing how the large source GIF affects:

- Build performance
- Thumbnail generation
- Page load times
- User experience

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.