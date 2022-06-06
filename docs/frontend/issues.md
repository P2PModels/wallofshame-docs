
## Onboarding

We use React Joyride for the onboarding:

- To highlight only one of the buttons, we use Button.js and we place a span for Joyride in the button with that text.

- To only show the tour the first time, we use the prop run and a callback function

- When we use disableBeacon on every step, we have no beacon but it obligues us to follow every step.

- When you clicked the close button, a beacon appeared and we were not able to take it away. Thus, the solution was to not render the close button of the onboarding, as we have the skip button which does the same.

In order to show the onboarding only once for each user, we use the variable Localstorage: we have to give it an initial value.


Some functionality and design decisions where made:
1. No beacon (the red dot)
2. 4º step only appears in the report button
3. The tour only renders the first time.
4. Names of buttons are changed to spanish

## Map


In order to change the icon, we place a new icon called punteroMapa in the file config.json instead of the smart-logo.


## Retry button in Report form

When the form was sent and an error occurred, all the information entered by the user was lost. To avoid this, we create a retry button.

- We use the variable error to see if an error occurred in sendReport.

- We create a new retry button and show it when when an error occurs, not showing the end one.

- We show an info dialog with the retry button thanks to a hook called showInfoDialogRetry and error. Both have to be true for the dialog to appear. The hook is set to true every time you start the second part of the report, hence the infodialog is only shown once for every retry: open={showInfoDialogRetry && error}


## Sticky heading in CardList

In modaltitle, we changed css to be sticky and top 0.
We put the title in a grid with className in order to have a white opaque background. We had changed the padding of the container.

## Coordinates of barcelona

Changed by looking the correct ones in google.

## Bug with enter

When in the report we pressed enter, the report was sent.

We include an e in useForm: 
const submit = (e, queryFcn, payload) => e => {


## Google Sheet for contanting organizations

First, we tried to use sheet.best, which allows us to take our Google Sheet data and export it as a JSON object. It conects with the google sheet. The key is this [link](https://docs.google.com/spreadsheets/d/1w2J9DuzFHkUmBQ0zHHY51gPY7NRzmbdUV_VckSfhbSA/edit#gid=0). We needed to have the sheet public for everyone with the url.


In order to render and filter by job and region: we used the function filter.
We used the function *includes* for the jobs because we can have more than one job in the sheet for the same organization. 


However, we had a problem: sheet.best only allows 250 views. Change of plans. We needed another way to achieve it.

We followed the steps in this [web](https://dev.to/calvinpak/how-to-read-write-google-sheets-with-react-193l)
We created a google account in the [GoogleCloudPlatform](https://console.developers.google.com/) that will have access to the google sheet: 
p2psheet@p2psheet.iam.gserviceaccount.com 
For this reason, we needed to share the sheet with this mail, so that it can have access to interact with the spreadsheet.

To install it, we used:
npm install  google-spreadsheet

We added the credentials to a .env to privatize them. Using the specific functions that connect the sheet with the code, we are able to obtain the different rows of the google sheet. 

In this sheet, the data should be written in a special way:

- The first row must contain the names with which we will identify each column.

- We can write the following rows.

- We should not write data elsewhere in order to avoid problems.

We used useEffect and hooks for async