---
title: Unit Converter 2021 — by 9dogs
permalink: /
---

<style>
/* Simple, modern gallery + responsive layout */
:root { --accent: #2c97ff; }
.hero { text-align:center; padding: 3rem 1rem 2rem; }
.hero h1 { margin: 0 0 .25rem; font-size: 2.2rem; }
.hero p.lead { color:#4a4a4a; font-size:1.1rem; margin:.25rem 0 1rem; }
.cta {
  display:inline-block; padding:.75rem 1.2rem; border-radius:10px;
  background: var(--accent); color:#fff !important; text-decoration:none;
  box-shadow: 0 6px 18px rgba(44,151,255,.35);
}
.meta { margin-top:.75rem; color:#666; font-size:.95rem; }
.grid {
  display:grid; gap:12px; grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
}
.grid img { width:100%; height:auto; border-radius:16px; border:1px solid #e5e5e5; }
.section { margin: 2.5rem 0; }
.kicker { text-transform: uppercase; letter-spacing:.08em; color:#888; font-size:.8rem; margin-bottom:.5rem; }
blockquote { background:#f9fafb; border-left:4px solid var(--accent); padding:.75rem 1rem; }
@media (min-width: 900px) {
  .hero h1 { font-size:2.6rem; }
}
</style>

{% assign app = site.data.app_parsed %}

<div class="hero">
  <h1>{{ app.trackName | default: "Unit Converter 2021" }}</h1>
  <p class="lead">A simple, fast, and clean unit converter built for clarity.</p>
  <a class="cta" href="{{ app.trackViewUrl | default: site.app_store_url }}" rel="noopener" target="_blank">Download on the App Store</a>
  <div class="meta">
    {{ app.formattedPrice | default: "Free" }} · {{ app.primaryGenreName | default: "Utilities" }} · Rating {{ app.averageUserRating | default: 5 | round: 1 }}/5 ({{ app.userRatingCount | default: 0 }})
  </div>
</div>

<div class="section">
  <div class="kicker">Screenshots</div>
  <div class="grid">
    {% for shot in app.screenshotUrls %}
      <a href="{{ shot }}" target="_blank" rel="noopener">
        <img src="{{ shot }}" alt="App screenshot {{ forloop.index }}" loading="lazy" />
      </a>
    {% endfor %}
  </div>
</div>

<div class="section">
  <div class="kicker">Why You’ll Love It</div>
  {% if app.description %}
    <blockquote>{{ app.description | strip_newlines | truncate: 600 }}</blockquote>
  {% else %}
    <blockquote>
      Designed for signal over noise — convert units fast without distractions. Thoughtful UI, clear abbreviations (kg ⇄ lb, cm ⇄ in, °C ⇄ °F), and a smooth experience.
    </blockquote>
  {% endif %}
</div>

<div class="section">
  <div class="kicker">Details</div>
  <ul>
    <li><strong>Version:</strong> {{ app.version | default: "—" }}</li>
    <li><strong>Updated:</strong> {{ app.currentVersionReleaseDate | date: "%b %d, %Y" }}</li>
    <li><strong>Size:</strong> {% if app.fileSizeBytes %}{{ app.fileSizeBytes | plus: 0 | divided_by: 1048576.0 | round: 1 }} MB{% else %}—{% endif %}</li>
    <li><strong>Languages:</strong> {% if app.languageCodesISO2A %}{{ app.languageCodesISO2A | join: ", " }}{% else %}—{% endif %}</li>
    <li><strong>Age Rating:</strong> {{ app.contentAdvisoryRating | default: app.trackContentRating | default: "—" }}</li>
    <li><strong>Compatibility:</strong> iPhone (iOS {{ app.minimumOsVersion | default: "9.0+" }})</li>
  </ul>
</div>

<hr>

<p style="text-align:center; font-size:.95rem; color:#666;">
  Questions? Contact <a href="mailto:{{ site.email }}">{{ site.email }}</a> · © {{ "now" | date: "%Y" }} 9dogs
  {% if app.sellerUrl %} · <a href="{{ app.sellerUrl }}" target="_blank" rel="noopener">Support</a>{% endif %}
</p>

