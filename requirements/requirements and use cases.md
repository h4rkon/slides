# Top-Level Requirements and Use Cases

## 1. Review Document

### Use Cases:
- **Show Document:** Review Document Data
- **Review Changes:** Review Changes
- **Visualize Delta:** Visualize Delta
- **Reset Delta Visualization:** Reset Delta Visualization

## 2. Change Document

### Use Cases:
- **Checkout for Edit:** Checkout Document for Edit
- **Make Changes:** Modify Document
- **Release Lock:** Release Exclusive Lock

## 3. Transition Phases

### Use Cases:
- **Create Major Version/Next Phase:** Create Major Version/Next Phase

## 4. Collaboration

### Use Cases:
- **Give Comments:** Add Comments

## 5. Manage Documents

### Use Cases:
- **Import Document:** Import Document
- **Export Document:** Export Document
- **Close Document:** Close Tab, Return to Dashboard

# List of Use Cases

## Login
   - Title: Automatic Login via SSO
   - Description: When accessing the dashboard URL or a deep link, the user is automatically logged in through single sign-on; if the user is eligible, the content is displayed, otherwise, an appropriate message is shown.

## Dashboard Overview
   - Title: View Dashboard Overview
   - Description: Users can view an overview of all entries, each representing a tracker document.

## Document Access
   - Title: Access Specific Document
   - Description: Users can click on an entry in the dashboard to view the specific tracker document.

## Show Document
   - Title: Review Document Data
   - Description: The user can review all data recorded in the specific document within the tracker app. The data is displayed as read-only unless the user has an exclusive lock on the document.

## Give Comments
   - Title: Add Comments
   - Description: A user can leave a comment at the document level or for each specific value within the document.

## Review Changes
   - Title: Review Changes
   - Description: The user can review any changes made at both the document and value levels.

## Checkout for Edit
   - Title: Checkout Document for Edit
   - Description: The user can check out an unlocked and currently open document to exclusively lock it for changes. No other user can lock this document unless the initiating user releases the lock again.

## Make Changes
   - Title: Modify Document
   - Description: The user with an acquired exclusive lock on the currently open document can:
     - Change values in text fields
     - Select options
     - Choose from options (combo box) and display as text
     - Add attachments
     - Remove attachments

## Close Document
   - Sub-use Case 9a: Close Tab
     - Title: Close Tab
     - Description: The user closes the tab showing the document, which results in logging out.
   - Sub-use Case 9b: Return to Dashboard
     - Title: Return to Dashboard
     - Description: The user clicks the link to return to the dashboard.

## Release Lock
    - Title: Release Exclusive Lock
    - Description: The user can release the exclusive lock on the currently open and exclusively locked document, creating a new sub-version of the document. The user can provide a comment for the check-in.

## Import Document
    - Title: Import Document
    - Description: A user can click "import a document" on the dashboard view, by selecting the target template and the document from the local file system. The dashboard shows the newly imported document.

## Export Document
    - Title: Export Document
    - Description: A user can export a document from the dashboard by selecting one document in the list and clicking the export button.

## Create Major Version/Next Phase
    - Title: Create Major Version/Next Phase
    - Description: A user can create a major version and declare the next phase of an open, not exclusively locked document. While creating the new version, the user can leave a comment.

## Visualize Delta
    - Title: Visualize Delta
    - Description: A user can visualize the delta of an open and unlocked document between two versions by defining the "compare from" and "with" fields. The currently open document shows changes between these versions colored in red.

## Reset Delta Visualization
    - Title: Reset Delta Visualization
    - Description: The user can press the "reset delta" button to remove the colored visualization and show the open and read-only document again.


# States Overview

## 1. Authenticated
- **Description:** The user has successfully logged in via single sign-on and is eligible to access the application.

## 2. Dashboard Visible
- **Description:** The dashboard is displayed, showing an overview of all entries, each representing a tracker document.

## 3. Document Open, Read-Only
- **Description:** A specific document is open for review. The data is displayed as read-only.
- **Sub-states:**
  - **With Comments Added:** Comments have been added to the document.
  - **With Changes Reviewed:** Changes to the document have been reviewed.

## 4. Document Open, Write Enabled
- **Description:** A specific document is open and editable due to the user having an exclusive lock on the document.
- **Sub-states:**
  - **With Comments Added:** Comments have been added to the document.
  - **With Changes Reviewed:** Changes to the document have been reviewed.

## 5. Document Open, Read-Only, Visualized Delta
- **Description:** The document is open for review, showing changes between two versions highlighted in red. The data is displayed as read-only.

## 6. Not Logged In
- **Description:** The user is not logged into the application.