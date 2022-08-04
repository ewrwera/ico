Driver detective error 1001

𝐃𝐨𝐰𝐧𝐥𝐨𝐚𝐝 𝐡𝐞𝐫𝐞 ===> https://is.gd/8RtTnR?20518

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

Join our site today to ask your question. This site is completely free -- paid for by advertisers and donations. If you're not already familiar with forums, watch our Welcome Guide to get started.
Join over , other people just like you! Forums New posts Search forums. What's new New posts Unanswered threads Latest activity. Members Current visitors. Log in Sign up. Search titles only. Search Advanced search…. New posts. Search forums. Log in. Sign up. Computer problem? Tech Support Guy is completely free -- paid for by advertisers and donations. Click here to join today! JavaScript is disabled.
For a better experience, please enable JavaScript in your browser before proceeding. Thread starter m. Status This thread has been Locked and is not open to further replies.
The original thread starter may use the Report button to request it be reopened but anyone else with a similar issue should start a New Thread. AND , you got "Error  In order to stop service first and delete them you have to fill ServiceContol table of the MSI and then StopServices, DeleteServices actions will recognize what to they have to stop and delete , like this:. OpenView query : CheckError view. Execute : CheckError. And, btw, if you don't want to change the strategy, please don't rely on SequenceID in MSI table, it can be change, you have to get the at the runtime.
See also more advanced explanation of how MSI works here. Also I had to tweak the Conditions for some of the service actions. These may be wrong as I'm still not able to do exactly what I want on an upgrade stop service, replace all files regardless of version, start service so take these with a grain of salt. Delete service by using; sc delete "Name of service". Ask a question. Quick access. Search related threads.
Remove From My Forums. Answered by:. Archived Forums. ClickOnce and Setup. Sign in to vote. Hi everybody, I wrote a "Class Library" project which is a service using Visual Stodio recently, then tried to use a Visual Studio Setup Project to install it.
Here is what I did for the "Class Library": 1. Finish the program. Add Installer 3. Change the serviceInstaller so that "StartType" to be Aotumatic 4. Add the exe file built from the "Class Library" project to the Application Folder 2.
Change the property of the project so that "RemovePreviousVersion" to be true 4. Two things I notived: 1. After unstall, the registry was not cleaned up about the installed program 2. The specified service already exists" My questions are: 1. How to cleanup the registry when uninstall a program? How to deal with the "Error  The specified service already exists"? Thanks a lot! Tuesday, June 3, PM.
Thanks Phil! I tried to add the exe file for the service to the Rollback and Uninstall nodes on the "Custom Action" Editor of the Setup project, build the Setup project, run the msi file, but still got the same error. Additional questions: 1. Should I always add the exe file for the service to Rollback and Uninstall nodes?
As far as my experience, the exe file was removed from the installation directory after removing it using Add or Remove Programs. But the registry was not clean up. So, 2. How to change the Setup project so that the registry will be cleaned upon uninstalled? After I removed the ProjectInstaller. I need the ProjectInstaller. Is there other ways to do so? You'll definitely get the same error if that service is still there on the system and you haven't deleted it. This is why Virtual PC is useful for testing.
Use it with undo disks and the sysetm gets trashed by an install it doesn't matter. Always start from the fresh OS image. Wednesday, June 4, PM. Hi Phil, I am observing a similar problem: my installer package deploys a Windows Forms application and a Windows Service.
So, I changed the RemovePreviousVesrions property of the Deployment Project to True hoping to allow the new version's installer to trigger automatic uninstall of the older version, but now I am getting this Error complaining that the service already exists. Here's an excerpt from the RemovePreviousVesrions property's documentation: If you have set both install and uninstall custom actions in an application's setup project, and you have enabled the RemovePreviousVersions property in Visual Studio , the previous version of the product is uninstalled during an upgrade.
However, this behavior changed in Visual Studio as follows: In Visual Studio , the custom actions were called as follows on an upgrade from v1. Thursday, June 12, PM. Phil, Thanks for your reply. I cannot and perhaps, do not want to restrict the users to what location they might select to install the app to. Is this service installation error happening when using the RemovePreviousVersions property simply a limitation of the Visual Studio's handling of the MSI generation or is this behavior of the Windows Installer itself?
In other words, can this upgrade process be implemented using some other more powerful MSI generator? Regards, Alex. Tuesday, June 17, PM. This means that the new version gets installed if we're installing to the same location on top of the older version, so: 1 File update rules are followed.
Phil, Thanks for the comprehensive explanation of the issue - it helps to see the bigger picture. In your point 4 you state that the old version's uninstall custom actions are still being executed, when upgrading with an MSI built in VS, but the RemovePreviousVersions documentation says that only the install custom action of the upgrade package will be executed. Have I missed something? Wednesday, June 18, AM. An upgrade is an install and also an uninstall of the old product, so yes, only the install custom actions run for the incoming new install, but the uninstall custom actions of the old product run as it is being uninstalled.
Wednesday, June 18, PM. If that's the case, it is not how one would read and understand the documentation of the RemovePreviousVesrions property: In Visual Studio , the custom actions were called as follows on an upgrade from v1. Anyway, moving on. What's even worse, when later trying to uninstall this failed-to-repair application it throws a "Null Reference" exception during the uninstall I am trapping, displaying and then swallowing all errors in my custom uninstall action , potentially aborting a half-completed uninstall.
Again, the Null Reference exception is only happening on unistall if I previously tried repairing the installation and it failed with Error  Friday, June 20, PM. Friday, June 27, PM. Monday, June 30, PM. This is ridiculous. I prefer the VS way of installs. Please give me the Uninstall back before the Install logic in VS  Tuesday, March 17, PM. I agree, changing how installers act using the RemovePreviousVersions was a mistake. In any case, I tried a work around where I attempt to remove the service on install first using this code in the beginning of my install method, but it does not seem to remove the old service.
This is required as the binary which runs the service may have changed, or the location of the installation may have changed. I almost understand why MS decided to change how setup projects work in , but at least give a work around, for instance, how about showing us some code which could be put into the Installer class which would uninstall previous versions the old way , or some code which would show us how to uninstall a service.
Monday, November 9, PM. It might be that reverting to the VS upgrade method will work better for some. This thread explains how, but it's a manual operation using Orca unless someone can automate a post-build step.
Tuesday, November 10, AM. Using Orca is really not a solution. Just simply a method to run uninstaller on previous versions via code in the installer of the setup created in would work fine.
Using Orca is a solution because it reverts to the VS upgrade mechanism and has the advantage that you don't need to write any code. Why is that not a solution? You're right, uninstalling the previous version during the install of the VS would work, but you can't do it. Install custom actions run too late, but yes you could add a custom action to uninstall the previous service but you'd have to arrange for it to run much earlier, so you're back to using Orca again.
Phil Wilson. Tuesday, November 10, PM. If you search this forum for WiRunSql you'll see some examples of post-build automation steps that people have used to update MSI files. Wednesday, November 11, PM.
Friday, May 28, PM. Okay, I'll bite I believe the only safe way to install and upgrade services with a Visual Studio setup project is to: 1. Microsoft does great unit testing but its integration testing stinks. Thanks again for this post. Friday, June 4, PM. Does anyone know if this situation improves in Visual Studio ? Thursday, August 12, AM.
Hi Phil, I am trying with those conditions but I still get the error. Wednesday, August 25, PM. Yeah, I'm in the same boat. A setup project should be simple to incorporate into any solution and work seamlessly without adverse impact. Workarounds are present, but there is so much disinformation to wade through, it takes forever and dead ends constantly kill.
Microsoft does a horrible job of documenting anything, and here this really shines through. Moderators that cannot deliver a specific solution that gets the programmer back to programming are common. Microsoft has no examples of how this should be done in each case effectively, probably because it can't be done.
Instead, we are led to believe it is our fault for not knowing every possible pattern and code api microsoft provides for us and that if we just try harder or get out big hammers to hack our way through, we will succeed. Try again moderators, and how about providing some good instructions on how to implement, like steps from beginning to end, or source so that the end user can determine if the solution is a fit or not right off the bat.
Better yet would be to create a microsoft document that can be posted up on MSDN for all to see quick and easily. I won't hold my breath, its been 15 years and nobody has listened yet Wednesday, May 4, PM. Monday, June 20, AM. And I'm sometimes still getting the old you must restart for changes to take effect even though I have code to explicitly restart my service after the installation is committed.
This is such a pain. Hi, Everything works fine except in case of repair. Can anyone help me in this regard? Thanks and Regards, Arun. Monday, July 4, PM. Installed is true when a repair is being run.