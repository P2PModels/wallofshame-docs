# Roadmap

In this document we want to write down the features we are considering for development. We use the INVEST principles for that, based in ["How to write user stories" by Stormotion](https://stormotion.io/blog/how-to-write-a-good-user-story-with-examples-templates/)

Note: we should define which features we _need to develope_ to test our idea and whitch features we _could simulate_. As an example we could simulate the register page and provide previously created users to testers. We will mark rank features depending in the degree of importance like this:

!!! important "A feature that needs to be developed"
    Cool and core feature.

!!! warning "A feature that would improve the prototype and doesn't require a great effort"
    Cool and light feature.

!!! danger "A feature that would improve the prototype but also requires a great effort"
    Cool but heavy feature.

Note: this features will have 4 different states:

🟢 if the feature has been developed 

🟡 if the feature has been developed partially 

🔴 if the feature is pending

🔵 if the feature is been developed in a different way


## Development scope

This prototype will tries to tackle a progressive adoption of web3 technologies. In order to succesfully achive this task three different user profiles along with three interfaces have been designed:

1. **Outsider**: in this scenario we encounter a user that wants to use our solution but lacks any knowledge regarding blockchain technology neither has she any intention of getting familiarized with it. She has never used a wallet or any cryptocurrency, she has never heard about a smart contract and she has no intention of learning about it, she just wants to use the website. Therefore the requirements for this scenario is: **Transparent use of web3 technologies through a platform account**. The only ethereum account (EOA) would be the one of P2PModels and it will cover the costs for all the blockchain interactions. As mentioned in [Task assignment in Amara. Prototyping Round Robin with blockchain (I)](https://p2pmodels.eu/task-assignment-in-amara-prototype-round-robin/):

    > The idea behind this component is to cover the costs related to these transactions. We want to spare the users (linguists) this expense, as it could severely affect the user experience and usability of the prototype.

2. **Adopter**: in this scenario we could find a completly nobel user of web3 technologies but interested in learning, or we could find a user with some basic notions about cryptocurrencies and wallets. In both cases, the user prefers a web2 interface but might be interested in some extra info regarding the signer account and recovering it and start using a web3 ui. Therefore the requirements for this scenario is: **Transparent use of web3 technologies with personal account (Ethereum EOA)**. Each user will have its own wallet, with fonds provided by the organization account/using metatransactions, managed by the platform until the user exports it.

3. **Native**: in this scenario the user is completly familiarized with web3 technologies. The platform can be presented as a dApp, requesting user wallet connection, transaction signing, etc. Therefore the requirements are: **Opaque use of web3 technologies through personal account (Ethereum account)** the platform won't have any record about the user.

---

## **WoS - v0.1**: outsiders scenario

The current state of the project covers the following features:

### Milestone | **Landing and info page**

!!! important "As a user I want to see an overview of the project so I can be informed." 
    - 🟢 A landing page is accesible by the user. 
    - 🟢 There is a header with the title of the page, a link to the info page and a call to action to report a case. 
    - 🟢 An interactive map lets the user see the cases (anonymazed). - A dashboard section under the map shows the user the metrics of the currently selected region. 
    - 🟢 An info page with text sections about: ¿what is WoS?, the methodology, ¿Why blockchain? is accesible by the user.

!!! warning "As a user I want to know where to find help so that I can start the report process"  
    - 🔴 When hovering over the header, it grows and fills the whole page with a message to encourage the partcipation.

!!! danger "As a user I want to be guided in the process of contacting an organization and reporting the case so I dont have to put to much effort in learning how the platform works" 
    - 🔴 A chatbot propmts and ask if it can help. - A chatbot guides the user to the main resources close to its location.

#### Epic: Map interaction

!!! important "As a user I want to be able to see the reported cases in a map so I can have a geographical reference of the problem." 
    - 🟢 User can see an informative map of Spain. 
    - 🟢 User can see markers in the map with the number of cases in that area. 
    - 🟢 The data is loaded from the blockchain.

!!! important "As a user I want to be able to interact with the map so I can see the reported cases in different parts of it." 
    - 🟢 User can zoom in and out. 
    - 🟢 User can move the view point up, down, left and right. 
    - 🟢 Information (markers) will split or join based in the zoom value.

!!! important "As a user I want to see the summary of each case represented by a marker so I can understand in depth the situation and empathize." 
    - 🟢 A list of cards shows up when a marker is clicked. 
    - 🟢 Each card has the following fields: random nickname, type of case, proffesion, company name (only if a min number of cases have been reported) & description in a dropdown 
    - 🟢 The list disapears when the close button is clicked. 
    - 🟢 The data is loaded from the blockchain.

!!! warning "As a user I want to filter reported cases by proffesion, region and type of case so I can have a segregated reference of the problem." 
    - 🔴 Three different dropdowns let the user filter the cases by proffesion, city and type of case. 
    - 🔴 Once a filter is selected the map markers are updated.

#### Epic: Responsive dashboard

!!! important "As a user I want to see the metrics used by the tool so I can have a quantitative reference of the problem." 
    - 🟢 User can see a dashboard with plots of the current data stored in the blockchain.

    **Specifications**, the user can see:

    - 🟢 Name of the current region of the data (e.g. Spain, Andalucía, Sevilla).
    - 🟢 Number of reported cases.
    - 🟢 Number of reported cases by type of case.
    - 🟢 Percentage of reported cases by profession.
    - 🟢 Percentage of reported cases by gender.
    - 🟢 Percentage of reported cases by age range.

!!! important "As a user I want to be able to see the metrics by region by selecting markers in the map so I can have a more precise cuantitative reference of the problem depending on location." 
    - 🔴 When the user clicks a cluster of markers the dashboard is refreshed with the data of that list of cases.

#### Epic: Onboarding

!!! warning "As a user I would want to have an initial tour to understand the platform " 
    - 🟢 On the first step it will inform the user about what is this page and its aim
    - 🟢 It will be short enough not to be tedious
    - 🟢 It will cover and explain the main functionalities of the platform
    - 🟢 It's style should be homogeneous with the rest of the app




---

### Milestone | **Case report**


!!! danger "As a user I want to be able to report a case so I can share my experience" 
    - 🟢 A Call to Action is accesible by the user and redirects to the login/form page. 
    - Once logged in the user is redirected to a form page. 
    - 🟢 The user can fill the form and send it to the backend. 
    - 🟢 The case data is saved in the blockchain. 
    - 🟢 While the transaction is being mined the user sees an animation of loading in the form page. 
    - 🟢 When the transaction is confirmed the user is redirected to a confirmation page where a notification will announce the success of the transaction. 
    - 🟢 If the transaction fails a notification will show up with an error text and a button to retry.

#### Epic: Case form

!!! important "As a user I want to be able to provide the details of my case, including the company I work for and my context so I can give visibility to the specific problems of my proffesion and the social groups I belong to. " 
    - There is an accesible form for the user. 
    - The form has two parts: one for the information regarding the company and other for the information regarding the anonimyzed individual. 
    - The form fields are validated and the user is notified if there is an invalid or empty field. 
    - The form state is controlled.

    **Specifications**:

    Part 1

    - Name of the company
    - Type of case: non-payment, delay in payment, abuses
    - Summary of the case 150-500 characters
    - Proofs* (anonimyzed)

    Part 2

    - Region
    - Zip code*
    - Proffesion
    - Gender
    - Age range
    - Expirience

!!! important "As a user I want to store my case in the blockchain without having previous knowledge of this technology so I can give visibility to the specific problems of my proffesion and the social groups I belong to without censorship" 
    - 🟢 Once filled and submited the data of the case is stored in the blockchain without user interaction with web3 technologies. 
    - 🟢 After the transaction is mined, the user is redirected to a confirmation page. 
    - 🟢 The confirmation page has a CtA to return to the landing page. 
    - 🟢 Once the transaction is confirmed the user is notified.

Confirmation shows the emails of authorized users

!!! important "As a user I want to be able to re-send my case to the blockchain so that I don't loose the information I've already provided to the website" 
    - 🟢 Add a retry button.

!!! warning "As a user I want to be able to be reached by organizations that can help with my situation so I can be assited in the process of demanding or leaving the company" 
    - 🟢 The form has a field in the third part regarding contact data to confirm if the user wants to be reached by orgs. 
    - 🟢 The form informs the user of the risks of exposing themselves and asks for confirmation. 
    - 🟢 The user can fill the contact details and save them in the backend server, never in the blockchain. 
    - 🟢 The user can choose to ask for help only or ask for help and the remain as a contact to be reached by others. 
    - The registered organizations close to the user and working in they field are automatically notified that a user is asking for support with a template e-mail that its filled with the user contact details and reported case and sent through an e-mail server.
  
    **Specifications**:
    Part 3 - Checkbox, list of relevant organizations I want to contact.

#### Epic: Case Registry

!!! important "As a user I want to be able to register a case in the blockchain without previous knowledge so I can take advantage of the web3 ecosystem properties."  
    - The submission of the case report form triggers a resolver in the backend to manage the sc interaction. 
    - A tx with the data is sent from the backend server with the P2PModels EOA. 
    - 🟢 The information is stored in the smart contract.

!!! important "As a user I want to be able to check the reported cases in an Ethereum explorer so I can assure that they can't be deleted." 
    - 🟢 Once the case report form is filled and submited the information is stored in a smart contract.

!!! important "As an organization I want to be able to get access to all the relevant data through a decentralized provider so we can assure that the data can't be compromised." 
    - 🟢 The data from reported cases is accessible through a decentralized provider (The Graph).

!!! important "As a user I want to be able to get access to the cases data through a centralized provider so that I can use complementary web2 services." 
    - 🟢 The data from reported cases is accessible through a centralized provider (GraphQL Gateway).

#### Epic: Login

!!! warning "As a user I want to authenticate myself so that I can report my case"
     - 🟡 A page to log in is accesible by the user through a CtA "Report your case".
     - 🟡 If the user provide incorrect credentials an error message will pop up.
     - 🟡 If the user provide correct credentials a session is started and the client receives a unique token for authorizarion.
     - 🟡 Once logged in the user will be redirected to the report form.

    **Specifications**:

    Login form fields

    -   Username (Required)
    -   Password (Required)
    -   Sumbit button

    Authentication errors

    -   Username doesn't exist
    -   Incorrect password

!!! warning "As a user I want to be able to register a profile so that I can report my case from a individual EOA without web3 knowledge"
     - 🟡 In the login page there is a "Register" link that redirects the user to a register page.
     - 🟡 The user is asked to fill the e-mail and password through a form.
     - 🟡 Once submited the user is redirected to the log in page and can now log in.

!!! danger "As a user I want to be able to confirm my e-mail so that I nobody can register with my e-mail adress"
     - 🟡 From the register page, once the form is filled and submited, a prompt message asks the user to check they inbox.
     - 🟡 A e-mail template is filled with the user data and sent through an e-mail server.
     - 🟡 The user receives an e-mail with a link to confirm e-mail.
     - 🟡 When the user clicks the link a request is sent to the backend with a secret, onced validated the e-mail state changes to confirmed.

!!! danger "As a user I want to be able to recover my password so that I can forget it and not loose all data"  
     - 🟡 In the login page there is a "Forgot password" link that redirects to a recovery page.
     - 🟡 The user is asked to fill the e-mail address through a form.
     - 🟡 An e-mail template is filled with user recovery password and sent trough an e-mail server.
     - 🟡 The user receives an e-mail and can log in with the temporary password.
     - 🟡 Once logged in the user is redirected to a change password view.
     - 🟡 The password of the user is updated and the user is redirected to the private area.

!!! danger "As an organization we want to be able to register so that we can be notified if a user is asking for support"

---

### Milestone | **Confirmation page**

!!! important "As a user I want to be able to confirm that my case has been reported so that I can check it in the map."
     - 🟢 Once the transcation is confirmed, the user is redirected to the confirmation page.
     - 🟢 The confirmation page shows a thank you message along a confirmation message and icon/animation.

!!! important "As a user I want to know the metrics of similar cases so that I can get informed of the current situation."
     - 🟢 In the confirmation page there is a section with the number of cases reported from the user's proffesion and region.
     - 🟢 These metrics are loaded from the blockchain.

#### Epic: Contact people with similar cases

!!! important "As a user I want to be able to be reached by others in my situation so I can share my experience one-to-one" 
    - 🟢 The form has a third part regarding contact data. 
    - 🟢 The form informs the user of the risks of exposing themselves and asks for confirmation. 
    - 🟢 The user can fill the contact details and save them in the backend server, never in the blockchain. 
    
    **Specifications**:

    Part 3
    - Risks text
    - Agree*
    - E-mail

!!! warning "As a user I want to be notified that a new case similar to mine has been reported so I can contact the person who reported and share my experience one-to-one" 
    - 🟢 The reporting user can choose to ask for help only, ask for help and then remain as a contact to be reached by others or just remain as a contact. 
    - Other users with similar cases to the one reported are automatically notified that a user is asking for support with a template e-mail that its filled with the user contact details and reported case and sent through an e-mail server.

!!! important "As a user I want to be able to contact people with similar cases so that I can receive help or organize with others to take action."
     - 🟢 In the confirmation page there is a section with e-mails of users with similar cases reported that have authorized to be contacted.

#### Epic: Contact helpful organizations

!!! warning "As a user I want to be informed of helpful organizations so that I can contact them."
     - 🟢 In the confirmation page there is a section with organizations and contact info that can help the user.
     - 🔵 This information is loaded from the backend.
        *Changed*: this information is loaded from a google-sheet

---

### Milestone | **Uncensurable**

!!! important "As an organization we want to be able to replicate this site's relevant data without a central failure point so we can't be censored."
     - All the data provided to the user is accesible through the blockchain.
     - A subgraph with a complete API of the needed requests for the map and dashboard exists in The Graph testnet.
     - The smart contracts are properly documented and the docs are publicly available.

!!! danger "As a user I want to be able to access the web site through web3 technologies so I can't be restricted by governs and tech giants."
     - The frontend is accesible from multiple endpoints.
     - The frontend is allocated in multiple servers working as a network.

---

## **WoS - v0.2**
