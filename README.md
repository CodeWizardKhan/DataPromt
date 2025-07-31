BRCCOMNI-10990
PRI-Verify data populating in HTML Page and Excel data

1. Action: Click on Production Report
	Expected Result: Production Report page should open.
2. Action: Click on Customer Communications Inquiry
	Expected Result: The page should navigate to Customer Communications Inquiry from Production Report page.
3. Action: Click submit and excel button.
	Expected Result: Test data should generate in HTML Page and Excel file.
4. Action: Enter the valid data: Verify data populating in HTML page and excel.
	Expected Result: selected test data should be valid :

For this above test scenario generate Serenity Cucumber code with following configuration.

1 Feature File
	Ex: Feature: Job Processing Status Inquiry - Crystal Report Validation

  @issue:BRCCOMNI-10222
  Scenario: PRI - Validate all the fields are displayed in Crystal Report in Job Processing Status Inquiry page
    Given User is on the Production Reports and Inquiries page
    When User clicks on the Job Processing Status Inquiry
    Then The page should navigate to Job Processing Status Inquiry


2. Step Definition Java file
	Ex: public class ProductionReportandInqueriesStepDefs {

    @Steps
    ProductionReportandInqueriesSteps productionReportandInqueriesSteps;


    @Given("User is on the Production Reports and Inquiries page")
    public void userIsOnProductionReportsPage() throws Exception{
        productionReportandInqueriesSteps.navigateToProductionReports();
    }

    @When("User clicks on the Job Processing Status Inquiry")
    public void userClicksOnJobProcessingStatusInquiry() throws Exception{
        productionReportandInqueriesSteps.clickJobProcessingStatusInquiry();
    }

3. Page Java file
	Ex: public class ProductionReportandInqueriesPage extends PageObject {

    @FindBy(xpath = "//div[contains(text(),'Production Reports')]")
    public WebElementFacade  productionReportandInqueriesTitle;

    @FindBy(xpath = "//a[text()='Job Processing Status Inquiry']")//id = "openReport"
    public WebElementFacade jobProcessingStatusInquiryLink;

4. Step Java file
	Ex: public class ProductionReportandInqueriesSteps {


    @Steps
    ProductionReportandInqueriesPage productionReportandInqueriesPage;
    CommonMethods commonMethods;

    private static final Actor report = Actor.named("User");
    private static final Logger logger = LoggerFactory.getLogger(AdministrationSteps.class);

    public void navigateToProductionReports()throws Exception{
        logger.info("navigateToProductionReports() : Start ");

        try{
            productionReportandInqueriesPage.productionReportandInqueriesTitle.waitUntilClickable();
            logger.info("productionReportandInqueriesPage.productionReportandInqueriesTitle.isDisplayed() : "+ productionReportandInqueriesPage.productionReportandInqueriesTitle.isDisplayed());
            Serenity.recordReportData().withTitle("productionReportandInqueriesPage.productionReportandInqueriesTitle.isDisplayed()");
            productionReportandInqueriesPage.productionReportandInqueriesTitle.click();
        }   catch (Exception e){
            logger.info(e.getMessage());
        }
        commonMethods.clickOnSendAnyway();
        logger.info("navigateToProductionReports() : End ");
    }


Once we land in 	
Customer Communications Inquiry Page,

there is dropdown: select T-Mobile Color Statements
Mailed check box: CheckIn
Account test feld: add 106645754
Start Date and End date Text box: add some date.
Submit button: Click

# DataPromt


<div class="crystalstyle" style="margin:24px 24px 24px 24px;top:0px;left:0px;width:1008px;height:768px;"><div id="Box2" style="z-index:10;top:10px;left:0px;width:1002px;height:197px;"><img border="0" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA+oAAADFCAYAAADDjAisAAAEY0lEQVR42u3XwQmAMAxA0c7pJg7kellBaUGRHDxJm8MLPAqhp9x+a2m2/TgBAACAOdrX9A8RAQAAAExyt7hIBwAAgKqxLtIBAACgSKyLdAAAAKgT60IdAAAAhDoAAAAg1AEAAECoAwAAAEIdAAAAhDoAAAAg1AEAAECoAwAAAEIdAAAAhDoAAAAg1AEAAECoAwAAAEIdAAAAhLpQBwAAAKEOAAAACHUAAAAQ6gAAAIBQBwAAAKEOAAAACHUAAAAQ6gAAAIBQBwAAAKEOAAAACHUAAAAQ6gAAAIBQBwAAAKEu1AEAAECoAwAAAEIdAAAAhDoAAAAg1AEAAECoAwAAAEIdAAAAhDoAAAAg1AEAAECoAwAAAEIdAAAAhDoAAAAg1AEAAECoC3UAAAAQ6gAAAIBQBwAAAKEOAAAACHUAAAAQ6gAAAIBQBwAAAKEOAAAACHUAAAAQ6gAAAIBQBwAAAKEOAAAACHUAAABAqAMAAIBQBwAAAIQ6AAAACHUAAABAqAMAAIBQBwAAAIQ6AAAACHUAAABAqAMAAIBQBwAAAIQ6AAAACHUAAABAqAMAAABCHQAAAIQ6AAAAINQBAABAqAMAAABCHQAAAIQ6AAAAINQBAABAqAMAAABCHQAAAIQ6AAAAINQBAABAqAMAAABCHQAAABDqAAAAINQBAAAAoQ4AAABCHQAAABDqAAAAINQBAAAAoQ4AAABCHQAAABDqAAAAINQBAAAAoQ4AAABCHQAAABDqAAAAgFAHAAAAoQ4AAAAIdQAAABDqAAAAgFAHAAAAoQ4AAAAIdQAAABDqAAAAgFAHAAAAoQ4AAAAIdQAAABDqAAAAgFAHAAAAhDoAAAAIdQAAAECoAwAAgFAHAAAAhDoAAAAIdQAAAECoAwAAgFAHAAAAhDoAAAAIdQAAAECoAwAAgFAHAAAAhDoAAAAg1AEAAECoAwAAAEIdAAAAhDoAAAAg1AEAAECoAwAAAEIdAAAAhDoAAAAg1AEAAECoAwAAAEIdAAAAhDoAAAAg1AEAAAChDgAAAEIdAAAAEOoAAAAg1AEAAAChDgAAAEIdAAAAEOoAAAAg1AEAAAChDgAAAEIdAAAAEOoAAAAg1AEAAAChDgAAAAh1AAAAEOoAAACAUAcAAAChDgAAAAh1AAAAEOoAAACAUAcAAAChDgAAAAh1AAAAEOoAAACAUAcAAAChDgAAAAh1AAAAQKgDAACAUAcAAACEOgAAAAh1AAAAQKgDAACAUAcAAACEOgAAAAh1AAAAQKgDAACAUAcAAACEOgAAAAh1xwAAAAChDgAAAAh1AAAAEOoAAACAUAcAAAChDgAAAAh1AAAAEOoAAACAUAcAAAChDgAAAAh1AAAAEOoAAACAUAcAAACh7hgAAAAg1AEAAAChDgAAAEIdAAAAEOoAAAAg1AEAAAChDgAAAEIdAAAA+DHU+4h1AAAAWB/p/R2h/l4AAAAAayL9CXWxDgAAAIUiPcc6AAAAMEeO9Auiip+CP8FUtgAAAABJRU5ErkJggg==" alt="Box2" style="width:1002px;height:197px;position:absolute;"></div><div id="Box1" style="z-index:10;top:744px;left:1px;width:1006px;height:24px;clip:rect(0px,1007px,24px,0px);"><img border="0" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA+0AAAAYCAYAAACP8BwkAAAAzklEQVR42u3XwQmAMBBFwa3TTizI9tKCsoIiOXhMVpkPQ2BJAy+i27JuOwAAADBevC0/tNYAAACACa4uF+wAAADwhXAX7AAAAFAw3AU7AAAA1Ax30Q4AAACiHQAAABDtAAAAINoBAAAA0Q4AAACiHQAAABDtAAAAgGgHAAAA0Q4AAACIdgAAABDtAAAAgGgHAAAARDsAAACIdgAAAEC0AwAAwH+iPSfcAQAAoFaw53tG+/MAAAAAzA/2O9qFOwAAABQN9j7cAQAAgPH6YD8ALA7NMUzS9NkAAAAASUVORK5CYII=" alt="Box1" style="width:1005px;height:24px;position:absolute;"></div><div id="PageHeaderSection1" style="z-index:3;top:0px;left:0px;width:1008px;height:208px;"></div>
<div contextid="CTX_1_0" id="Text1" type="text" class="ad1753986746406-54399-42347-0" style="top:14px;left:4px;width:1002px;height:48px;"><p align="center" style="position:relative;padding-left:1px;font-size:18.0pt;white-space:nowrap;margin:0px;"><span style="line-height:30px;position:relative;display:block;font-size:18.0pt;font-family:Arial;font-weight:bold;"><span class="fc1753986746406-57214-8779-0">Production&nbsp;Statistics&nbsp;by&nbsp;CDF&nbsp;Report&nbsp;</span></span></p><p align="center" style="position:relative;padding-left:1px;font-size:18.0pt;white-space:nowrap;margin:0px;"><span style="line-height:30px;position:relative;display:block;font-size:18.0pt;font-family:Arial;font-weight:bold;"><span>&nbsp;</span></span></p></div>
<div contextid="CTX_1_0" id="Text2" type="text" class="ad1753986746406-54399-42347-0" style="top:153px;left:28px;width:150px;height:16px;"><p style="position:relative;padding-left:1px;font-size:10.0pt;white-space:nowrap;margin:0px;"><span style="line-height:16px;position:relative;display:block;font-size:10.0pt;font-family:Arial;font-weight:bold;"><span class="fc1753986746406-57214-8779-1">Transmit&nbsp;File&nbsp;Name:</span></span></p></div>
<div contextid="CTX_1_0" id="Text28" type="text" class="ad1753986746406-54399-42347-0" style="top:136px;left:28px;width:157px;height:16px;"><p style="position:relative;padding-left:1px;font-size:10.0pt;white-space:nowrap;margin:0px;"><span style="line-height:16px;position:relative;display:block;font-size:10.0pt;font-family:Arial;font-weight:bold;"><span class="fc1753986746406-57214-8779-1">Customer&nbsp;Defined&nbsp;Field:</span></span></p></div>
<div contextid="CTX_1_0" id="Text29" type="text" class="ad1753986746406-54399-42347-0" style="top:81px;left:28px;width:72px;height:16px;"><p style="position:relative;padding-left:1px;font-size:10.0pt;white-space:nowrap;margin:0px;"><span style="line-height:16px;position:relative;display:block;font-size:10.0pt;font-family:Arial;font-weight:bold;"><span class="fc1753986746406-57214-8779-1">Customer:</span></span></p></div>
<div contextid="CTX_1_0" id="Text3" type="text" class="ad1753986746406-54399-42347-0" style="top:57px;left:12px;width:160px;height:24px;"><p style="position:relative;padding-left:1px;font-size:12.0pt;white-space:nowrap;margin:0px;"><span style="line-height:20px;position:relative;display:block;font-size:12.0pt;font-family:Arial;font-weight:bold;"><span class="fc1753986746406-57214-8779-2">Selection&nbsp;Criteria</span></span></p></div>
<div contextid="CTX_1_0" id="Text21" type="text" class="ad1753986746406-54399-42347-0" style="top:118px;left:28px;width:72px;height:16px;"><p style="position:relative;padding-left:1px;font-size:10.0pt;white-space:nowrap;margin:0px;"><span style="line-height:16px;position:relative;display:block;font-size:10.0pt;font-family:Arial;font-weight:bold;"><span class="fc1753986746406-57214-8779-1">Geo&nbsp;Area:</span></span></p></div>
<div contextid="CTX_1_0" id="Text7" type="text" class="ad1753986746406-54399-42347-0" style="top:100px;left:28px;width:72px;height:16px;"><p style="position:relative;padding-left:1px;font-size:10.0pt;white-space:nowrap;margin:0px;"><span style="line-height:16px;position:relative;display:block;font-size:10.0pt;font-family:Arial;font-weight:bold;"><span class="fc1753986746406-57214-8779-1">Corp&nbsp;Type:</span></span></p></div>
<div contextid="CTX_1_0" id="ascustflddesc2" type="field" class="ad1753986746406-54399-42347-0" style="top:136px;left:198px;width:340px;height:16px;white-space:nowrap;"><div align="left" style="position:relative;font-size:10.0pt;"><span class="fc1753986746406-57214-8779-3">CD1&nbsp;test</span></div></div>
<div contextid="CTX_1_0" id="ASCUSTOMERNM1" type="field" class="ad1753986746406-54399-42347-0" style="top:81px;left:198px;width:340px;height:16px;white-space:nowrap;"><div align="left" style="position:relative;font-size:10.0pt;"><span class="fc1753986746406-57214-8779-3">T-Mobile&nbsp;Color&nbsp;Statements</span></div></div>
<div contextid="CTX_1_0" id="ASCORPTYPEDESC1" type="field" class="ad1753986746406-54399-42347-0" style="top:100px;left:198px;width:340px;height:16px;white-space:nowrap;"><div align="left" style="position:relative;font-size:10.0pt;"><span class="fc1753986746406-57214-8779-3">All&nbsp;Corp&nbsp;Types</span></div></div>
<div contextid="CTX_1_0" id="ASGEOAREADESC1" type="field" class="ad1753986746406-54399-42347-0" style="top:119px;left:198px;width:340px;height:16px;white-space:nowrap;"><div align="left" style="position:relative;font-size:10.0pt;"><span class="fc1753986746406-57214-8779-3">All&nbsp;Geo&nbsp;Areas</span></div></div>
<div contextid="CTX_1_0" id="Text5" type="text" class="ad1753986746406-54399-42347-0" style="top:171px;left:28px;width:150px;height:16px;"><p style="position:relative;padding-left:1px;font-size:10.0pt;white-space:nowrap;margin:0px;"><span style="line-height:16px;position:relative;display:block;font-size:10.0pt;font-family:Arial;font-weight:bold;"><span class="fc1753986746406-57214-8779-1">Run&nbsp;Month:</span></span></p></div>
<div contextid="CTX_1_0" id="DT1" type="field" class="ad1753986746406-54399-42347-0" style="top:172px;left:715px;width:282px;height:19px;text-align:right;white-space:nowrap;"><div align="right" style="position:relative;font-size:10.0pt;"><span class="fc1753986746406-57214-8779-4" style="position:absolute;right:0px;">Create&nbsp;Date:&nbsp;July&nbsp;31,&nbsp;2025&nbsp;14:30&nbsp;PT</span></div></div>
<div contextid="CTX_1_0" id="transfilehdr1" type="field" class="ad1753986746406-54399-42347-0" style="top:153px;left:198px;width:340px;height:16px;white-space:nowrap;"><div align="left" style="position:relative;font-size:10.0pt;"><span class="fc1753986746406-57214-8779-3">Displayed</span></div></div>
<div contextid="CTX_1_0" id="ASRUNMONTH1" type="field" class="ad1753986746406-54399-42347-0" style="top:171px;left:198px;width:339px;height:14px;white-space:nowrap;"><div align="left" style="position:relative;font-size:10.0pt;"><span class="fc1753986746406-57214-8779-3">01/2025</span></div></div>
<div id="Picture1" type="ole" class="ad1753986746406-54399-42347-0" style="font-size:0.05pt;top:6px;left:838px;width:165px;height:45px;white-space:nowrap;"><img border="0" src="data:image/png;base64,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" alt="Picture1" style="width:165px;height:45px;position:absolute;"></div>
<div contextid="CTX_1_0" id="Text19" type="text" class="ad1753986746406-54399-42347-0" style="top:184px;left:24px;width:150px;height:16px;"><p style="position:relative;padding-left:1px;font-size:10.0pt;white-space:nowrap;margin:0px;"><span style="line-height:16px;position:relative;display:block;font-size:10.0pt;font-family:Arial;font-weight:bold;"><span class="fc1753986746406-57214-8779-1">&nbsp;Cust&nbsp;File&nbsp;Name:</span></span></p></div>
<div id="PageHeaderSection2" style="z-index:3;top:208px;left:0px;width:1008px;height:64px;"></div>
<div contextid="CTX_1_0" id="Text69" type="text" class="ad1753986746406-54399-42347-0" style="top:215px;left:29px;width:680px;height:56px;"><p style="position:relative;padding-left:1px;font-size:16.0pt;white-space:nowrap;margin:0px;"><span style="line-height:25px;position:relative;display:block;font-size:16.0pt;font-family:Arial;font-weight:bold;"><span class="fc1753986746406-57214-8779-5">No&nbsp;data&nbsp;was&nbsp;found&nbsp;for&nbsp;your&nbsp;query&nbsp;parameters.&nbsp;</span></span></p><p style="position:relative;padding-left:1px;font-size:16.0pt;white-space:nowrap;margin:0px;"><span style="line-height:25px;position:relative;display:block;font-size:16.0pt;font-family:Arial;font-weight:bold;"><span class="fc1753986746406-57214-8779-5">Please&nbsp;alter&nbsp;your&nbsp;parameters&nbsp;and&nbsp;resubmit&nbsp;your&nbsp;query.</span></span></p></div>
<div id="GroupHeaderSection3" style="z-index:3;top:272px;left:0px;width:1008px;height:14px;"></div>
<div id="GroupHeaderSection1" style="z-index:3;top:286px;left:0px;width:1008px;height:16px;"></div>
<div id="GroupHeaderSection2" style="z-index:3;top:302px;left:0px;width:1008px;height:16px;"></div>
<div id="GroupHeaderSection4" style="z-index:3;top:318px;left:0px;width:1008px;height:17px;"></div>
<div id="DetailSection1" style="z-index:3;top:335px;left:0px;width:1008px;height:16px;"></div>
<div id="PageFooterSection1" style="z-index:3;top:741px;left:0px;width:1008px;height:27px;"></div>
<div contextid="CTX_1_0" id="PageNofM1" type="field" class="ad1753986746406-54399-42347-0" style="top:748px;left:918px;width:82px;height:15px;text-align:right;white-space:nowrap;"><div align="right" style="position:relative;font-size:8.0pt;"><span class="fc1753986746406-57214-8779-6" style="position:absolute;right:0px;">Page&nbsp;1&nbsp;of&nbsp;1</span></div></div>
<div contextid="CTX_1_0" id="DTfooter1" type="field" class="ad1753986746406-54399-42347-0" style="top:748px;left:7px;width:170px;height:15px;white-space:nowrap;"><div align="left" style="position:relative;font-size:8.0pt;"><span class="fc1753986746406-57214-8779-6">Create&nbsp;Date:&nbsp;07/31/2025&nbsp;14:30&nbsp;PT</span></div></div>
<div contextid="CTX_1_0" id="Text27" type="text" class="ad1753986746406-54399-42347-0" style="top:748px;left:303px;width:414px;height:15px;"><p align="center" style="position:relative;padding-left:1px;font-size:8.0pt;white-space:nowrap;margin:0px;"><span style="line-height:14px;position:relative;display:block;font-size:8.0pt;font-family:Arial;"><span class="fc1753986746406-57214-8779-6">PR&amp;I&nbsp;-&nbsp;Production&nbsp;Statistics&nbsp;RM&nbsp;Report&nbsp;by&nbsp;CDF.rpt</span></span></p></div>
</div>
