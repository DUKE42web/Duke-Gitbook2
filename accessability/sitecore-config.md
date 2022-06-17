# Sitecore Config

| The purpose of this spreadsheet is to allow values to be changed in lower environments. After EVERY deployment, the lower environments (Test, QA, etc) have their master databases restored from Production. That is great news that most of the conten is fresh but one issue is that any values that are hard coded for production, are also hard coded for the lower environments. There needs to be a way to modify these "production" values to their lower environment equivalents. That is where this spreadsheet comes in. This spreadsheet is used against each new database restore to update the production values to their lower environmetn equivalents. |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Item - The full sitecore path to the item that needs to be modified.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| GUID - The GUID to the item that needs to be modified.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Field - The name of the field on that item that needs to be modified. If you specify the value of DELETEME, this item will be DELETED from Sitecore.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Dev, Test, UAT, HotFix, QA, PFT - Each of these columns contains the change that is need for that specific environment. This is the REPLACEMENT value.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Prod - The value that is being search for which will be replaced by one of the lower environment column valued.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| So how does this work? If you have a value that needs to be updated, you will need to add a row and specify ALL the values. ALL the columns are required. In many instanced, the column values may be the same (for instance, Test and UAT and Hotfix may be all the same).                                                                                                                                                                                                                                                                                                                                                                                           |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Now here is the caveat. The contents of the Prod column is the driver. That value MUST exist in the lower environments field that is to be replaced (or it will not update). Also, this column value DOES NOT have to be the complete value for the Production field. Only the value that needs to be replaced. Ok, so that is confusing so lets show a couple of examples.                                                                                                                                                                                                                                                                                           |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Example 1:                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| There is a field "Google Analytics Body Code" that contains this complete value:                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| <p>&#x3C;!-- Google Tag Manager (noscript) retainstyle--><br>&#x3C;noscript>&#x3C;iframe src="https://www.googletagmanager.com/ns.html?id=GTM-N6GDT9" height="0" width="0" style="display:none;visibility:hidden">&#x3C;/iframe>&#x3C;/noscript><br>&#x3C;!-- End Google Tag Manager (noscript)--></p>                                                                                                                                                                                                                                                                                                                                                                |
| We need to have the value in Test/UAT/Hotfix modified to this:                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| <p>&#x3C;!-- Google Tag Manager (noscript) --><br>&#x3C;noscript>&#x3C;iframe src="https://www.googletagmanager.com/ns.html?id=GTM-N6GDT9&#x26;gtm_auth=3voUst9VwgohH28csS13-g&#x26;gtm_preview=env-1559&#x26;gtm_cookies_win=x" height="0" width="0" style="display:none;visibility:hidden">&#x3C;/iframe>&#x3C;/noscript><br>&#x3C;!-- End Google Tag Manager (noscript) --></p>                                                                                                                                                                                                                                                                                    |
| If you look at the entire value, there is only one change. The value of id=GTM-N6GDT9 has come content appended to it. So in the spreadsheet, the Prod column should specify:                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| id=GTM-N6GDT9                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| And the Test and UAT and Hotfix columns should specify:                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| id=GTM-N6GDT9\&gtm_auth=3voUst9VwgohH28csS13-g\&gtm_preview=env-1559\&gtm_cookies_win=x                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| There is no need to specify the entire contents. Just specify the value that needs to be change and then the value to be changed to.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Example 2:                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| There is a field "Link URL" that contains this complete value:                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| \<link text="Register Now" linktype="external" url="https://progress-energy.com/app/LoginRegistration/register.aspx?RC=progress-energy.com%2Fapp%2FUtilityConsultant%2Flist.aspx" anchor="" target="" />                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| We need to have the value in Test/UAT/Hotfix modified to this:                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| \<link text="Register Now" linktype="external" url="https://dev.progress-energy.com/app/LoginRegistration/register.aspx?RC=dev.progress-energy.com%2Fapp%2FUtilityConsultant%2Flist.aspx" anchor="" target="" />                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| If you look at the entire value, there is only one change. The value of the url:                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| "https://progress-energy.com/app/LoginRegistration/register.aspx?RC=progress-energy.com%2Fapp%2FUtilityConsultant%2Flist.aspx                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| And the Test and UAT and Hotfix columns should specify:                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| [https://dev.progress-energy.com/app/LoginRegistration/register.aspx?RC=dev.progress-energy.com%2Fapp%2FUtilityConsultant%2Flist.aspx](https://dev.progress-energy.com/app/LoginRegistration/register.aspx?RC=dev.progress-energy.com%2Fapp%2FUtilityConsultant%2Flist.aspx)                                                                                                                                                                                                                                                                                                                                                                                          |
| There is no need to specify the entire contents. Just specify the value that needs to be change and then the value to be changed to.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| The ability to only need to specify what needs to be changed vs the entire field is quite noticeable on certain very large fields (Rich Text).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |