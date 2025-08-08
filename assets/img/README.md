# Image Assets

This directory contains images used throughout the blog:

- `/posts/` - Images for blog posts
- `/favicons/` - Favicon files for the site
- `avatar.jpg` - Your profile picture for the sidebar

## Image Guidelines

- Use descriptive filenames
- Optimize images for web (compress them)
- Include alt text for accessibility
- Recommended sizes:
  - Avatar: 200x200px
  - Post images: Max width 800px
  - Screenshots: Keep original size but compress

## Adding Images to Posts

Reference images in posts using:

```markdown
![Alt text](/assets/img/posts/image-name.jpg)
_Caption text_
```

For images with specific styling:

```markdown
{% include image.html src="/assets/img/posts/image-name.jpg" alt="Alt text" caption="Caption text" %}
```
