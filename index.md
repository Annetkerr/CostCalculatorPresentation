---
title       : Using the Cost Calculator Tool
subtitle    : Presentation Using Slidify
author      : Anne Kerr
job         : Developing Data Products Class Project
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [shiny, interactive, bootstrap]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides

---



## What is the Cost Calculator all about?


This application calculates the estimated costs of two methods 
of implementing a specific software solution.

Standalone Sites    -OR-   A Shared Site

![](e:/coursera/developing data products/shinyappcostcalculator/costcalcpresentation/assets/sasmall.jpg)      - OR -
![](/assets/shsmall.jpg)


Let's say a company is willing to subsidize the cost of implementing the software for each of its branch offices. There are two options: purchasing a separate site for each office, or implementing a single site at the main office and sharing it with the branches. The home office wants to see estimate the costs of each options, given different assumptions. This tool helps them do it. 

---

## Input Variables - Standalone Sites


The tool allows the user to maniuplate a slider control to adjust the number of branches offices using each option. It also allows the user to enter assumptions about the overhead costs of supporting each option, as well as a percentage of staff support time the home office will subsidize.

<div class="row-fluid">
  <div class="span4">
    <form class="well">
      <div>
        <label class="control-label" for="nStandalone">Number of Standalone sites:</label>
        <input id="nStandalone" type="slider" name="nStandalone" value="10" class="jslider" data-from="0" data-to="33" data-step="1" data-skin="plastic" data-round="FALSE" data-locale="us" data-format="#,##0.#####" data-smooth="FALSE"/>
      </div>
      <div>
        <label class="control-label" for="sasupportfactor">Assumed annual cost of standardization across standalone sites: ($K)</label>
        <input id="sasupportfactor" type="slider" name="sasupportfactor" value="30" class="jslider" data-from="0" data-to="60" data-step="1" data-skin="plastic" data-round="FALSE" data-locale="us" data-format="#,##0.#####" data-smooth="FALSE"/>
      </div>
    </form>
  </div>
  <div class="span8"></div>
</div>



---


## Input Variables - Shared Site


The tool allows the user to maniuplate a slider control to adjust the number of branches offices using each option. It also allows the user to enter assumptions about the overhead costs of supporting each option, as well as a percentage of staff support time the home office will subsidize.

<div class="row-fluid">
  <div class="span4">
    <form class="well">
      <div>
        <label class="control-label" for="nShared">Number offices using shared site:</label>
        <input id="nShared" type="slider" name="nShared" value="10" class="jslider" data-from="0" data-to="33" data-step="1" data-skin="plastic" data-round="FALSE" data-locale="us" data-format="#,##0.#####" data-smooth="FALSE"/>
      </div>
      <div>
        <label class="control-label" for="aasupportfactor">Assumed annual cost of standarization in shared site: ($K)</label>
        <input id="aasupportfactor" type="slider" name="aasupportfactor" value="25" class="jslider" data-from="0" data-to="50" data-step="1" data-skin="plastic" data-round="FALSE" data-locale="us" data-format="#,##0.#####" data-smooth="FALSE"/>
      </div>
      <div>
        <label class="control-label" for="sharedsupportsubsidy">Assumed percent shared Systems Admin paid by main office: (%)</label>
        <input id="sharedsupportsubsidy" type="slider" name="sharedsupportsubsidy" value="50" class="jslider" data-from="0" data-to="100" data-step="1" data-skin="plastic" data-round="FALSE" data-locale="us" data-format="#,##0.#####" data-smooth="FALSE"/>
      </div>
    </form>
  </div>
  <div class="span8"></div>
</div>

---


## Output

A simple table displays the calculated cost based on the input assumptions.

For example, 


```
##       Option Count     cost
## 1 Standalone    10 $176,220
## 2     Shared    15 $172,311
```

When 10 offices use standalone sites, and overhead per site is assumed to be $12K annually, the annual cost to the main office is $176,220.

When 15 offices are using the shared site, overhead per is assumed to be $2K annually, and the main office pays 50% of the support costs, the annual cost to the main office is $172,000.


