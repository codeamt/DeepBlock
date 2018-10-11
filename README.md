# DeepBlock

# Introduction

For the final Capstone Project of the [Grow With Google Developer](https://sites.google.com/udacity.com/gwgdevscholarship/home) Scholarship Program (and conjointly [Udacity's Android Developer Nanodegree](https://in.udacity.com/course/android-developer-nanodegree-by-google--nd801) program), students were asked to design and build an original app (written in Java) from scratch. 

DeepBlock, my Captone project, is a blockchain app that gives machine learning researchers with limited computing resources an outsourced solution for training deep learning projects. 

Researchers, use our app to submit projects in need of training. Blockchain Miners, pool mobile computing power with other users to help train AI and earn cryptocurrency.

## Intended Users

- Machine Learning Researchers
- Blockchain Miners

## Features

- Email/Oauth2 Authorization, GitHub Integration
- Distributes ad-hoc AI training sessions
- Rations project-based payouts
- AI model indexing with stats published blockchain
- Ethereum-based mobile wallet included

# Phase 1: Specs & Wireframes (Preview)


## User Authorization Interface Flow
<p align="center">
  <img src="https://ucarecdn.com/3e41bf64-4144-4c10-9d19-4e53cff90fc6/" width="70%" height="60%" />
</p>

The above UI map details the authorization flow for the app. Users have two initial options:<br><br>
**(1)** registration for new users and<br> 
**(2)** Sign In for returning users. 

One step further into the flow, users have the option of using GitHub to authenticate for access. First time users will be directed to an onboarding interface to input additional profile data before the Main Activity screen.

## Home-to-Menus Interface Flow 

<p align="center">
  <img src="https://ucarecdn.com/5009fefa-448a-4d68-a777-a7020bce92f8/" width="70%" height="60%" />
</p>

The above UI map details the primary navigation options for the app. Users have two navigation menus available to them:<br><br>
**(1)** the ide nav drawer and<br>
**(2)** the options menu located in the app bar. 

The nav drawer presents an unordered list of links to additional in-app activities. If a user opts for uploading an avatar, this image will be displayed in the nav drawer header, above the user’s primary email.

The app bar options menu will be consistent for all parent activities, offering quick access to logout action or launching the Settings activity.

The Main Activity for this app is a blockchain ledger archiving past deep learning / machine learning models that have been completely trained using the app’s ensemble training method.
These “deep blocks” offer topical info about the project, such as number of users that worked on the model, the final accuracy metric, and the total number of epochs from all training sessions. In terms of blockchain consensus, these deep blocks verify that a model was fully trained.

## Project Dashboard Interface Flow

<p align="center">
  <img src="https://ucarecdn.com/20f4a361-f18f-4748-bb8f-ed95075a7f92/" width="70%" height="60%" />
</p>

Digging deeper into additional in-app activities, the above UI map illustrates how a user’s projects will be organized in their respective dashboard. The tab layout provides a distinct way to toggle between the two types of projects a user can create in the app:<br><br>(1) research project submissions and<br>(2)sessions where the user has contributed some percentage of computing power towards the research owner’s overarching goal. 

Drilling deeper into either of these types of projects leads the user to the Project Detail Activity that itemizes training assets, the research submission team, an abstract, metrics for logged loss and weight averaging, and a list of users that have trained the model to some capacity.

## Wallet Utilities Interface Flow

<p align="center">
  <img src="https://ucarecdn.com/6999d1b9-ba83-483e-bdc8-c487da44b7d8/" width="70%" height="60%" />
</p>

Again, digging deeper into additional in-app activities, the above UI map illustrates how a user’s wallet will look and function. 

With every block mined (e.g., model trained), users that contributed to mining that block (e.g., training that model) will receive a payout (unitized with db) for the work they contributed towards a project’s goal. 

Clicking through to view a transaction receipt evokes a modal with metadata about the payout.


## Project Discovery Interface Flow 

<p align="center">
  <img src="https://ucarecdn.com/c70c4cb6-ca1e-4765-a8e7-279e07ca8d64/" width="70%" height="60%" />
</p>

The above UI map details the project discovery flow for the app. Upon launching the Discovery Activity from the nav drawer, the user transitions to a collection of projects in need of more training. A tab layout segments projects by neural network classes (e.g, Natural Language Processing, Computer Vision, etc.) and each project has a status indicator about its current stage in training.

The User has two options for proceeding:<br><br>
**(1)** Pressing the FAB to submit a new project and<br> 
**(2)** drilling deeper on a project to launch its respective Project Detail Activity. 

The Project Detail Activity presents yet another FAB that launches an activity for configuring a Neural Network fitting session, followed by a neural network training session itself for a number of epochs specified by the end user. The Session configuration allows enables users to customize device settings (e.g., secondary storage and hardware acceleration) to optimize performance.

## Network Explorer Flow  

<p align="center">
  <img src="https://ucarecdn.com/d6b00fc4-e3ad-4033-bb84-4261d03f7b9b/" width="70%" height="60%" />
</p>

The above UI map details the network exploration flow for the app. 

Users have two options:<br><br> 
**(1)** view network performance stats or<br>
**(2)** view historical index of pricing, and the USD at a the current time. 

**Note:** pricing tab will be further fleshed out in future iterations of the project.

## Home Screen Widget User Interface Flow

<p align="center">
  <img src="https://ucarecdn.com/f7e641c2-79fc-4edf-8ac9-44cc7611dd20/" width="70%" height="60%" />
</p>

The above UI map details the home screen widget flow for the app. 

The widget pairs with the Session Activity to broadcast the progress of training. Clicking through on the widget calls the Session UI back into the foreground. In future iterations, Users will be able to pause/resume Session from the Home/Lock Screen interfaces. 

## Key Considerations
***How will your app handle data persistence?***<br><br>
I’ll use Room to persist 90% of data in the form of 2-3 SQL tables, and attempt to use IPFS to cache unstructured data otherwise persist these files to a Firebase DB. I’ll also use Shared Preferences for storing user defined preferences. 

***Describe any edge or corner cases in the UX.***<br><br>
Users have options for importing (in addition to uploading) their NN models and training data by, syncing with a GitHub account.

The screen that ties with the Neural Network Fitting Session Activity will likely consume a lot of power. Users can pre-configure session settings to balance between hardware acceleration and battery usage, according to their preferences. These changes will be reflected in the Settings Activity.  

Users will be able to press a pause/play button that saves the current model and reloads the necessary files from the appropriate file path for continuation of the training session.

***Libraries***<br>

- Retrofit v2.4.0
- Room, Lifecycle Components v1.1.1
- Java IPFS v1.2.2
- DeepLearning4j v1.0.0-beta2, ND4J-native v0.7.2
- Web3j v3.5.0
- Support Libraries v7:27.1.1, v8
- ExpansionPanel v1.1.1
- Indefinite Pager Indicator v1.0.9
- Android hardware, os.hardware and os.storage modules v27
- GSON v2.8.5, Parceler v1.1
- Butterknife v8.8.1






