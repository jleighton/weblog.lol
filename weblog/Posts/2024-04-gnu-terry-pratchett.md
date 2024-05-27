title: GNU Terry Pratchett
date: 2024-04-28 12:37
Author: jamesleighton
Category: How-To
Tags: Books, Discworld, Networking
Slug: gnu-terry-pratchett
Status: published
commentsid: 112348650963494945
og_image: images/2024/10.12.12TerryPratchettByLuigiNovi1.jpg
og_summary: It is Sir Terry Pratchett's birthday today so here is a quick guide on how to setup the GNU Terry Pratchett Tribute using Cloudflare.
---
It is Sir Terry Pratchett's birthday today so here is a quick guide on how to setup the GNU Terry Pratchett Tribute using Cloudflare.

> "A man is not dead while his name is still spoken."
<cite>&mdash; Going Postal, Chapter 4 prologue</cite>
<hr />

>  In Terry Pratchett's Discworld series, the clacks are a series of semaphore towers loosely based on the concept of the telegraph. Invented by an artificer named Robert Dearheart, the towers could send messages "at the speed of light" using standardized codes. Three of these codes are of particular import:<br />
>
>    G: send the message on<br />
>    N: do not log the message<br />
>    U: turn the message around at the end of the line and send it back again<br />
>
>When Dearheart's son John died due to an accident while working on a clacks tower, Dearheart inserted John's name into the overhead of the clacks with a "GNU" in front of it as a way to memorialize his son forever (or for at least as long as the clacks are standing.) 
<cite>&mdash; [GNUTerryPratchett.com](http://www.gnuterrypratchett.com/)</cite>

<hr />
 <div class="row">

<div class="col-md-3">
    <div class="thumbnail">
      <a href="https://commons.wikimedia.org/w/index.php?curid=22449958">
        <img src="/images/2024/10.12.12TerryPratchettByLuigiNovi1.jpg" alt="Sir Terry Pratchett" style="width:100%">
        <div class="caption">
          <p>Sir Terry Pratchett Photo By Luigi Novi, CC BY 3.0</p>
        </div>
      </a>
    </div>
  </div>

</div>

## How to Add 'X-Clacks-Overhead' to Cloudflare

Log into your Cloudflare dashboard, go to your website, select Rules>Transform Rules then click on Modify Response Header

![Cloudflare Dashboard](/images/2024/gnu-terry-pratchett-01.png)

Click 'Create Rule', and give it a useful name like 'GNU Terry Pratchett':

![Creating a new Response Header Rule](/images/2024/gnu-terry-pratchett-02.png)

Select 'All Incoming Requests' under 'When Incoming Requests Match':

![Setting the match rules](/images/2024/gnu-terry-pratchett-03.png)

Finally, choose 'Set Static', enter the header name of 'X-Clacks-Overhead' and the value of 'GNU Terry Pratchett':

![Setting the header itself](/images/2024/gnu-terry-pratchett-04.png)

Finally, click 'Deploy'.

You can check that it's working by running 'curl -v https://semaj.omg.lol' and checking the headers that come back:

![HTTP Headers showing x-clacks-overhead](/images/2024/gnu-terry-pratchett-05.png)