---
title: 'Draft: LoRaWAN Devices'
source: 'draft/devices/1'
---

## Examples

### Vendor

{% highlight yaml %}
{% include {{ page.source }}/examples/acme.yaml %}
{% endhighlight %}

### End Device

{% highlight yaml %}
{% include {{ page.source }}/examples/sensor.yaml %}
{% endhighlight %}

#### End Device Profile

{% highlight yaml %}
{% include {{ page.source }}/examples/profile.yaml %}
{% endhighlight %}

## Definition

{% highlight json %}
{% include {{ page.source }}/schema.json %}
{% endhighlight %}
