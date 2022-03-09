# Sela Bootcamp
## _Deployment Bootcamp project website on your Microsoft machine using IIS_

**Cloning Repo and Publish the project :(for personal use)**

 To deploy this project on IIS server please follow by the following intructions:

```sh
1. Open your desired directory where you want to clone the repo files.
2. Run git clone <repositoryURL>
3. Cd to the Bootcamp deirectory
4. Open some ide aplication > open file > load the project sulution.
5. Build the solution > Publish the project > wait for text "Publish succeeded" messge appears.
6. Click on Target Location which should reddirect you to the  project published files - > copy the publish files (We will use these files for the IIS, need to put them at the IIS website directory).

```


*******************************************************************************************************


**IIS server Installation :**


1. Connect via rdp to the windows server (Since download is not allowd).

2. Open the Server manager> Click on  Manage > Add Roles and Feature> select "Role-based or feature-base installation" > click on Next> Select your server, and click on next> 
   select the Web Server( iis). make sure applictaion development is checked too> click next and finish the instalation.

3. Open rdp connection from your pc to the windows remote server and copy the dotnet-runtime-6.0.2-win-x64.exe Installation file  -> Install it.

4. Open the IIS > Under sites > create a new website > Set a name >using port 5100, at the physical path  click on the three dots >carete a new directory for this site under C:\inetpub\wwwroot\<newDirectory>   > point to this directory.

5. During the website creation I created Application pool --> Save the website 

6. Right Click on your new site > click on browse and put the files we published in step 6 in the above section.

7. Stand On you site object >   Click on Browse:*:5100 link -> in case the website failed to be shown.

8. Copy from your PC copy the dotnet-runtime-6.0.2-win-x64.exe Installation file  and dotnet hosting-> Install it.

9. Stand On you site object >   Click on Browse:*:5100 link  - Greate now its working!





***********************************************************************************************

**Optional: Crating the Build and Publishing to Git**

In this project Iv'e performed the following steps:

1. Create a new “ASP.NET Core Web App” project Open visual studio> select New priject> select “ASP.NET Core Web App”
   Set  "Project name" and click on "next" button > select .NET 6.0 >click on "Create" button.

2. Build the project 
3. You should see bin. obj, Pages,Propertis,wwwroot folders, also appsettings.Development.json, appsettings.json, Bootcamp.csproj and Program.cs files.

   Right click on you project > select "open folder in file explorer"> Check your csproj content

   <Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net6.0</TargetFramework>
    <Nullable>enable</Nullable>
    <ImplicitUsings>enable</ImplicitUsings>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="13.0.1" />
  </ItemGroup>

</Project>


4. Inside the bin folder/Debug or Release(depends how you build your project)->  you should see all the binaries files.


   
5. **Add “Newtonsoft.Json” Package:**
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   Right click on you project >select "Manage NuGet Packages", Click on Browse tab > type "Newtonsoft" and click install > click "ok".
   Validate that under <yourProject>/dependencis/packages you can see the "Newtonsoft"package.

   

6. Rebuild the project and see that new dll for this package was added under bin folder.
   also added to the Bootcamp.csproj file. you will find a new ItemGroup is added 
   inside Bootcamp.csproj.

<ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="13.0.1" />
  </ItemGroup>

7. Add README.md file to your projects files.

8. **Publish the project:**
   ~~~~~~~~~~~~~~~~~~~~
   
   
   For Target > select the "Folder option > click on "next" > click on "Finish".
   "Ready to Publish" message should be displayed in blue.
   Click on the Publish button.
   Wait for :
   
   ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========

   ========== Publish: 1 succeeded, 0 failed, 0 skipped ==========

   Also Publish succeeded on <date> at <time> messge should be displayed in green.

   Click on the ink under "Target Location"

   Copy the files and directories (need to put them at the IIS website directory).
 

9. **Working with Git:**
   ~~~~~~~~~~~~~~~~~~~~~~~~
    On the right panel move to "Git changes" tab > Click on "create git repository" >set the Repository name> Uncheck the "private repository" checkbox.
    Use the built in integration to git and publish your project to a desired New repository.
    Click on "Create and Push" button 







