---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
# To see the site locally:
# Run
# To view changes run: bundle exec jekyll serve
#layout: home
---

An attempt will be made to keep this feed up to date.

<div class="news-container" style="border: 2px solid #ddd; border-radius: 8px; padding: 20px; margin: 20px 0; box-shadow: 0 2px 4px rgba(0,0,0,0.1);">
  <h2 style="text-align: center; margin-bottom: 20px;">News feed</h2>
  <div style="display: grid; grid-template-columns: 1fr 3fr; gap: 15px;">
    <div style="font-weight: bold; padding: 8px; background-color: #f5f5f5; border-bottom: 1px solid #ddd;">Date</div>
    <div style="font-weight: bold; padding: 8px; background-color: #f5f5f5; border-bottom: 1px solid #ddd;">Content</div>
    {% for item in site.data.News %}
      <div style="padding: 8px; border-bottom: 1px solid #eee;">{{ item.date }}</div>
      <div style="padding: 8px; border-bottom: 1px solid #eee;">{{ item.content | markdownify }}</div>
    {% endfor %}
  </div>
</div>
