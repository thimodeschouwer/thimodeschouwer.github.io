<h2 id="workingpapers" class="section-heading">Working Papers</h2>

<div class="publications">
<ol class="bibliography">

{% for link in site.data.workingpapers.main %}

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr">
    {% if link.image %}
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1">
    {% endif %}
    {% if link.conference_short %}
    <abbr class="badge">{{ link.conference_short }}</abbr>
    {% endif %}
  </div>
  <div class="col-sm-9">
      <div class="title"><a href="{{ link.pdf }}">{{ link.title }}</a></div>
      <div class="author">{{ link.authors }}</div>
      <div class="periodical"><em>{{ link.conference }}</em>
      </div>
      {% if link.notes %}
      <div class="pub-note">{{ link.notes }}{% if link.journal %} at <a href="{{ link.journal_link }}" target="_blank">{{ link.journal }}</a>{% endif %}</div>
      {% endif %}
    <div class="links">
      {% if link.pdf %}
      <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0 btn-paper" role="button" target="_blank" style="font-size:12px;">WP</a>
      {% endif %}
      {% if link.code %}
      <a href="{{ link.code }}" class="btn btn-sm z-depth-0 btn-code" role="button" target="_blank" style="font-size:12px;">Code</a>
      {% endif %}
      {% if link.slides %}
      <a href="{{ link.slides }}" class="btn btn-sm z-depth-0 btn-slides" role="button" target="_blank" style="font-size:12px;">Slides</a>
      {% endif %}
      {% if link.outreach %}
      <a class="btn btn-sm z-depth-0 btn-outreach" role="button" style="font-size:12px;cursor:pointer;" onclick="toggleOutreach(this)">Outreach</a>
      {% endif %}
      {% if link.bibtex %}
      <a class="btn btn-sm z-depth-0 btn-bibtex" role="button" style="font-size:12px;cursor:pointer;" onclick="toggleBibtex(this)">BibTex</a>
      {% endif %}
      {% if link.others %}
      {{ link.others }}
      {% endif %}
    </div>
    {% if link.bibtex %}
    <div class="bibtex-content" style="display:none;">
      <div class="bibtex-header">
        <span class="bibtex-label">BibTeX</span>
        <button class="bibtex-copy" type="button" onclick="copyBibtex(this)">
          <i class="fas fa-copy"></i><span>Copy</span>
        </button>
      </div>
      <pre>{{ link.bibtex }}</pre>
    </div>
    {% endif %}
    {% if link.outreach %}
    <div class="outreach-content" style="display:none;">
      <ul>
      {% for item in link.outreach %}
        <li><a href="{{ item.url }}" target="_blank">{{ item.title }}</a></li>
      {% endfor %}
      </ul>
    </div>
    {% endif %}
  </div>
</div>
</li>

{% endfor %}

</ol>
</div>

