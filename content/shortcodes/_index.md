+++
title = 'shortcode'
date = 2023-11-03T18:08:01+09:00
draft = true
+++

## icon

* code
{{< highlight go-html-template "lineNos=table" >}}
    {{< icon name="fa-github" style="fab" size="64px" >}}
    {{< icon name="fa-github" style="fab" size="32px" >}}
    {{< icon fa-github b >}}
{{< /highlight >}}

* result   
  {{< icon name="fa-github" style="fab" size="64px" >}}
  {{< icon name="fa-github" style="fab" size="32px" >}}
  {{< icon fa-github b >}}

* suorce   
  https://fontawesome.com/icons?d=gallery&s=brands,solid&m=free/

## alert

* code
{{< highlight go-html-template "lineNos=table" >}}
    {{% alert primary %}}**this** is a primary{{% /alert %}}
    {{% alert theme="info" %}}**this** is a text{{% /alert %}}
    {{% alert theme="success" %}}**Yeahhh !** is a text{{% /alert %}}
    {{% alert theme="warning" %}}**Be carefull** is a text{{% /alert %}}
    {{% alert danger %}}**Beware !** is a text{{% /alert %}}
    {{% alert dark %}}**Dark !** is a dark{{% /alert %}}
    {{% alert light %}}**oooh !** is a light{{% /alert %}}
    {{% alert secondary %}}**Wait !** is a secondary{{% /alert %}}
{{< /highlight >}}

* result
{{% alert primary %}}**this** is a primary{{% /alert %}}
{{% alert theme="info" %}}**this** is a text{{% /alert %}}
{{% alert theme="success" %}}**Yeahhh !** is a text{{% /alert %}}
{{% alert theme="warning" %}}**Be carefull** is a text{{% /alert %}}
{{% alert danger %}}**Beware !** is a text{{% /alert %}}
{{% alert dark %}}**Dark !** is a dark{{% /alert %}}
{{% alert light %}}**oooh !** is a light{{% /alert %}}
{{% alert secondary %}}**Wait !** is a secondary{{% /alert %}}

## gist

* code
{{< gist byungkwonc 4c2f910c428561200f99ff56103b108e >}}