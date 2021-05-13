---
description: How to Git gud
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

{% tab title="Pull" %}
```
git pull --recurse-submodules
```
{% endtab %}
{% endtabs %}

To remove tracked files, that should be ignored from .gitignore

```text
git rm -r --cached . && git add . && git commit -am "Remove ignored files"
```

