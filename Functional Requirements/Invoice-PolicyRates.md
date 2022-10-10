#Title Calculation/Policy Rates Calculation

##Overview
The PRC calculates the loan’s and owner’s policy or premium that needs to be paid whenever there is a loan or a lender, the calculation depends on the state, transaction type, underwriter, close form, and rate type. Both policies need to be purchased by the homebuyer, however, there are some states where the seller is the one that pays for the Loan’s Policy. Also, the Owner's policy is an optional purchased, still is recommended to purchase both of them.  

##Enable Title Calculation or Policy Rates Calculation

REQ-IS-001
    WHERE the File has the address in CT, MA, or RI,
    WHEN the user opens the File,
    the app shall add the 'Title Calculation' Section as enabled.

REQ-IS-002.     
    WHERE the FILE doesn’t have the address in CT, MA, or RI,
    WHEN user opens the FILE,
    The app shall not show the ‘Title Calculation’ section as enabled.

##Admin/Database Configuration Switch
REQ-SC-001
    WHILE the user is inside Admin configuration,
    WHEN user clicks on Sysconfig option,
    the app shall open all the features configuration.

REQ-SC-002.
    WHILE the user is on features configuration,
    WHEN user switches on a feature and clicks on ‘Accept’ button,
    the app shall enable the feature on its respective section/place.

REQ-SC-003.
    WHILE the user is on features configuration,
    WHEN user switches off a feature and clicks on ‘Accept’ button,
    the app shall disable the feature on its respective section/place.

##Premium Calculations

### Generic Requirements

REQ-GEN-001.
    WHEN user selects the premium type and transaction different from construction,
    the app shall always show standard and enhanced option.

REQ-GEN-002.
    WHEN user selects a file with address in MA,
    the app shall enable the ‘First Time Homeowner’ option.

REQ-GEN-003.
    WHEN user selects any premium type,
    the app shall enable Standard & Enhanced Policy option.

REQ-GEN-004.
    WHEN user already calculated, but made a change on a field,
    The app shall ask for a re-calculation with the new changes to update the final amounts.

WHERE the FILE has the address in CT, MA, or RI, and Transaction Type is ‘Residential’,
### Premium Calculations - Residential (PCR)

REQ-PCR-001
    WHEN user selects ‘Residential’ property type,
    the app shall enable the transactions: purchase, purchase with cash, refinance, refinance (reissue), and construction.

REQ-PCR-002
    WHEN user selects ‘Purchase’ transaction,
    the app shall enable the premium types: loan policy only, owner policy only, and both.

REQ-PCR-003 (SPECIFIC SCENARIO)
    WHEN user already has paid the settlement,
    the user can ask for a Owner Policy only for a Purchase with mortgage transaction.

REQ-PCR-004
    WHEN user selects purchase and Loan Policy only,
    the app shall show ONLY the Loan policy calculation.

REQ-PCR-005
    WHEN user selects purchase and both premium types,
    the app shall show the calculation of both policies.

REQ-PCR-006
    WHILE premium types is for both,
    WHEN user didn’t add purchase price or loan amount, and clicks on ‘Calculate’ button,
    the app shall show a message to enter a value to the respective field to have a calculation.

REQ-PCR-007
    WHEN the liability loan amount is different from the loan amount,
    the app shall consider the liability amount instead of the loan amount for the calculation.

REQ-PCR-008
    WHILE the transaction selected is ‘Purchase w/cash’
    the app shall enable only the premium for Owner Policy.

REQ-PCR-009
    WHEN user selects the Owner Policy and clicks ‘Calculate’ button,
    The app shall show the calculation of the owner’s policy (standard or enhanced).

REQ-PCR-010
    WHEN the transaction selected is ‘Refinance’ or 'Refinance (reissue),
    the shall enable only the loan policy premium.  

REQ-PCR-011
    WHEN the transaction selected is ‘Refinance’ or 'Refinance (reissue) and loan policy only,
    the app shall show the calculation of the loan’s policy (standard or enhanced).

WHERE the FILE has the address in CT, MA, or RI, and Transaction Type is ‘Commercial’,
### Premium Calculation - Commercial (PCC)

REQ-PCC-001
    WHEN user selects ‘Commercial’ property type,
    the app shall enable the transactions: purchase, purchase with cash, refinance, refinance (reissue), and construction.

REQ-PCC-002
    WHEN user selects ‘Purchase’ transaction,
    the app shall enable the premium types: loan policy only, owner policy only, and both.

REQ-PCC-003 (SPECIFIC SCENARIO)
    WHEN user already has paid the settlement,
    the user can ask for a Owner Policy only for a Purchase with mortgage transaction.

REQ-PCC-004
    WHEN user selects purchase and Loan Policy only,
    the app shall show ONLY the Loan policy calculation.

REQ-PCC-005
    WHEN user selects purchase and both premium types,
    the app shall show the calculation of both policies.

REQ-PCC-006
    WHILE premium types is for both,
    WHEN user didn’t add purchase price or loan amount, and clicks on ‘Calculate’ button,
    the app shall show a message to enter a value to the respective field to have a calculation.

REQ-PCC-007
    WHEN the liability loan amount is different from the loan amount,
    the app shall consider the liability amount instead of the loan amount for the calculation.

REQ-PCC-008
    WHEN the transaction selected is ‘Refinance’ or 'Refinance (reissue),
    the shall enable only the loan policy premium.  

REQ-PCC-009
    WHEN the transaction selected is ‘Refinance’ or 'Refinance (reissue) and loan policy only,
    the app shall show the calculation of the loan’s policy (standard or enhanced).

## Endorsements

REQ-END-001
    WHILE user is on the ‘Title Calculation’ screen,
    the app shall show the ‘Line Item Charge’ section with the ‘Add Charge’ or '+' button to add endorsements.

REQ-END-002
    WHILE user is on the ‘Title Calculation’ screen,
    WHEN user clicks on ‘Add Charge’ or '+',
    the app shall add a new row with a combo box where the catalog of endorsements can be selected depending on the state.

REQ-END-003
    WHILE user is adding a charge,
    WHEN user selects the endorsement desire,
    the app shall fill the row with the default values depending on the admin settings and the state and also the

REQ-END-004
    WHEN a new charge is added and user double clicks the row,
    the app shall open a ‘Line Item Detail’ window in case the user wants to make an override.  

REQ-END-005
    WHILE user is on the ‘Line Item Detail' window,
    WHEN user clicks on ‘OK’ button,
    the app shall close the window and make the changes done by the user on the row added in ‘Title Calculation’ screen.

REQ-END-006
    WHILE user is on the ‘Line Item Detail' window,
    WHEN user clicks on ‘Cancel’ button,
    the app shall close the window and don’t make changes.

## User override

REQ-OR-001
    WHILE user is in the ‘Title Calculation’ section,
    WHEN user selects a field and the field can be override,
    the app shall show the checkbox to be checked if the user wants to override.

REQ-OR-002
    WHEN user checks an override checkbox,
    the app shall enable the field for the user to modify.

REQ-OR-003
    WHEN user accepts the override changes,
    the app shall make the necessary changes on the ‘Title Calculation’ section and re-calculations if necessary.

REQ-OR-004
    WHEN user accepts the override changes and affects directly the Policy calculation,
    the app shall ask the user to re-calculate the policies.
