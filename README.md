
# StreeTunes

## Overview
StreeTunes is a web based application where street musicians can store their music and create unique, single-use QR (Quick-Response), codes to share to purchasers who are interested in hearing more of their music. StreeTunes also provides extensive data and analytics about download volume so that artists can optimize their distribution efforts. A QR code is only valid for scan ONCE. Upon clicking the download link generated from a scanned QR, it's path is deleted from the database of valid paths.

Our application helps street musicians connect to their listeners in a more modern way, but providing both the musician and their consumer a technology-friendly way to share their music. Our application will also help them reduce costs and increase business on their end since they will not have to go out of their way to buy and produce actual CDs!

There are 3 separate docker containers used, each representing a database (shard), musician_id will serve as the sharding key across all models except User and Profile (which are on auth_db).


## Important notes
Please assess app.code only under the branch "new-deployment" - this branch shows the most updated application.


## Technologies used
* Backend: Python(2.7) and Django(1.9) on Apache Webserver
* Frontend: Django templates, HTML/CSS/Javascript, Google Maps API
* Deployment: AWS (Amazon Web Services)


## Data Model
The application will store User, Profile, Album, Purchase, Song
* musicians can have multiple albums
* each album can contain multiple songs
* the purchase model represents a single purchase
* a purchase refers to one 'version' of an album -- to avoid conflicts if/when musicians change albums between QR code creation and download on consumer side
* the "version_hash" denotes the name of the zip file containing a version of that album


## User Stories or Use Cases
1. as a musician (already-registered user), I can upload songs to the app (to the cloud) and can generate QR codes on demand as I wish
2. as a purchaser (anonymous user, who recieves a QR code), I can scan a QR code from a musician and download the zip file of that album
3. as a unregistered musician I can sign up for an account, then have the ability to perform step 1^
4. as an anonymous user, I can view the analytics page
5. as a musician (already-registered user) I can update my profile details with details about my Gender, Music Genre, and Age

## Test Account Created
* Site URL: https://streeTunes.williamtsao.com/streeTunes
	* Please open in Chrome
	* The browser will tell you your connection "is not private" through using HTTPS
	* Please click "Advanced", then "Proceed"
	* Please allow the site to access your camera and location (for full functionality of site)
* Log in using a test account we created:
	* Username: yairsovran
	* Password: lswaproject12
* Navigate the site through the menu on the left-hand side
* Enjoy the pre-populated albums/songs!
