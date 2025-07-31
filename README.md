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



