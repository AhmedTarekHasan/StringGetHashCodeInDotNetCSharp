<link rel="canonical" href="https://www.developmentsimplyput.com/post/when-string-gethashcode-in-net-c-drives-you-crazy" />

# When String.GetHashCode() in .NET C# Drives You Crazy
### Know when to depend on String.GetHashCode() in .NET C#, and when not.

<p align="center">
  <img src="https://static.wixstatic.com/media/488a99_127af5026f354e39b96849d8f7bc1d4f~mv2.png">
</p>

<br/>

<p>
I was working on a side project of a tool to help me with my daily work. In one module, I needed to keep track of some transactions which could be executed between the tool runs. In other words, when I close and open the tool, these transactions should be there.
</p>

<br/>

<p>
For storage, I used a SQLite database where I save a hash-code of an entity representing my Transaction class. I was depending on this hash-code as at some point the tool would generate a new hash-code and compare it to the one already saved in the database.
</p>

<br/>

<p>
So, after setting everything in place, I started the tool, give it a try, yes… it is working. I close the tool, do some stuff, then try testing another thing, now it is not working as it should!!
</p>

<br/>

<p>
I kept trying to understand what is going on and finally I got it. The hash-code comparison is not working fine. During the same run session of the tool, the comparison is working fine. However, when I close and open the tool, the newly generated hash-code -to the same exact transaction-is not the same as the one saved in the database.
</p>

<br/>

<p>
I searched the internet and found that this is true.
</p>

<br/>

<p>
Therefore, I am now sharing this with you and I am going to tell you how to overcome this in a good way.
</p>

<br/>

If you are interested into reading more about this topic, you can read [the rest of the article][Article]. 

<br/>

## If you want to support me:
▶ Subscribe to Medium using [my referral link][Membership]<br/>
▶ Subscribe to [Medium Newsletter][Subscribe]<br/>
▶ Subscribe to [LinkedIn Newsletter][Newsletter]<br/>
▶ Follow me on [Medium][Blog]<br/>
▶ Follow me on [Twitter][Twitter]<br/>
▶ Follow me on [LinkedIn][LinkedIn]

<br/>

## Authors:
* [Ahmed Tarek Hasan]


[Ahmed Tarek Hasan]: https://medium.com/@eng_ahmed.tarek
[Blog]: https://medium.com/@eng_ahmed.tarek
[Membership]: https://medium.com/@eng_ahmed.tarek/membership
[Subscribe]: https://medium.com/subscribe/@eng_ahmed.tarek
[Twitter]: https://twitter.com/AhmedTarekHasa1
[LinkedIn]: https://www.linkedin.com/in/atarekhasan/
[Friend Links]: https://www.linkedin.com/feed/update/urn:li:activity:6866082670108143616/
[Newsletter]: https://www.linkedin.com/newsletters/development-simply-put-6866647119655247872/
[Article]: https://www.developmentsimplyput.com/post/when-string-gethashcode-in-net-c-drives-you-crazy
