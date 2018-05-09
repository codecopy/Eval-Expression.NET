---
layout: default
title: LINQ Dynamic - Distinct
description: C# Dynamic LINQ Distinct examples using an Expression Evaluator.
permalink: linq-dynamic-distinct-examples
---

{% include template-h1.html %}

## LINQ Dynamic Distinct Examples
{{ page.description }}

- [Distinct - 1](#distinct---1)
- [Distinct - 2](#distinct---2)

## Distinct - 1
This C# example uses the LINQ Distinct method with a dynamic expression to remove duplicate elements in a sequence of factors of 300.

### LINQ
{% highlight csharp %}
int[] factorsOf300 = {2, 2, 3, 5, 5};

var uniqueFactors = factorsOf300.Distinct();

Console.WriteLine("Prime factors of 300:");
foreach (var f in uniqueFactors)
{
	Console.WriteLine(f.ToString());
}
{% endhighlight %}
{% include  component-try-it.html href='https://dotnetfiddle.net/p6rdJI' %}

### LINQ Execute
{% highlight csharp %}
int[] factorsOf300 = {2, 2, 3, 5, 5};

var uniqueFactors = factorsOf300.Execute<IEnumerable<int>>("Distinct()");


Console.WriteLine("Prime factors of 300:");
foreach (var f in uniqueFactors)
{
	Console.WriteLine(f.ToString());
}
{% endhighlight %}
{% include  component-try-it.html href='https://dotnetfiddle.net/uMxKIt' %}

### Result
{% highlight text %}
LINQ Execute Test
------------------------------
Prime factors of 300:
2
3
5

{% endhighlight %}

## Distinct - 2
This C# example uses the LINQ Distinct method with a dynamic expression to find the unique Category names.

### LINQ
{% highlight csharp %}
var products = getList();

var categoryNames = products.Select(x => x.Category).Distinct();

Console.WriteLine("Category names:");
foreach (var n in categoryNames)
{
	Console.WriteLine(n);
}
{% endhighlight %}
{% include  component-try-it.html href='https://dotnetfiddle.net/TZUcdy' %}

### LINQ Execute
{% highlight csharp %}
var products = getList();

var categoryNames = products.Execute<IEnumerable<string>>("Select(x => x.Category).Distinct()");

Console.WriteLine("Category names:");
foreach (var n in categoryNames)
{
	Console.WriteLine(n);
}
{% endhighlight %}
{% include  component-try-it.html href='https://dotnetfiddle.net/gC6H2M' %}

### Result
{% highlight text %}
LINQ Execute Test
------------------------------
Category names:
Beverages
Condiments
Produce
Meat/Poultry
Seafood
Dairy Products
Confections
Grains/Cereals

{% endhighlight %}