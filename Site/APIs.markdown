---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
# To see the site locally:
# Run
# To view changes run: bundle exec jekyll serve
#layout: home
---

# APIs in PhysLean 

The below is a list of APIs in PhysLean. 
One way to help the project is by enhancing and developing these APIs. 
## Status Key

<div style="display: flex; flex-wrap: wrap; gap: 10px; margin-bottom: 20px;">
  <div style="padding: 8px 15px; border-radius: 4px; background-color: #d4edda; display: flex; align-items: center;">
    <span style="font-weight: bold;">Complete</span> - Implemented
  </div>
  <div style="padding: 8px 15px; border-radius: 4px; background-color: #fff3cd; display: flex; align-items: center;">
    <span style="font-weight: bold;">Needs Work</span> - Implemented but requires improvements
  </div>
  <div style="padding: 8px 15px; border-radius: 4px; background-color: #f7e4e5ff; border: 2px dashed #f8d7da; display: flex; align-items: center;">
    <span style="font-weight: bold;">Could be Started</span> - Development could be started
  </div>
  <div style="padding: 8px 15px; border-radius: 4px; background-color: #f8d7da; display: flex; align-items: center;">
    <span style="font-weight: bold;">Not Started</span> - Not started
  </div>
</div>
<div class="news-container" style="border: 2px solid #ddd; border-radius: 8px; padding: 20px; margin: 20px 0; box-shadow: 0 2px 4px rgba(0,0,0,0.1);">
  <h2 style="text-align: center; margin-bottom: 20px;">APIs in PhysLean</h2>
  <div style="display: grid; grid-template-columns: 1fr 3fr; gap: 15px;">
    <div style="font-weight: bold; padding: 8px; background-color: #f5f5f5; border-bottom: 1px solid #ddd;">Title</div>
    <div style="font-weight: bold; padding: 8px; background-color: #f5f5f5; border-bottom: 1px solid #ddd;">Description</div>
    {% for item in site.data.APIs %}
      <div style="padding: 8px; border-bottom: 1px solid #eee; {% if item.status == 'Complete' %}background-color: #d4edda;{% elsif item.status == 'NeedsWork' %}background-color: #fff3cd;{% elsif item.status == 'StartedSoon' %}border: 2px dashed #f8d7da; background-color: #f7e4e5ff; {% elsif item.status == 'NotStarted' %}background-color: #f8d7da;{% endif %}">{% if item.link %}<a href="{{ item.link }}">{{ item.title }}</a>{% else %}{{ item.title }}{% endif %}</div>
        <div style="padding: 8px; border-bottom: 1px solid #eee; {% if item.status == 'Complete' %}background-color: #d4edda;{% elsif item.status == 'NeedsWork' %}background-color: #fff3cd;{% elsif item.status == 'StartedSoon' %}border: 2px dashed #f8d7da; background-color: #f7e4e5ff; {% elsif item.status == 'NotStarted' %}background-color: #f8d7da;{% endif %}">{{ item.content | markdownify }}</div>
    {% endfor %}
  </div>
</div>
