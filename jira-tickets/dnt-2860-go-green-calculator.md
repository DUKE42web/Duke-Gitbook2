---
cover: ../.gitbook/assets/Screen Shot 2022-05-04 at 9.17.12 AM.png
coverY: 0
---

# DNT-2860 Go Green Calculator

{% embed url="https://bryan-guner.gitbook.io/duke/jira-tickets/dnt-2860-go-green-calculator" %}

<details>

<summary>New Features</summary>



### **New Simple Calculator Input Warning And Block** **Explanation**\*\*

&#x20;

**The need for this ticket derives from a fictional unit of energy duke created called a block which is "100 kWh of 'green' energy". Because a block requires whole-number outputs that necessitates a minimum input value; which arguably needs to be explained to the user, and if the user fails to heed the instructions... have the warning change color to red if they input a lower number.**

&#x20;

[**Simple Calc Branch**](https://bitbucketp.duke-energy.com/projects/DUKCOM/repos/dxt-jss-public/pull-requests/884/builds)&#x20;

&#x20;

![](https://jiraprod.duke-energy.com/secure/attachment/463555/463555\_Screen+Shot+2022-05-10+at+8.37.55+PM.png)

&#x20;

**i.e. input modulo 100 should return a number not equal to input.**

&#x20;

![](https://jiraprod.duke-energy.com/secure/attachment/463557/463557\_Screen+Shot+2022-05-10+at+9.31.59+PM.png)

#### &#x20;[Abstract](https://app.abstract.com/projects/7d33aa49-f1f0-47eb-971d-893d6457bcbc/branches/4d491d6e-63f5-4bad-951e-0f327cfc047c/commits/afba0d4f418ba1a5f186815496c8331add993f74/files/56AED96A-C786-42FD-8B75-CFA17F1BE644/layers/BB077CE9-8557-4DDA-8C01-FC5575EE35A4?collectionId=123e3638-3117-4bbb-b7b0-8e43052397a8\&collectionLayerId=6d234c60-58b2-4027-a631-e01d158248ab) <a href="#c2-a0abstracthttps-3a-2f-2fapp.abstract.com-2fprojects-2f7d33aa49f1f047eb971d893d6457bcbc-2fbranches" id="c2-a0abstracthttps-3a-2f-2fapp.abstract.com-2fprojects-2f7d33aa49f1f047eb971d893d6457bcbc-2fbranches"></a>

**Additionally the calculator should include an explanation of the fictional unit being used in the output**

i.e.

&#x20;

![](https://jiraprod.duke-energy.com/secure/attachment/463559/463559\_Screen+Shot+2022-05-10+at+9.30.25+PM.png)

When you participate in the GoGreen Ohio program, you’re supporting the advancement of green power sources. Green power is electricity produced from natural resources – like the sun, wind, and water – that do not emit pollutants into the atmosphere.

As a GoGreen Ohio participant, you can match your home’s electricity use by purchasing blocks\* of renewable energy certificates (RECs). These RECs certify the generation of green power on your behalf. Every block you purchase supports the advancement of environmentally friendly, renewable energy sources, thereby reducing dependence on fossil fuels to generate energy.

_\*One GoGreen Ohio program block represents 100 kWh of clean energy. A 10-block purchase (1,000 kWh) equals one REC (1MWh)._

&#x20;

&#x20;\
**This will be a replacement of the existing calculators:**\
**Go Green:** [**https://www.duke-energy.com/home/products/renewable-energy/gogreen-energy**](https://www.duke-energy.com/home/products/renewable-energy/gogreen-energy) **(Ohio jurisdiction, calc is under the Go Green Ohio video)**

**Renewable Advantage:** [**https://www.duke-energy.com/home/products/renewable-advantage**](https://www.duke-energy.com/home/products/renewable-advantage) **(NC jurisdiction, look for "Calculate Your Estimated Cost"**

*
  * **Design questions contact:** [**marcus.wilson@duke-energy.com**![](https://jiraprod.duke-energy.com/images/icons/mail\_small.gif)](mailto:marcus.wilson@duke-energy.com)\


</details>

![](<../.gitbook/assets/Screen Shot 2022-05-04 at 9.47.44 AM.png>) ![](<../.gitbook/assets/Screen Shot 2022-05-04 at 9.47.36 AM.png>)



![](<../.gitbook/assets/Screen Shot 2022-05-04 at 9.17.12 AM (1).png>)

![](<../.gitbook/assets/Screen Shot 2022-04-11 at 10.28.41 AM.png>)

[https://app.abstract.com/projects/7d33aa49-f1f0-47eb-971d-893d6457bcbc/branches/4d491d6e-63f5-4bad-951e-0f327cfc047c/commits/afba0d4f418ba1a5f186815496c8331add993f74/files/56AED96A-C786-42FD-8B75-CFA17F1BE644/layers/BB077CE9-8557-4DDA-8C01-FC5575EE35A4?collectionId=123e3638-3117-4bbb-b7b0-8e43052397a8\&collectionLayerId=6d234c60-58b2-4027-a631-e01d158248ab](https://app.abstract.com/projects/7d33aa49-f1f0-47eb-971d-893d6457bcbc/branches/4d491d6e-63f5-4bad-951e-0f327cfc047c/commits/afba0d4f418ba1a5f186815496c8331add993f74/files/56AED96A-C786-42FD-8B75-CFA17F1BE644/layers/BB077CE9-8557-4DDA-8C01-FC5575EE35A4?collectionId=123e3638-3117-4bbb-b7b0-8e43052397a8\&collectionLayerId=6d234c60-58b2-4027-a631-e01d158248ab)

This will be a replacement of the existing calculators:

Go Green: [https://www.duke-energy.com/home/products/renewable-energy/gogreen-energy](https://www.duke-energy.com/home/products/renewable-energy/gogreen-energy) (Ohio jurisdiction, calc is under the Go Green Ohio video)

Renewable Advantage: [https://www.duke-energy.com/home/products/renewable-advantage](https://www.duke-energy.com/home/products/renewable-advantage) (NC jurisdiction, look for "Calculate Your Estimated Cost"

![](<../.gitbook/assets/Screen Shot 2022-05-23 at 1.32.08 PM.png>)

![](<../.gitbook/assets/Screen Shot 2022-05-23 at 1.32.15 PM.png>)

![](<../.gitbook/assets/Screen Shot 2022-05-23 at 1.32.00 PM.png>) ![](<../.gitbook/assets/Screen Shot 2022-05-23 at 1.31.55 PM.png>)

Design questions contact: Marcus Wilson

|                  SimpleCalc-Min-Val                  |               Go-Green(OH)               |                    Renewable-Advantage(NK)                    |                                               |
| :--------------------------------------------------: | :--------------------------------------: | :-----------------------------------------------------------: | --------------------------------------------- |
| <mark style="color:green;">MatchElectricUsage</mark> | 2<mark style="color:green;">00kWh</mark> |            <mark style="color:green;">250kWh</mark>           | "The minimum kWh that can be entered is"      |
|   <mark style="color:red;">ChooseYourPayment</mark>  |   <mark style="color:red;">$2.00</mark>  | <mark style="color:red;background-color:yellow;">$3.00</mark> | "The minimum amount that can be entered is $" |
