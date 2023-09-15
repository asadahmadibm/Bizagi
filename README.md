# Bizagi

## 7 مرحله دارد        
     ساخت فرایند یا Process model
    ایجاد data model
    طراحی فرم
    تعییین قواعد کسب و کار Business rule
     تخصیص کاربران
    مرحله integration
    اجرا
## Help Table

     WFCLASS درخواست مرخصی
     WORKFLOW  ->   TASK   اجزای ورک فلو
     
     WFCASE رکوردهای ثبت درخواست
     1- after define process insert record in WFCLASS then insert record in WORKFLOW as version
     2- define task insert records in TASK
     3- define data model insert in ATTRIB and Make Entity LeaveRequest
     4- define form save in binary into BARENDERCACHE for temp maybe
     3- user fill form insert record in WFCASE and WORKITEM  and LeaveRequest
     4- after each step insert to   WORKITEM and pre record in update to Completed state
     5- important table
     WORKITEMSTATE
     BABIZAGICATALOG
     vwBA_Catalog3_BABIZAGICAT_ALL

## Tools
     Devexpress
     telerik
     hangfire
## API Refrence

     We recommend you enable API to grant access so you can make full use of the OData services.
	
     1-Register an OAuth application -> Work Portal -> Admin>Security -> OAuth2 Applications -> Add grant access to an external application
     2. Get the authorization token
          2-1 : Encode [Client Id]:[Client Secret] with base64 in https://www.base64encode.org/,
          2-2 : Open the Postman
     -------------------------------------------------------------------------------------------
    https://desktop-3kqcogv/HRBizagi/oauth2/server/token
     Headers : Keys value :
     Content-Type Basic ZTkzNzUxY2EzMGUzYTZkYTk4ODg5N2FkZWRjYzhkMGE4ODA3YTc2M2U1ZGQxN2RlYzNkYzYzMDk2NWQxODI0ODphMTA0Yjg4NDE2Yjg3N2NhZTg0ZTc3YzBlMmM5NmE5Mjc1OGMyY2I4YTNkYTIwZGQ0ZjYwMDAwZThiMWE2MWM5
     Authorization application/x-www-form-urlencoded
      Body tab -> raw in Text -> grant_type=client_credentials&scope=api
     return
     
     {
         "access_token": "144eb417290721e30405267c5167678e28ae62be841726efe25e30abe3b0e338",
         "token_type": "bearer",
         "expires_in": 1073001600,
         "scope": "api openid",
         "http_status_code": 200
     }
     --------------------------------------------------------
    https://desktop-3kqcogv/HRBizagi/odata/query/entity -> no body
    https://desktop-3kqcogv/HRBizagi/odata/data/cases?$top=2&$skip=0&$count=true 
    https://desktop-3kqcogv/HRBizagi/odata/data/cases(10)
    https://desktop-3kqcogv/HRBizagi/odata/data/processes
    https://desktop-3kqcogv/HRBizagi/odata/data/searchByCaseNumber(caseNumber='10')
    
     Headers : Keys value :
     Content-Type Bearer 144eb417290721e30405267c5167678e28ae62be841726efe25e30abe3b0e338
     Authorization application/json

     return

     {
    "@odata.context": "https://desktop-3kqcogv/HRBizagi/odata/data/$metadata#cases(10)",
    "@odata.id": "https://desktop-3kqcogv/HRBizagi/odata/data/cases(10)",
    "@processEntityKey": "25cae22b-6ed4-40d8-bbcc-ac95289ce884",
    "id": 10,
    "caseNumber": "10",
    "creationDate": "2023-09-07T16:05:49+03:30",
    "estimatedSolutionDate": "2023-09-15T16:05:49+03:30",
    "solutionDate": null,
    "processName": "درخواست مرخصی",
    "closed": false,
    "parameters": [
        {
            "xpath": "actionDate",
            "value": ""
        },
        {
            "xpath": "attachment",
            "files": []
        },
        {
            "xpath": "description",
            "value": "dddddddddd"
        },
        {
            "xpath": "endDate",
            "value": "2023-09-08T00:00:00"
        },
        {
            "xpath": "HrSaveDate",
            "value": ""
        },
        {
            "xpath": "isOk",
            "value": null
        },
        {
            "xpath": "mandeh",
            "value": null
        },
        {
            "xpath": "requestDate",
            "value": "2023-09-07T16:05:49"
        },
        {
            "xpath": "requestDescution.name",
            "value": null
        },
        {
            "xpath": "startDate",
            "value": "2023-09-09T00:00:00"
        }
    ]
}
--------------------------------------------------------------------------------
	Send Master Detail
	{
	  "startParameters": [
	       {
	           "xpath": "MyProcessEntity.MyCollection",
	           "type": "collection",
	           "rows": [
	                         {
	                   "columns": [
	                         {
	                          "xpath": "FullName",
	                           "value": "Juliette Leroy"
	                       },
	                       {
	                           "xpath": "Income",
	                           "value": "300000"
	                       }
	                   ]
	               },
	               {
	                   "columns": [
	                         {
	                           "xpath": "FullName",
	                           "value": "Piotr Blanter"
	                       },
	                       {
	                           "xpath": "Income",
	                           "value": "300000"
	                       }
	                   ]
	              }
	           ]
	       }
	   ]
	}

 

 ## Font farsi iranyekan
         copy asset directory from source-rtl
         change bizagi-default-theme.css in path : C:\Bizagi\Projects\HRBizagi\WebApplication\ThemeBuilder\libs\css
         @font-face {
          	font-family: iranyekan;
          	font-style: normal;
          	font-weight: bold;
          	src: url('../assets/fonts/IranYekan/eot/iranyekanwebbold(fanum).eot');
          	src: url('../assets/fonts/IranYekan/eot/iranyekanwebbold(fanum).eot?#iefix') format('embedded-opentype'), /* IE6-8 */
          	url('../assets/fonts/IranYekan/woff2/iranyekanwebbold(fanum).woff2') format('woff2'), /* FF39+,Chrome36+, Opera24+*/
          	url('../assets/fonts/IranYekan/woff/iranyekanwebbold(fanum).woff') format('woff'), /* FF3.6+, IE9, Chrome6+, Saf5.1+*/
          	url('../assets/fonts/IranYekan/ttf/iranyekanwebbold(fanum).ttf') format('truetype');
          }
          
          @font-face {
          	font-family: iranyekan;
          	font-style: normal;
          	font-weight: 300;
          	src: url('../assets/fonts/IranYekan/eot/iranyekanweblight(fanum).eot');
          	src: url('../assets/fonts/IranYekan/eot/iranyekanweblight(fanum).eot?#iefix') format('embedded-opentype'), /* IE6-8 */
          	url('../assets/fonts/IranYekan/woff2/iranyekanweblight(fanum).woff2') format('woff2'), /* FF39+,Chrome36+, Opera24+*/
          	url('../assets/fonts/IranYekan/woff/iranyekanweblight(fanum).woff') format('woff'), /* FF3.6+, IE9, Chrome6+, Saf5.1+*/
          	url('../assets/fonts/IranYekan/ttf/iranyekanweblight(fanum).ttf') format('truetype');
          }
          
          @font-face {
          	font-family: iranyekan;
          	font-style: normal;
          	font-weight: normal;
          	src: url('../assets/fonts/IranYekan/eot/iranyekanwebregular(fanum).eot');
          	src: url('../assets/fonts/IranYekan/eot/iranyekanwebregular(fanum).eot?#iefix') format('embedded-opentype'), /* IE6-8 */
          	url('../assets/fonts/IranYekan/woff2/iranyekanwebregular(fanum).woff2') format('woff2'), /* FF39+,Chrome36+, Opera24+*/
          	url('../assets/fonts/IranYekan/woff/iranyekanwebregular(fanum).woff') format('woff'), /* FF3.6+, IE9, Chrome6+, Saf5.1+*/
          	url('../assets/fonts/IranYekan/ttf/iranyekanwebregular(fanum).ttf') format('truetype');
          }
          html,
          body {
          	
             font-family: iranyekan !important;
          }
