---
title: Visualization
date: '2024-01-01'
type: book
weight: 30
highlight: true
---

Learn how to visualize data with Plotly.

<!--more-->

{{< icon name="clock" pack="fas" >}} 1-2 hours per week, for 8 weeks

## Learn

{{< youtube 4O_o53ag3ag >}}

## Quiz

{{< spoiler text="When is a heatmap useful?" >}}
Lorem ipsum dolor sit amet, consectetur adipiscing elit.
{{< /spoiler >}}

{{< spoiler text="Write Plotly code to render a bar chart" >}}
```python
import plotly.express as px
data_canada = px.data.gapminder().query("country == 'Canada'")
fig = px.bar(data_canada, x='year', y='pop')
fig.show()
```
{{< /spoiler >}}
