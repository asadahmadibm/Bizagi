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
     4- define form 
     3- user fill form insert record in WFCASE and WORKITEM  and LeaveRequest
     4- after each step insert to   WORKITEM and pre record in update to Completed state
     5- important table
     WORKITEMSTATE
     BABIZAGICATALOG
     vwBA_Catalog3_BABIZAGICAT_ALL


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
