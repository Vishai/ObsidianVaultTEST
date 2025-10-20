# Export as HTML Steps

## Overview
Step-by-step guide to export your Obsidian vault as HTML files.

## Using Webpage HTML Export Plugin

### Installation
1. Open Obsidian Settings
2. Navigate to Community Plugins
3. Browse and search for "Webpage HTML Export"
4. Click Install
5. Enable the plugin

### Configuration
1. Open plugin settings
2. Configure export options:
   - Include inline styles
   - Export linked notes
   - Image handling
   - Custom CSS
   - Navigation options

### Export Single Note
1. Open the note you want to export
2. Open command palette (Cmd/Ctrl + P)
3. Type "Export as HTML"
4. Select "Export current file"
5. Choose destination folder

### Export Multiple Notes
1. Open command palette
2. Select "Export vault as HTML"
3. Configure export settings
4. Select output directory
5. Wait for export to complete

### Export with Custom Styling
1. Create custom CSS in assets/css/
2. Reference in plugin settings
3. Export with custom CSS applied

## Post-Export Steps
1. Test HTML files in browser
2. Verify all links work
3. Check image paths
4. Upload to web server

## Hosting Options
- GitHub Pages
- Netlify
- Vercel
- Traditional web hosting

## Automation
Set up automatic exports:
1. Use n8n workflow
2. Schedule regular exports
3. Auto-deploy to hosting

## Tips
- Test locally before deploying
- Use relative paths for portability
- Optimize images for web
- Consider mobile responsiveness

## Related
- [[obsidian_publish_workflow]]
- [[n8n_automation_cheatsheet]]
