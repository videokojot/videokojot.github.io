---
layout: post
title:  "Nullable reference types in C#8 - what are they?"
date:   2020-04-24 11:14:16 +0200
categories: dev C#
---

I wanted to see what are the new NRT in C#8 and how they affect resulting IL. 

So they are actually doing very nothing to the generated IL - compiler is just adding attribute to mark arguments or return types as nullable. 
This means that all the heavy lifting (determine the null flow and generating warnings on appropriate places) must be done in the compiler/analyzer of the calling code, the code which uses methods/classes with those attributes.

You can see the code below here:
<https://github.com/videokojot/NullableReferenceTypes>

Other useful links:
<https://docs.microsoft.com/en-us/dotnet/csharp/nullable-references> Info about annotation and warning contexts
<https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/attributes/nullable-analysis> More fine grained control of nullablity for generics/ref/out etc. stuff
<https://devblogs.microsoft.com/dotnet/try-out-nullable-reference-types/> Nice article with examples

This code in C#8:
``` csharp
using System;
using System.Runtime.CompilerServices;

internal class Program
{
	public string? MyPropertyNullable
	{
		get;
		set;
	}

	public string MyPropertyNotNullable
	{
		get;
		set;
	}

	private static void Main(string[] args)
	{
		Console.WriteLine("Hello World!");
	}

	private static string returnsNotNull(string? nullableArg, string nonNullableArg)
	{
		return string.Empty;
	}

	private static string? returnsNull()
	{
		return null;
	}
}

```
is somehow equivalent to the code in C#7 (at least according to ILSpy):

``` csharp
using System;
using System.Runtime.CompilerServices;

[System.Runtime.CompilerServices.NullableContext(1)]
[System.Runtime.CompilerServices.Nullable(0)]
internal class Program
{
	[System.Runtime.CompilerServices.Nullable(2)]
	[field: System.Runtime.CompilerServices.Nullable(2)]
	public string MyPropertyNullable
	{
		[System.Runtime.CompilerServices.NullableContext(2)]
		get;
		[System.Runtime.CompilerServices.NullableContext(2)]
		set;
	}

	public string MyPropertyNotNullable
	{
		get;
		set;
	}

	private static void Main(string[] args)
	{
		Console.WriteLine("Hello World!");
	}

	private static string returnsNotNull([System.Runtime.CompilerServices.Nullable(2)] string nullableArg, string nonNullableArg)
	{
		return string.Empty;
	}

	[System.Runtime.CompilerServices.NullableContext(2)]
	private static string returnsNull()
	{
		return null;
	}
}
```
