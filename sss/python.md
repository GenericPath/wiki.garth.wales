---
description: Mostly snake related
---

# Python

### pip

{% tabs %}
{% tab title="Packages from a file \(in format of pip freeze\)" %}
```text
pip install -r requirements.txt
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
 [pipdeptree](https://pypi.org/project/pipdeptree/) can be used to visualise the dependencies and top-level packages
{% endhint %}

### Anaconda

{% hint style="info" %}
When installing in windows, ensure 'Add to PATH' is selected
{% endhint %}

{% hint style="info" %}
conda create --name cosc420 python=3.8
{% endhint %}

{% hint style="info" %}
When using Git bash, add [conda.sh](http://conda.sh) to ~/.bashrc   
e.g. `echo ". ${PWD}/conda.sh" >> ~/.bashrc`   
\([source](https://discuss.codecademy.com/t/setting-up-conda-in-git-bash/534473)\)
{% endhint %}

