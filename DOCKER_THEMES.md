# Docker Theme Configuration Guide

## Where to Place Themes in Docker YAML File

This guide explains where to place theme configurations in your `docker-compose.yml` file.

## Theme Placement Location

Themes are configured in the **`environment`** section of your service definition in the `docker-compose.yml` file.

### Example Structure:

```yaml
version: '3.8'

services:
  your-service-name:
    image: your-image
    environment:
      # ← THEMES GO HERE in the environment section
      THEME_NAME: theme-value
      COLOR_SCHEME: color-value
```

## Complete Example

Here's a complete example for GitHub profile badges:

```yaml
version: '3.8'

services:
  github-profile:
    image: nginx:alpine
    environment:
      # LeetCode Stats Theme Configuration
      LEETCODE_THEME: unicorn        # Available: light, dark, wtf, forest, unicorn, nord
      LEETCODE_FONT: "Zen Antique Soft"
      
      # GeeksforGeeks Stats Theme Configuration  
      GFG_THEME: light               # Available: light, dark
      
      # Header Theme Configuration
      HEADER_COLOR_LIST: "6,11,20"
      HEADER_TYPE: waving
```

## Theme Configuration Options

### LeetCode Stats Themes
- `light` - Light theme
- `dark` - Dark theme
- `wtf` - Colorful theme
- `forest` - Forest green theme
- `unicorn` - Rainbow theme
- `nord` - Nord theme
- And many more...

### GeeksforGeeks Stats Themes
- `light` - Light theme
- `dark` - Dark theme

## How to Use Themes

1. **In docker-compose.yml**: Define theme environment variables in the `environment:` section
2. **In your application**: Reference these environment variables to apply themes
3. **Direct URL usage**: Or use the theme parameter directly in image URLs:
   - `https://leetcard.jacoblin.cool/username?theme=unicorn`
   - `https://gfgstatscard.vercel.app/username?theme=light`

## Key Points

✅ **DO**: Place themes in the `environment` section  
✅ **DO**: Use consistent naming for theme variables  
❌ **DON'T**: Place themes in the `ports` or `volumes` sections  
❌ **DON'T**: Place themes at the root level of the YAML file  

## Questions?

If you need to customize themes:
1. Edit the values in the `environment` section
2. Save the `docker-compose.yml` file
3. Restart your containers: `docker-compose down && docker-compose up -d`
