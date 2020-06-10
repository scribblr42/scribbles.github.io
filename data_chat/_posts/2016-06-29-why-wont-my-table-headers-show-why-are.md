---
layout: post
title: Why won't my table headers show? Why are they concatenating? - Quick Tableau
  Tip!
date: '2016-06-29T17:06:00.000+01:00'
author: VizScribbler
tags:
- how to
- tutorial
- tableau
- tip
modified_time: '2017-01-09T12:51:47.588Z'
thumbnail: https://4.bp.blogspot.com/-3Oao53jatdA/V3PvptR_UnI/AAAAAAAAA7Y/SHXtHr7EXBECbVA10aVsxfjT1p_pCo6GgCLcB/s72-c/Animation.gif
blogger_id: tag:blogger.com,1999:blog-5138343082934398153.post-8250218051835060508
blogger_orig_url: https://vizscribbler.blogspot.com/2016/06/why-wont-my-table-headers-show-why-are.html
---

<i>So, some of these images are broken, and it's been a few years and I'm not sure what they were.. so.... sorry..</i>

While with a client, my colleague Jules and I had the same issue on the same day. Puzzled, we reached out to the wider Information Lab team and learnt something completely new! I'll explain below.<br /><div><br /></div><div><b>The issue was this;&nbsp;</b></div><div><br /></div><div class="separator" style="clear: both; text-align: center;"><a href="https://4.bp.blogspot.com/-3Oao53jatdA/V3PvptR_UnI/AAAAAAAAA7Y/SHXtHr7EXBECbVA10aVsxfjT1p_pCo6GgCLcB/s1600/Animation.gif" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="184" src="https://4.bp.blogspot.com/-3Oao53jatdA/V3PvptR_UnI/AAAAAAAAA7Y/SHXtHr7EXBECbVA10aVsxfjT1p_pCo6GgCLcB/s640/Animation.gif" width="640" /></a></div><div><br /></div><div>Basically, if you have 7 dimensions on the 'rows' shelf, the first two get concatenated, or disappear. But when you taken off the last one and make it six, it reappears.&nbsp;</div><div>Was this a bug or by design?&nbsp;</div><div><b><br /></b></div><div><b>Tableau rockstars to the rescue!</b></div><div>André was the first to respond, knocking it out of the park with the solution. Check out the .gif below.</div><div><br /></div><div class="separator" style="clear: both; text-align: center;"></div><div class="separator" style="clear: both; text-align: center;"><a href="https://3.bp.blogspot.com/-A_FFWaq-vzA/V3PxkcwpDzI/AAAAAAAAA7s/6mvnZ4P2II0SpxDZkNWOUir6-50JwMYawCLcB/s1600/Animation.gif" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="330" src="https://3.bp.blogspot.com/-A_FFWaq-vzA/V3PxkcwpDzI/AAAAAAAAA7s/6mvnZ4P2II0SpxDZkNWOUir6-50JwMYawCLcB/s640/Animation.gif" width="640" /></a></div><div><br /></div><div><br /></div><div>Chris Love also chipped in to inform us that if you're looking to include 16 or more columns, then the .xml is a great place to go.</div><div><br /></div><div>Pretty cool, huh! It is if, like Jules and I, you weren't aware of this. Of course, this is probably a Google-able issue, and one that is easy to find online.</div>
