---
layout: default
title: "Dashboard Analisi Dati"
plotly: true
header_type: hero
header_img: assets/images/plotly-gallery.png
header_title: "Plotly Charts"
subtitle: "How to embed Plotly charts in your Jekyll pages"
---

You can add interactive charts to your pages using the `plotly-graph.html` include. To embed a Plotly chart, you need to export the chart as an HTML file and place it in the `assets/charts/plotly/` directory.
{: .lead}

<br>
---

# From Python to the Web

Plotly is a powerful Python library for interactive data visualization. To display a Plotly chart on your website, export the chart as an HTML file.

### Exporting a Plotly Chart

Given any Plotly `figure`:

```python
import plotly.graph_objects as go

# Example data
fig = go.Figure(data=[go.Bar(x=['A', 'B', 'C', 'D', 'E'], y=[28, 55, 43, 91, 81])])


# Save the chart as an HTML file
fig.write_html("grafico1.html", include_plotlyjs=False, full_html=False, div_id="grafico1")
```

`full_html=False` exports only the chart, not a full HTML page.

`div_id="grafico1"` sets the ID for the chart's container, which you can reference in your page.

**Place the exported grafico1.html file in the assets/charts/plotly/ directory.**

#### Example of export of a Plotly Chart

[Colab Notebook Example](https://colab.research.google.com/drive/18L-aGb1r3HlfTNprgBfqqlWxge4cqF4L?usp=sharing){:target="_blank"} 

<br>
---

### Embedding the Chart in a Jekyll Page
To display the chart, use the following tag in your markdown file:

{% raw %}
```markdown
{% include plotly-graph.html id="grafico1" file="grafico1.html" height="500px" %}
```
{% endraw %}
  
Parameters:

- `id`: ID of the container div (required)
- `file`: name of the HTML file with the chart (required)
- `path`: custom path (default: /assets/charts/plotly/)
- `height`: chart height (default: 500px)
- `width`: chart width (default: 100%)
- `class`: additional CSS classes (optional)

<br>

# Plotly Chart Example

{% include plotly-graph.html id="grafico1" file="grafico1.html" height="500px" %}