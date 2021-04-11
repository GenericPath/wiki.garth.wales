---
description: How to Git gud.
---

# Git

### Submodule \(repo in a repo\)

{% tabs %}
{% tab title="Existing .gitmodules" %}
```text
git submodule init
git submodule update
```
{% endtab %}

{% tab title="Fresh clone" %}
```
git clone <...> --recurse-submodules
```
{% endtab %}
{% endtabs %}



