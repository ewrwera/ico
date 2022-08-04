Add driver to txtsetup.sif

𝐃𝐨𝐰𝐧𝐥𝐨𝐚𝐝 𝐡𝐞𝐫𝐞 ===> https://is.gd/8RtTnR?309957

.

.

.

.

.

.

.

.

.

.

.

.

Which, unfortunately, is not supported by Windows XP "out of the box". Normally in these situations, you'd press F6 during the boot process, and insert a driver disk. Trouble is, this machine has no floppy drive, and Windows does not want drivers on CD-ROM during this phase of the installation process.
So what can I do? This requires the following steps:. The driver would normally come in the form of a set of files: as a minimum, a. Once you found the files, you need to compress them with the makecab utility, e.
This compression step is apparently necessary, otherwise the installation process would be looking for the correct checksum in the txtsetup.
I haven't actually verified this, I am just following the advice I read elsewhere. Note You must use signed drivers. Note the lack of a backslash; also note the trailing period at the end of the line. The driver does not ship with Windows XP. If you are loading an updated mass-storage device driver for one that ships with Windows XP: The correct mass-storage driver is provided in the location specified by OemPnPDriversPath. The driver is signed and is a more recent version than the one provided with Windows XP.
If you are loading a new mass-storage device driver that did not ship with Windows XP: The driver is new not included with Windows XP , signed, and installs properly during text-mode Setup.
Posted August 7,  Thank-you for your response. Any ideas?! Br4tt3 Posted August 7,  Good luck to u There is one thing even though I dont think it will matter for the functionality See what happens!
Posted August 7, edited. Thanks for all your help!! Posted August 8,  Cheers for all your help, its much appreciated!! Br4tt3 Posted August 8,  SIF method! There are much info within MSFN, some good links to start of with if u thinking about this approach are: Gosh's site Raskren's guide My last issue..
Hope it helps Posted February 3, edited. Create an account or sign in to comment You need to be a member in order to leave a comment Create an account Sign up for a new account in our community. Register a new account. Filed under: Beginners Guides.
External Mfg. Website: PCstats. Contents of Article: PCstats Guides. Step 1: Copying the source files to your hard drive Pg 3. Step 2 Con't: Installing the service packs Pg 4. Step 3. Share More sharing options Followers 0. Recommended Posts. Posted November 9, edited. Just a small idea: Would it be possible to edit txtsetup. So the benefits would be: 1- the ability to do F6 to load MassStorage drivers 2- An accurate Progress bar when copying file in the first stage?
There could be drawback also: 1- cmdlines. Link to comment Share on other sites More sharing options Posted November 9,  In a word, yes! Wraith Posted November 9,  I believe it should've been "if it hadn't been for you meddling kids! Incidentally, the first suggestion is a failure! Posted November 15,  Posted November 20,  Posted December 13,  Create an account or sign in to comment You need to be a member in order to leave a comment Create an account Sign up for a new account in our community.