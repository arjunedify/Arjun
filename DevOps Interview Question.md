# DevOpsInterviewQuestion

1. WhatisSourceCodeManagement?

It is a process through which we can store and manage any code. Developerswrite code, Testers write test cases and DevOps engineers write scripts. Thiscode, we can store and manage in Source Code Management. Different teamscanstorecodesimultaneously. Itsavesall changesseparately.Wecanretrievethiscodeat anypoint oftime.

![Shape1](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhataretheAdvantagesofSourceCodeManagement?

.HelpsinAchievingteamwork

.Canworkondifferentfeaturessimultaneously

. Actslikepipelineb/w offshore&onshoreteams

.Trackchanges(Minutelevel)

.Differentpeoplefromthesameteam, aswellasdifferentteams, canstorecodesimultaneously(Saveallchangesseparately)

![Shape2](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. AvailableSourceCodeManagementtoolsinthemarket?

Therearesomany SourceCodeManagementtoolsavailableinthemarket.Thoseare

.Git

.SVN

.Perforce

.Clearcase

Out of all these tools, Git is the most advanced tool in the market where wearegettingso manyadvantagescomparedtootherSourceCodeManagementtools.

1. WhatisGit?

Git isoneoftheSourceCodeManagementtoolswherewecanstoreanytypeof code. Git is the most advanced tool in the market now. We also call Git isversion control system because every update stored as a new version. At anypoint of time, we can get any previous version. We can go back to previousversions. Every version will have a unique number. That number we callcommit-ID. By using this commit ID, we can track each change i.e. who didwhatatwhattime. Foreveryversion, ittakesincremental backupinsteadof

takingthewholebackup.That'swhy Gitoccupieslessspace. Sinceitisoccupyinglessspace,itisveryfast.

![Shape3](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whataretheadvantages ofGit?

# .Speed:-

Git stores every update in the form of versions. For every version, it takesincrementalbackupinsteadoftakingthewholebackup.Sinceitistakinglessspace,Git isveryfast.Thatincremental backupwecall"Snapshot"

# .Parallelbranching:-

We can create any number of branches as per our requirement. No need totakeprior permissionfromanyone,unlikeother SourceCodeManagementtools. Branching is for parallel development. Git branches allow us to worksimultaneouslyonmultiplefeatures.

# .FullyDistributed:-

A backup copy is available in multiple locations in each and everyone's serverinstead of keeping in one central location, unlike other Source CodeManagement tools. So even if we lose data from one server, we can recover iteasily. That'swhywecall GITasDVCS (DistributedVersionControlSystem)

![Shape4](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatarethestagesinGit?

Therearetotalof4stages inGit

1.
# Workspace:-

It is the place where we can create files physically and modify. Being a Git user,weworkinthisworkspace.

1.
# Stagingarea/Indexingarea:-

Inthisarea,Gittakesasnapshotfor everyversion.Itisa bufferzonebetweenworkspaceandlocalrepository.Wecan'tseethisregionbecauseit isvirtual.

1.
# Localrepository:-

It is the place where Git stores all commit locally. It is a hidden directory sothatnoonecandeleteitaccidentally.Every commitwillhaveuniquecommitID.

1.
# Central repository:-

It is the place where Git stores all commit centrally. It belongs to everyone whois working in your project. Git Hub is one of the central repositories. Used forstoringthecodeandsharingthecodetoothersintheteam.

1. WhatisthecommonbranchingstrategyinGit?

- Productisthesame,soonerepo.Butdifferentfeatures.
- Eachfeaturehasoneseparatebranch
- Finally,merge(code)allbranches
- ForParalleldevelopment
- Cancreateanynoofbranches
- Cancreateonebranchonthebasisofanotherbranch
- Changesarepersonaltothatparticularbranch
- Canputfilesonlyinbranches(notinrepodirectly)
- Thedefaultbranchis"Master"
- Files created in a workspace will be visible in any of the branchworkspacesuntilyoucommit. Onceyoucommit,thenthatfilebelongstothat particularbranch.

![Shape5](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Howmanytypes ofrepositoriesavailableinGit?

Therearetwotypesof repositoriesavailableinGit

# BareRepositories (Central)

Theserepositoriesareonlyfor Storing&SharingthecodeAll centralrepositoriesarebarerepositories

# Non –BareRepositories(Local)

Intheserepositories, wecanmodifythefiles

Alllocal/userrepositoriesareBareRepositories

![Shape6](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Canyouelaboratecommitin Git?

- Storingfilepermanently inthelocalrepositorywecallcommit.
- Foreverycommit,wegetonecommitID
- Itcontains40longAlpha-numericcharacters
- Itusestheconcept"Checksome"(It'sa toolinLinux,generatesbinaryvalueequaltothedatapresentinfile)
- Evenifyouchangeonedot,Commit-IDwillgetchanged
- Helpsintrackingthechanges

![Shape7](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatdoyoumeanby"Snapshot"inGit?

- Itisabackupcopyforeachversiongit storesinarepository.
- Snapshotisanincrementalbackupcopy(onlybackupfornewchanges)
- Snapshotrepresentssomedata ofparticulartimesothat,wecangetdata of particulartimebytakingthatparticularsnapshot
- This snapshot will be taken in Staging area in Git which is presentbetweenGitworkspaceandGitlocalrepository.

![Shape8](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisGitHub?

Git hub is central git repository where we can store code centrally. Git hubbelongs to Microsoft Company. We can create any number of repositories inGithub. Allpublicrepositoriesarefreeandcanbeaccessiblebyeveryone.

Privaterepositoriesarenotfreeandcanrestrictpublicaccessforsecurity.Wecan copy the repository from one account to other accounts also. This processwe call as "Fork". In this repository also we can create branches. The defaultbranchis"Master"

![Shape9](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisGit merge?

By default, we get one branch in git local repository called "Master". We cancreate any no of branches for parallel development. We write code for eachfeature in each branch so that development happens separately. Finally, wemerge code off all branches in to Master and push to central repository. Wecan merge code to any other branch as well. But merging code into master isstandard practice that being followed widely. Sometimes, while merging,conflict occurs. When same file is in different branches with different code,when try to merge those branches, conflict occurs. We need to resolve thatconflictmanuallybyrearrangingthecode.

![Shape10](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisGitstash?

Wecreatemultiplebranchestoworksimultaneouslyonmultiplefeatures.Butto work on multiple tasks simultaneously in one branch (i.e. on one feature),we use git stash. Stash is a temporary repository where we can store ourcontent and bring it back whenever we want to continue with our work withthat stored content. It removes content inside file from working directory andputs in stashing store and gives clean working directory so that we can startnew workfreshly. Lateronyoucanbringbackthatstasheditemstoworking

directory and can resume your work on that file. Git stash applicable tomodifiedfiles. Notnewfiles. Oncewefinishourwork,wecanremoveallstasheditemsform stashrepository.

![Shape11](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisGitReset?

Git Reset command is used to remove changes form staging area. This isbringing back file form staging area to work directory. We use this commandbefore commit. Often we go with git add accidentally. In this case if wecommit, that file will be committed. Once you commit, commit ID will begeneratedanditwillbeintheknowledgeofeveryone.Sotoavoidthisone, weuseGitreset.

If you add "–hard" flag to git reset command, in one go, file will be removedfromstagingareaaswellasworkingdirectory.Wegenerallygowiththisoneifwefellthat somethingwronginthefileitself.

![Shape12](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatis GitRevert?

Git Revert command is used to remove changes from all 3 stages (workdirectory, staging area and local repository). We use this command aftercommit.Sometimes, wecommitaccidentallyandlater onwerealizethatweshouldn't have done that. For this we use Git revert. This operation willgenerate new commit ID with some meaningful message to ignore previouscommit where mistake is there. But, here we can't completely eliminate thecommitwheremistakeisthere. BecauseGittrackseachandeverychange.

![Shape13](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. DifferencebetweenGitpullandGitclone?

We use these two commands to get changes from central repository. For thefirst time if you want whole central repository in your local server, we use gitclone. It brings entire repository to your local server. Next time onwards youmight want only changes instead of whole repository. In this case, we use Gitpull.

Gitcloneistogetwholecopyofcentral repository

Gitpullistogetonlynewchangesfromcentralrepository(Incrementaldata)

![Shape14](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisthedifferencebetweenGitpullandFetch?

We use Git pull command to get changes from central repository. In thisoperation,internallytwo commandswillgetexecuted.OneisGitfetchandanotheroneisGitmerge.

Git fetch means, only bringing changes from central repo to local repo. Butthese changes will not be integrated to local repo which is there in your server.Git merge means, merging changes to your local repository which is there inyourserver.Thenonlyyoucanseethesechanges.

SoGitpullisthecombinationof Git pullandGitmerge.

![Shape15](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisthedifferencebetweenGitmergeandrebase?

We often use these commands to merge code in multiple branches. Both arealmost same but few differences. When you run Git merge, one new mergecommit will be generated which is having the history of both developmentbranches. It preserves the history of both branches. By seeing this mergecommit, everyone will come to know that we merged two branches. If you doGit rebase, commits in new branch will be applied on top of base branch tip.There won't be any merge commit here. It appears that you started working inone single branch form the beginning. This operation will not preserves thehistoryofnewbranch.

![Shape16](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisGitBisect?

Git Bisect we use to pick bad commit out of all good commits. Oftendevelopers do some mistakes. For them it is very difficult to pick that commitwhere mistake is there. They go with building all commits one by one to pickbadcommit. ButGitbisectmadetheirliveseasy. Gitbisectdividesallcommitsequally in to two parts (bisecting equally). Now instead of building eachcommit, they go with building both parts. Where ever bad commit is there,that part build will be failed. We do operation many times till we get badcommit. SoGit bisectallowsyoutofindabadcommitoutofgoodcommits.

You don't have to trace down the bad commit by hand; git-bisect will do thatforyou.

![Shape17](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisGitsquash?

Tomovemultiplecommitsintoitsparentsothatyouendupwithonecommit.If you repeat this process multiple times, you can reduce "n" number ofcommitstoasingleone. Finallywewillendupwithonlyoneparentcommit.

Weusethisoperationjustto reducenumberofcommits.

![Shape18](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisGit hooks?

Weoftencall thisaswebhooksaswell. Bydefault wegetsomeconfigurationfiles when you install git. These files we use to set some permissions andnotification purpose. We have different types of hooks (pre commit hooks &postcommithooks)

Pre-commit hooks:- Sometimes you would want every member in your team tofollow certain pattern while giving commit message. Then only it should allowthemtocommit.Thesetypeofrestrictionswecallpre-commit hooks.

Post-commit hooks:- Sometimes, being a manager you would want an emailnotification regarding every commit occurs in a central repository. This kind ofthingswecallpost-commithooks.

Insimpleterms,hooksarenothingbutscriptsto putsomerestrictions.

![Shape19](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisGit cherry-pick?

When you go with git merge, all commits which are there in new developmentbranch will be merged into current branch where you are. But sometimes,requirement will be in such that you would want to get only one commit formdevelopment branch instead of merging all commits. In this case we go with gitcherry-pick. Git cherry-pick will pick only one commit whatever you select andmerges with commits which are there in your current branch. So pickingparticular commitandmerginginto your currentbranchwecallgitcherry-pick.

![Shape20](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisthedifferencebetweenGitandSVN?

# SVN:-

Itiscentralizedversioncontrolsystem(CVCS)whereback upcopy willbeplacedinonlyonecentralrepository.

There is no branching strategy in SVN. You can't create branches. So no paralleldevelopment.

There is no local repository. So can't save anything locally. Every time afterwritingcodeyouneedto pushthatcodeto centralrepository immediatelytosavechanges.

# Git:-

It is a Distributed version control system where back up copy is available ineveryone'smachine'slocal repositoryaswell asacentral repository.

Wecancreateanynoofbranchesaswewant.Sowecangoinparalleldevelopmentsimultaneously.

Every Git repository will have its own local repository. So we can save changeslocally.Attheendofourworkfinally, wecanpushcodetoa centralrepository.

![Shape21](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatisthecommit messageinGit?

Every time we commit, while committing, we have to give commit messagejusttoidentifyeachcommit.Wecan'tremembertocommitnumbersbecausethey contain 40 long alphanumeric characters. So, to remember commitseasily, we give commit message. The format of commit message differs fromcompanytocompanyandindividualtoindividual.

Wehaveonemoreway toidentify commits.Thatisgiving"Tags".Tagisa kindof meaningful name to a particular commit. Instead of referring to commit ID,wecanrefertotags.Internallytagwillrefertorespectivecommit ID.

Thesearethewaystogetaparticularcommiteasily.

![Shape22](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisConfigurationManagement?

It is a method through we automate admin tasks. Each and every minutedetails of a system, we call configuration details. If we do any change heremeans we are changing the configuration of a machine. That means we aremanaging the configuration of the machine. System administrators used tomanagetheconfigurationofmachinethroughmanually.DevOpsengineersaremanagingthisconfigurationthroughautomatedwaybyusingsometools

which are available in the market. That's why we call these tools asconfigurationmanagement tools.

![Shape23](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisIAC?

IAC means Infrastructure As Code. It is the process through which weautomate all admin tasks. Here we write code in Ruby script in chef. When youapply this code, automatically code will be converted into Infrastructure. Soherewearegettingsomanyadvantagesinwritingthecode.Thoseare

1. CodeisTestable(Testingcodeiseasy comparetoInfrastructure)
2. CodeisRepeatable(Canre-usethesamecodeagainandagain)
3. CodeisVersionable(Canstoreinversionssothatcangetanypreviousversionsat anytime)

![Shape24](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatdoyoumeanbyITInfrastructure??

ITInfrastructureisacompositeofthefollowingthings

- Software
- Network
- People
- Process

![Shape25](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whataretheproblemsthatsystemadminsusedto faceearlierwhentherewerenoconfigurationmanagementtools?

1. Managingusers& Groupsisbighecticthing(createusersandgroups,delete,edit……)
2. Dealingwithpackages(Installing,Upgrading&Uninstalling)
3. Takingbackupsonregularbasismanually
4. Deployingallkindsof applicationsinservers
5. Configureservices(Starting,stoppingandrestartingservices)

These are some problems that system administrators used to face earlier intheirmanual processof managingconfigurationofanymachine.

![Shape26](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

30.WhyshouldwegowithConfigurationManagementTool?

1. By usingtheConfigurationManagementTool, wecanautomatealmosteachandeveryadmintask.
2. Wecanincreaseuptimesothatcanprovidemaximumusersatisfaction.
3. Improvetheperformanceofsystems.
4. Ensurecompliance
5. Preventerrorsastoolswon'tdoanyerrors
6. Reducecost(Buy toolonceanduse24/7)

![Shape27](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. HowthisConfigurationManagementToolworks?

Whatever system admins (Linux/windows) used to do manually, now we areautomating all those tasks by using any Configuration Management Tool. Wecan use this tool whether your servers are in on-premises or in the cloud. Itturns your code into infrastructure. So your code is versionable, repeatableand testable. You only need to tell what the desired configuration should be,not how to achieve it. Through automation, we get our desired state of server.ThisisuniquefeatureofConfigurationManagementTool.

![Shape28](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisthearchitectureofChef?

Chefisanadministrationtool. Inthiswehavetotal3stages.

1. ChefWorkstation(Itistheplacewherewewritecode)
2. ChefServer(Itistheplacewherewestorecode)
3. ChefNode(Itistheplacewhereweapplycode)

Weneedto establishcommunicationamongworkstation,serverandnodes.You can have any no of nodes. There is no limit. Chef can manage any no ofnodeseffectively.

![Shape29](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. ComponentsofChef?

**Chef Workstation:** Where you write the code **Chef Server:** Where you upload the code **Chef**** Node:**Whereyouapplythecode

**Knife:** Toolto establishcommunicationamongworkstation,server&node. **Chef-client:** Tool runs on every chef node to pull code from chef server **Ohai:** Maintainscurrentstateinformationof chefnode(SystemDiscovery

Tool)

**Idempotency:** Trackingthestateofsystemresourcesto ensurethatthechangesshouldnotre-applyrepeatedly.

**Chef**** Supermarket:**Whereyougetcustomcode

![Shape30](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. HowdoesChefWorks?

We need to install chef package in workstation, server and nodes. We createcookbookinworkstation.Insidecookbook,therewillbeadefaultrecipewhereyou write code in ruby script. You can create any no of recipes. There is nolimit. Afterwritingcodeinrecipe,weuploadwholecookbooktochef server.

Chef server acts as central hub storing code. Then, we need to add thiscookbook's recipe to nodes run-list. Chef-client tool will be there in each andevery chef node. It runs frequently. Chef-client comes to chef server and takethat code and applies that code in node. This is how code will be convertedintoinfrastructure.

![Shape31](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisIdempotency?

It is unique feature in all configuration management tools. It ensures thatchangesshould notre-applyrepeatedly. Oncechef-clientconvertedcodeintoInfrastructure, then even chef-client runs again, it will not take any action. Itwon't do the same task again and again. If any new changes are there in thatcode, then only chef-client is going to take action. So it doesn't make anydifference ever if you run chef-client any no of times. So tracking the systemdetailstonottoreapplychangesagainandagain, wecallIdempotency.

![Shape32](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisOhaiandhowdoesitworks??

Ohai we call "System Discovery Tool". It stores system information. It captureseach and every minute details of system and updates it then and there if anynewchangesarethere. Whenever chef-clientconvertscodeininfrastructureinnode, immediatelyOhaistorewill beupdated. Next timeonwards, before

chef-client runs, it verifies in Ohai store to know about current state ofinformation.Sochef-clientwillcometoknowthecurrentstateofserver.Thenchef-client acts accordingly. If new changes are there, then only it will takeaction. If there are no new changes, then it won't take any action. Ohai toolhelpsinachievingthis.

![Shape33](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Howmanytypesofchefserver?

Total thereare3waysthroughwhichwecanmanagechef server.

1. Directly we can take chef server from Chef Company itself. In this case,everything will be managed by Chef Company. You will get support from chef.ThistypeofserverwecallManaged/Hostedchef.ThisiscompletelyGraphicalUser Interface (GUI). It's not free. We need to pay to Chef Company afterexceedingfree tierlimit.
2. Wecanlaunchoneserver andweneedtoinstallchefserverpackage.Itiscompletelyfreepackage.It'sGUI.
3. Wecanlaunchoneserver andweneedtoinstallchefserverpackage.Itiscompletelyfreepackage.It'sCLI(CommandLineInterface).

![Shape34](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatisthereinsidecookbook??

Below mentionedfilesandfolderswillbethereinsidecookbookwhenyoufirstcreateit

**Chefignore:** like.gitignore(toignorefilesandfolders)

**Kitchen.yml:** fortestingofcookbook

**Metadata.rb:** name, author, version…. etc of cookbook **Readme.md:** information about usage of cookbook **Recipe:** It isafilewhereyouwritecode

**Spec:** forunittest

**Test:** forintegrationtest

![Shape35](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisAttributesconceptinchef?

Sometimes we might need to deploy web applications to in nodes and for thatweneedtoknow somehostspecificdetailsofeachserverlikeIPAddress,Hostname ….. etc. Because we need to mention that in configuration files of eachserver. These files we call as Configuration files. This information will be varyfrom system to system. These host specific details that we mention inConfiguration files,we call "Attributes". Chef-client tool gathers theseAttributes from Ohai store and puts in configuration files. Instead of hardcoding these attributes, we mention as variables so that every time, file will beupdatedwithlatestdetails of theirrespectivenodes.

![Shape36](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisRun-listinChef?

This is an ordered list of recipes that we are going to apply to nodes. Wemention all recipes in cookbook and then we upload that cookbook to chefserver. Then, we attach all recipes to nodes run-list in sequence order. Whenchef-client runs, it applies all recipes to nodes in the same order whatever theorder you mention in run-list. Because sometimes order is important especiallywhenwedealwithdependent recipes.

![Shape37](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatisbootstrap?

It is the process of adding chef node to chef server or we can call, bringing anymachine into chef environment. In this bootstrapping process total threeactionwillbeperformedautomatically.

1. Nodegetsconnectedto chefserver.
2. Chefserverwillinstallchefpackageinchefnode.
3. Cookbookswillbeappliedtochefnode.

It is only one time effort. As and when we purchase any new machine incompany,immediately weaddthatserver tochefserver.Ata time, wecanbootstraponemachine.Wecan'tbootstrapmultiplemachinesatatime.

![Shape38](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatis theworkflowofChef?

We connect chef workstation, chef server and chef node with each other. Afterthat, we create cookbook in chef workstation and inside that cookbook, wewrite code in recipe w.r.t. the infrastructure to be created. Then we uploadentire cookbook to chef server and attach that cookbook's recipe to nodes run-list. Now we automate chef-client which will be there in all chef nodes. Chef-client runs frequently towards chef server for new code. So chef-client will getthat code from server and finally applies to chef node. This is how, code isconvertedintoinfrastructure. If nochangesarethereincode,evenif chef-

clientrunsany nooftime, itwon'ttakeanyactionuntilitfindssomechangesincode.Thisiswhat wecall Idempotency.

![Shape39](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. HowdoesweconnectChef WorkstationtoChef Server?

First we download started kit from chef server. This will be downloaded in theformofzipfile.Ifweextractthiszipfile, wewill getchef-repofolder. Thischef-repo folder we need to place in chef workstation. Inside chef-repo folder, wecan see total three folders. They are .chef, cookbooks and roles. Out of thesethree, .chef folder is responsible to establish communication between chefserver and chef workstation. Because, inside .chef folder, we can see two files.They are knife.rb and organization.pem. Inside kinfe.rb, there will be the url(address) of chef server. Because of this url, communication will be establishedbetween chef server and chef workstation. This is how we connect ChefWorkstationtoChefServer.

![Shape40](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Howdoesthechef-clientrunsautomatically?

By default, chef-client runs manually. So we need to automate this manually.For this, we use "cron tool" which is the default tool in all Linux machines useto schedule tasks to be executed automatically at frequent intervals. So in this"crontab" file, we give chef-client command and we need to set the timing asper our requirement. Then onwards chef-client runs automatically after everyfrequent intervals. It is only one time effort. When we purchase any newserver in company, along with bootstrap, we automate chef-client then andthere.

![Shape41](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatischefsupermarket?

Chef supermarket is the place where we get custom cookbooks. Every time weneed not to create cookbooks and need not to write code from scratch. Wecan go with custom cookbooks which are available in chef supermarket beingprovided by chef organization and community. We can download thesecookbooks and modify as per our needs. We get almost each and everycookbookfromchef supermarket.Theyaresafetouse.

![Shape42](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatiswrappercookbook?

Either we can download those chef supermarket cookbooks or withoutdownloading, we can call these supermarket cookbooks during run time sothat every time we get updates automatically for that cookbook if any newupdates are there. Here, we use our own cookbook to call chef supermarketcookbook. This process of calling cookbook by using another cookbook, we callwrappercookbook.Especially,weusethisconcepttoautomatechef-client.

![Shape43](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatis"roles"inchef?

RolesarenothingbutaCustomrun-list. Wecreaterole&uploadtochef server& assign them to nodes. If we have so many nodes, need to add cookbook torun-list of all those nodes, it is very difficult to attach to all nodes run-list. So,we create role & attach that role to all those nodes once. Next time onwards,add cookbook to that role. Automatically, that cookbook will be attached to allthose nodes. So role is one time effort. Instead of adding cookbooks to each &everynode'srun-listalways,justcreatearole&attachthatroletonodes.

Whenweaddcookbook tothatrole,itwillbeautomaticallyappliedto allnodesthoseassignedwiththat role.

![Shape44](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatisinclude\_recipeinchef?

Bydefault,wecancallonerecipeatatimeinonecookbook. Butif youwanttocallmultiplerecipesfromsamecookbook, weuseinclude\_recipeconcept.

Here, we take default recipe and we mention all recipes to be called in thisdefaultrecipeinanorder.Ifwecalldefaultrecipe,automaticallydefaultrecipewill call all other recipes which are there inside default recipe. By using onerecipe, we can call any no of recipes. This process of calling one recipe by usingother recipe, we call as include\_recipe. Here condition is we can call recipesfromsamecookbook,butnot fromdifferent cookbooks.

![Shape45](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Howtodeployawebserverby usingchef?

package'httpd'doaction:install

end

file '/var/www/html/index.html' docontent 'Hello Dear Students!!'action:create

end

service 'httpd' doaction[:enable,:start]end

![Shape46](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Howtowriterubycodetocreatefile,directory?

file'/myfile'do

content'Thisismysecondfile'action:create

owner 'root'group 'root'end

directory '/mydir' doaction:create

owner 'root'group 'root'end

![Shape47](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Howtowriteruby codetocreateuser, groupandinstallpackage?

user'user1'doaction: createend

group 'group1' doaction :createmembers 'user1'appendtrue

end

package'httpd'doaction:install

end

![Shape48](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatiscontainer?

The container is like a virtual machine in which we can deploy any type ofapplications, soft wares and libraries. It's a light weight virtual machine whichusesOSintheformofimage,whichishavinglessinsizecomparetotraditionalVMwareandoraclevirtualboxOSimages.Containerwordhas beentakenfromshippingcontainers.Ithaseverythingtorunanapplication.

![Shape49](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatisvirtualization?

Logically dividing big machine into multiple virtual machines so that eachvirtualmachineactsasnewserver andwecandeploy any kindofapplicationsin it. For this first we install any virtualization software on top of base OS. Thisvirtualization software will divide base machine resources in to logicalcomponents. In a simple terms, logically dividing one machine into multiplemachineswecallvirtualization.

![Shape50](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisDocker?

Docker is a tool by using which, we create containers in less time. Docker useslightweightOSintheformofdocker imagesthatwewillgetfromdocker hub.

Dockerisopensourcenow.Itbecamesopopular becauseofitsunique

virtualizationconceptcalled"Containerization"whichisnotthereinothertools.WecanusedockerinbothwindowsandLinuxmachines.

![Shape51](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatdo youmeanbydocker image?

Docker image is light weight OS provided by docker company. We can get anytype of docker image form docker hub. We use these docker images to createdocker containers. This docker images may contain only OS or OS + other softwares as well. Each software in docker image, will be stored in the form oflayer. Advantage of using docker images is, we can replicate the sameenvironmentanynooftimes.

![Shape52](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatarethewaysthroughwhichwecancreatedockerimages?

Therearethreewaysthroughwhichwecancreatedockerimages.

1. Wecantakeanytypeofdockerimagedirectlyfromdockerhubbeingprovidedbydockercompanyanddockercommunity.
2. Wecancreateourowndockerimagesformourowndockercontainers.I.e.first we create container form base docker image taken form docker hub andthen by going inside container, we install all required soft wares and thencreatedockerimagefromourowndockercontainer.
3. Wecancreatedockerimageformdocker file.Itisthemostpreferredwayofcreatingdockerimages.

![Shape53](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatisdockerfileandwhydoweuseit?

It is a just normal text file with instructions in it to build docker image. It is theautomated way of creating docker images. Once you build docker image,automatically docker file will be created. In this file, we mention required OSimage and all required soft wares in the form of instructions. Once we builddocker file, back end, docker container will be created and then docker imagewill be crated from that container and that container will be destroyedautomatically.

![Shape54](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. DifferencebetweendockerandVMWare?

VMWareusescompleteOSwhichcontainsGBsinsize. Butdocker imagesizeis MBs only. So it takes less size. That's why it takes less base machineresources. This docker image is compressed version of OS. The secondadvantage of docker is, there is no pre-allocation of RAM. During run time, ittakes RAM as pre requirement from base machine and one's job is done, itreleaseRAM.ButinVMWare,pre-allocationof RAMisthereandit blocked

whether it uses or not. So need more RAM for base machine if you want to useVMWareunlikeDocker.

![Shape55](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisOS-LeverVirtualization?

It is the unique feature of Docker which is not available in other virtualizationsoft wares. Docker takes most of UNIX features form host machine OS and itonly takes extra layers of required OS in the form of docker image. So dockerimage contains only extra layers of required OS. For core UNIX kernel, itdepends upon host OS, why because UNIX kernel is same in any of the UNIXandLinuxflavors. Inasimpleterms, dockertakeshostOSvirtually. That'swhywecallthisconceptasOS-LeverVirtualization.

![Shape56](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisLayeredfilesystem/Unionfilesystem?

Inside docker container, wheat ever we do, that forms as a new layer. Forinstance, creating files, directories, installing packages etc. This is what we callas layered file system. Each layer takes less space. We can create docker imageform this container. In that docker image also we get all these layers and formsunity. That's why we also call Union File System. If we create container out ofdocker image, you can able to see all those files, directories and packages. Thisiswhat replicationofsameenvironment.

![Shape57](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatarethebenefitsof Docker?

- Containerization(OSlevelvirtualization)(NoneedguestOS)
- Nopre-allocationofRAM
- Canreplicatesameenvironment
- Lesscost
- Lessweight(MB'sinsize)
- Fasttofireup
- Canrunonphysical/virtual/cloud
- Canre-use(sameimage)
- Cancreatecontainersinlesstime

![Shape58](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. ListofDockercomponents?

**Docker image: –** Contains OS (very small) (almost negligible) + soft wares **Docker Container: –** Container like a machine which is created from Dockerimage.

**Docker file: –** Describes steps to create a docker image. **Docker**** hub/registry: ****–** Storesalldockerimagespublicly. **Docker daemon: –** Docker service runs at back endAbovefivecomponentswecallasDockercomponents

![Shape59](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisDockerworkflow?

First we create Docker file by mentioning instructions to build docker image.FormthisDockerimage, wearegoingtocreateDockercontainer. ThisDockerimage we can push to docker hub as well. This image can be pulled by othersto create docker containers. We can create docker images from dockercontainers. Like this we can create Docker images form either docker file ordocker containers. We can create docker containers from docker images. Thisistheworkflowofdocker.

![Shape60](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. SampleDockerfileinstructions?

FROM ubuntuWORKDIR/tmp

RUNecho"Hello"\>/tmp/testfileENVmynameuser1

COPY testfile1 /tmpADD test.tar.gz/tmp

![Shape61](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatistheimportanceof volumesinDocker?

- Volumeisa directory insideyour container
- Firstdeclaredirectoryasavolumeandthensharevolume
- Evenif westopcontainer,still wecanaccessvolume
- Volumewill becreatedinonecontainer
- Youcanshareonevolumeacrossanynoofcontainers
- Volumewill notbeincludedwhenyouupdateanimage
- Mapvolumesintwoways
- Sharehost–container
- Sharecontainer–container

![Shape62](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatdoyoumeanbyportmappinginDocker?

Suppose if you want to make any container as web server by installing webpackage in it, you need to provide containers IP address to public in order toaccess website which is running inside docker container. But Docker containersdon'thaveanIPaddress. So,toaddressthisissue, wehaveaconceptcalled

Docker port mapping. We map host port with container port and customersuse public IP of host machine. Then their request will be routed from host portto container's port and will be loaded web page which is running inside dockercontainer. This is how we can access website which is running inside containerthroughport mapping.

![Shape63](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisRegistry server inDocker?

Registry server is our own docker hub created to store private docker imagesinstead of storing in public Docker hub. Registry server is one of the dockercontainers. We create this Registry server from "registry" image, especiallyprovided by docker to create private docker hub. We can store any no ofprivate docker images in this Registry server. We can give access to others, sothat, they also can store their docker images whomever you provide access.Whenever wewant,wecanpulltheseimagesandcancreatecontainersoutoftheseimages.

![Shape64](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Importantdockercommands?

1. Dockerps(to seelistofrunningcontainers)
2. Dockerps-a(toseelistof allcontainers)
3. Dockerimages(toseelistofall images)
4. Dockerrun(to createdockercontainer)

4.Dockerattach(togoinsidecontainer)

1. Dockerstop(tostopcontainer)
2. Dockerstart(tostartcontainer)
3. Docker commit(tocreateimageoutofdocker file)
4. Dockerrm(to deletecontainer)
5. Dockerrmi(todeleteimage)

![Shape65](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisAnsible?

Ansible is one of the configuration Management Tools. It is a method throughwe automate system admin tasks. Configuration refers to each and everyminute details of a system. If we do any changes in system means we arechanging the configuration of a machine. That means we are changing theconfiguration of the machine. All windows/Linux system administratorsmanage the configuration of a machine manually. All DevOps engineers aremanaging this configuration automatic way by using some tools which areavailableinthemarket. Onesuchtool isAnsible.That'swhywecall Ansibleasconfigurationmanagement tool.

![Shape66](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WorkingprocessofAnsible?

HerewecratefilecalledplaybookandinsideplaybookwewritescriptinYAMLformat to create infrastructure. Once we execute this playbook, automaticallycode will be converted into Infrastructure. We call this process as IAC(Infrastructure as Code). We have open source and enterprise editions ofAnsible.Enterpriseeditionwecall AnsibleTower.

![Shape67](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. ThearchitectureofAnsible?

We create Ansible server by installing Ansible package in it. Python is pre-requisite to install ansible. We need not to install ansible package in nodes.Because,communicationestablishesfromservertonodethrough"ssh"client.By default all Linux machine will have "ssh" client. Server is going to push thecode to nodes that we write in playbooks. So Ansible follows pushingmechanism.

![Shape68](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Ansiblecomponents?

**Server:**** –**ItistheplacewherewecreateplaybooksandwritecodeinYMLformat

**Node:**** –**Itistheplacewhereweapplycodetocreateinfrastructure. Serverpushescodetonodes.

**Ssh: –** It is an agent through ansible server pushes code to nodes. **Setup:**** – **Itisamoduleinansiblewhichgathersnodesinformation.** Inventory ****file:-** InthisfilewekeepIP/DNSofnodes.

![Shape69](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. DisadvantagesinotherSCM(SourceCodeManagement)tools?

- HugeoverheadofInfrastructuresetup
- Complicatedsetup
- Pullmechanism
- Lotoflearningrequired

![Shape70](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. AdvantagesofAnsibleoverother SCM(SourceCodeManagement)tools?

- Agentless
- Relieson"ssh"
- Usespython
- Pushmechanism

![Shape71](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. HowdoesAnsiblework?

We give nodes IP addresses in hosts file by creating any group in ansible serverwhy because, ansible doesn't recognize individual IP addresses of nodes. Wecreate playbook and write code in YAML script. The group name we have tomention in a playbook and then we execute the playbook. By default, playbookwill be executed in all those nodes which are under this group. This is howansibleconvertscodeintoinfrastructure.

![Shape72](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatdoyoumeanby Ad-HoccommandsinAnsible?

These are simple one liner Linux commands we use to meet temporaryrequirementswithoutactually savingforlater.Herewedon'tuseansible

modules. So there, Idempotency will not work with Ad-Hoc commands. If at allwe don't get required YAML module to write to create infrastructure, then wego for it. Without using playbooks we can use these Ad-Hoc commands fortemporarypurpose.

![Shape73](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. DifferencesbetweenChefandAnsible?

- Ansiblechef
- Playbook –Recipe
- Module–Resource
- Host–Node
- Setup–Ohai
- Ssh–Knife
- Push-Pull

![Shape74](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisPlaybookinAnsible?

Playbook isafilewherewewriteYAMLscripttocreateinfrastructureinnodes.Here, we use modules to create infrastructure. We create so many sections inplaybook. We mention all modules in task section. You can create any no ofplaybooks. There is no limit. Each playbook defines one scenario. All sectionsbeginwith"-"&itsattributes&parametersbeneathit.

![Shape75](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. MentionsomelistofsectionsthatwementioninPlaybook?

1. Targetsection
2. Task section
3. Variablesection
4. Handlersection

![Shape76](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisTargetsectioninAnsibleplaybook?

This is one of the important sections in Playbook. In this section, we mentionthe group name which contains either IP addresses or Hostnames of nodes.When we execute playbook, then code will be pushed too all nodes which arethereinthegroupthatwementioninTargetsection. Weuse"all"keywordtoreferallgroups.

![Shape77](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisTasksectioninAnsibleplaybook?

This is second most important section in playbook after target section. In thissection, we are going to mention list of all modules. All tasks we mention inthis task section. We can mention any no of modules in one playbook. There isno limit. If there is only one task, then instead of going with big playbook,simply we can go with arbitrary command where we can use one module at atime. If more than one module, then there is no option except going with bigplaybook.

![Shape78](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisVariablesection?

Inthissectionwearegoingtomentionvariables. Insteadofhardcoding, wecanmentionasvariablessothatduringruntimeit pullstheactual valuein

placeofkey.Wehavethisconceptineachandevery programminglanguageandscriptinglanguage.Weuse"vars"keywordtousevariables.

![Shape79](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisHandlersection?

All tasks we mention in tasks section. But some tasks where dependency isthere, we should not mention in tasks section. That is not good practice. Forexample, installing package is one task and starting service is one more task.Butthereisdependency betweenthem.I.e.after installingpackageonly, wehave to start service. Otherwise it throws error. These kind of tasks, wemention in handler section. In above example, package task we mention intask section and service task we mention in handler section so that afterinstallingtaskonlyservicewillbestarted.

![Shape80](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisDryruninplaybook?

Dry run is to test playbook. Before executing playbook in nodes, we can testwhether the code in playbook is written properly or not. Dry run won't actuallyexecutes playbook, but it shows output as if it executed playbook. Then byseeing the output, we can come to know whether the playbook is writtenproperly or not. It checks whether the playbook is formatted correctly or not. Ittestshowtheplaybookisgoingtobehavewithoutrunningthetasks.

![Shape81](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhyareweusingloopsconceptinAnsible?

Sometimes we might need to deal with multiple tasks. For instance, Installingmultiple packages, Creating many users, creation many groups..etc. In thiscase,mentioningmoduleforeverytaskiscomplexprocess.So,to addressthisissue, we have a concept of loops. We have to use variables in combinationwithloops.

![Shape82](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WheredoweuseconditionalsinPlaybooks?

Sometimes, your nodes could be mixture of different flavors of Linux OS. Linuxcommands vary in different Linux operating systems. In this case, we can'texecute common set of commands in all machines, at the same time, we can'texecutedifferentcommandsineachnodeseparately.Toaddressthisissue,wehave conditionals concept where commands will be executed based up oncertainconditionthat wegive.

![Shape83](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisAnsiblevault?

Sometimes, weusesensitiveinformationinplaybookslikepasswords,keys

…etc. So any one can open these playbooks and get to know about thissensitiveinformation. Sowehavetoprotectour playbooksfrombeingreadbyothers. So by using Ansible vault, we encrypt playbooks so that, those whoever is having password, only those can read this information. It is the way ofprotectingplaybooksbyencryptingthem.

![Shape84](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatdoyoumeanby RolesinAnsible?

Adding more & more functionality to the playbooks will make it difficult tomaintain in a single file. To address this issue, we organize playbooks into adirectory structurecalled"roles". Wecreateseparatefileto eachsectionandwejust mentionthenamesofthosesectionsinplaybookinsteadof

mentioning all modules in main playbook. When you call main playbook, mainplaybook will call all sections files respectively in the order whatever order youmention in playbook. So, by using this Roles, we can maintain small playbookwithoutanycomplexity.

![Shape85](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Writeasampleplaybookto installanypackage?

- #MyFirstYAMLplaybook

- hosts: demouser: ansiblebecome: yesconnection: sshtasks:
- name: Install HTTPD on centos 7action:yumname=httpdstate=installed

![Shape86](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Writea sampleplaybookbymentioningvariablesinsteadofhardcoding?

- #MyFirstYAMLplaybook

- hosts: demouser: ansiblebecome: yesconnection: sshvars:

pkgname: httpdtasks:

- name:InstallHTTPDserver oncentos7

action:yumname='{{pkgname}}'state=installed

![Shape87](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatis CI&CD?

CI means Continues Integration and CD means Continues Delivery/Deploy.Wheneverdeveloperswritecode,weintegrateallthatcodeofalldevelopersat that point of time and we build, test and deliver/deploy to the client. Thisprocess we call CI & CD. Jenkins helps in achieving this. So instead of doingnightbuilds, buildasandwhencommitoccursbyintegratingallcodeinSCM

tool,build, testandcheckingthequalityofthatcodeiswhatwecallContinuesIntegration.

![Shape88](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. KeyterminologythatweuseinJenkins?

**Integrate:** Combineallcodewrittenbydeveloperstill somepointof time.

**Build:** Compilethecodeandmakeasmallexecutablepackage.

**Test:** Test in all environments whether application is working properly or not. **Archived:** Stored in an artifactory so that in future we may use/deliver again. **Deliver:** HandingtheproducttoClient

**Deploy:** Installingproductinclient'smachines.

![Shape89](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisJenkinsWorkflow?

We attach Git, Maven, Selenium & Artifactory plug-ins to Jenkins. OnceDevelopers put the code in Git, Jenkins pulls that code and send to Maven forbuild. Oncebuildisdone, Jenkinspullsthatbuiltcodeandsendtoseleniumfortesting. Once testing is done, then Jenkins will pull that code and send toArtifactory as per requirement and finally we can deliver the end product toclient we call Continues delivery. We can also deploy with Jenkins into clientsmachinedirectlyaspertherequirement.ThisiswhatJenkinsworkflow.

![Shape90](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatarethewaysthroughwhichwecandoContinuesIntegration?

aretotal threewaysthroughwhichwecandoContinuesIntegration

1. **Manually:**** –**Manuallywritecode,thendobuildmanually andthentestmanuallybywritingtestcasesanddeploymanuallyintoclientsmachine.
2. **Scripts: –** Candoaboveprocessby writingscriptsso thatthesescriptsdoCI&CDautomatically. Butherecomplexityis, writingscriptisnotsoeasy.
3. **Tool:**** –**UsingtoolslikeJenkinsisvery handy.Everythingispreconfiguredinthese type of tools. So less manual intervention. This is the most preferredway.

![Shape91](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

95.Benefits ofCI?

1. Detectsbugsassoonaspossible,sothatbugwillberectifiedfastanddevelopmenthappensfast.
2. Completeautomation.Noneedmanualintervention.
3. Wecanintervenemanuallywheneverwewant. I.e. wecanstopanystageatanypoint oftimesohavebettercontrol.
4. Canestablishcompleteandcontinuesworkflow.

![Shape92](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhyonlyJenkins?

- Ithassomany plug-ins.
- Youcanwriteyourownplug-in
- Youcanusecommunityplug-ins
- Jenkins is not just a tool. It is a framework. I.e. you can do what ever youwant.Allyouneedisplug-ins.
- Wecanattachslaves(nodes) toJenkinsmaster.Itinstructsothers(slaves)todoJob.If slavesarenotavailable,
- Jenkinsitselfdoesthejob.
- Jenkins also acts as crone server replacement. I.e. can do repeated tasksautomatically
- Runningsomescriptsregularly
- E.g.:Automaticdailyalarm.
- CancreateLabels(Groupofslaves) (Canrestrictwheretheprojecthastorun)

![Shape93](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisJenkinsArchitecture?

Jenkins architecture is Client-Server model. Where ever, we install Jenkins, wecall that server is Jenkins master. We can create slaves also in Jenkins, so that,serverloadwillbedistributedtoslaves.Jenkinsmasterrandomly assignstasksto slaves. But if you want to restrict any job to run in particular slave, then wecan do it so that, that particular job will be executed in that slave only. We cangroupsomeslavesbyusing"Label"

![Shape94](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. HowtoinstallJenkins?

- YoucaninstallJenkinsinany OS.AllOSssupportsJenkins.WeaccessJenkins through web page only. That's why it doesn't make anydifferencewhetheryouinstall JenkinsinWindowsorLinux.
- ChooseLongTermSupportreleaseversion,so thatyouwillgetsupportfrom Jenkins community. If you are using Jenkins for testing purpose,you can choose weekly release. But for production environments, wepreferLongTerm Supportreleaseversion.
- Needto installJAVA.Javaispre-requisitetoinstallJenkins.
- Needtoinstallwebpackage.Because,wearegoingto accessJenkinsthroughwebpageonly.

![Shape95](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. DoesJenkinsopensource?

TherearetwoeditionsinJenkins

1. Opensource
2. Enterpriseedition

OpensourceeditionwecallJenkins. Herewegetsupportfromcommunity ifweneedit.

EnterpriseeditionwecallHudson. HereJenkinscompanywillprovidesupport.

![Shape96](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

100.HowmanytypesofconfigurationsinJenkins?

Therearetotal3typesofconfigurationsinJenkins.

1. **Global: –** Here,whateverconfigurationchangeswedo,applicabletowholeJenkinsincludingjobsaswellasnodes. Thisconfigurationhashighpriority.
2. **Job:**** –**Theseconfigurationsapplicabletoonly Jobs. JobsalsowecallasprojectsoritemsinJenkins.
3. **Node: –** Theseconfigurationsapplicabletoonly nodes.Also wecallSlaves.Thesearekindof helperstoJenkinsmastertodistributetheexcessiveload.

![Shape97](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatdo youmeanbyworkspaceinJenkins?

The workspace is the location on your computer where Jenkins places all filesrelated to the Jenkins project. By default each project or job is assigned aworkspace location and it contains Jenkins-specific project metadata,temporary files like logs and any build artifacts, including transient build files.Jenkins web page acts like a window through which we are actually doing workinworkspace.

![Shape98](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. ListofJenkinsservices?

- localhost:8080/restart(torestartJenkins)
- localhost:8080/stop(to stopJenkins)
- localhost:8080/start(tostartJenkins)

![Shape99](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. HowtocreateafreestyleprojectinJenkins?

- Createprojectbygivinganyname
- SelectFreestyleproject
- Clickonbuild
- Selectexecutewindowsbatchcommand
- Giveanycommand(echo"HelloDearStudents!!")
- SelectSave
- ClickonBuildnow
- Finally canseeConsoleoutput

![Shape100](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Whatdo youmeanbyPluginsinJenkins?

- With Jenkins, nearly everything is a plugin and that nearly allfunctionality isprovidedbyplugins.Youcanthink ofJenkinsaslittlemorethananexecutorof plugins.
- Plugins are small libraries that add new abilities to Jenkins and canprovideintegrationpointstoothertools.
- SincenearlyeverythingJenkinsdoesisbecauseofa plugin, Jenkinsshipswith a small set of default plugins, some of which can be upgradedindependentlyofJenkins

![Shape101](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. HowtocreateMavenProject?

- Selectnewitem
- Copythegit hubmavenprojectlinkandpasteingitsectioninJenkins
- Selectbuild
- Clickoncleanpackage
- Selectsave
- ClickonBuildnow
- VerifyworkspacecontentswithGitHubsideSee consoleoutput

![Shape102](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. HowcanweScheduleprojects?

Sometimes, we might need some jobs to be executed after frequent intervals.Toscheduleajob,

- Clickonany project
- Click onConfigure
- SelectonBuildtriggers
- ClickonBuildperiodically
- Givetiming(\*\*\*\*\*)
- SelectSave
- Canseeautomaticbuildsevery1 min
- Youcanmanuallytriggerbuildaswell ifyouwant

![Shape103](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatdoyoumeanbyUpstreamandDownstreamprojects?

We can also call them as linked projects. These are the ways through which,weconnectjobsonewithother.InUpstreamjobs,firstjobwilltrigger secondjobafterbuildisover.InDownstream jobs,secondjobwill waittill firstjob

finishesitsbuild. Asandwhenfirstjobfinishesitswork,thensecondjobwillbetriggered automatically. In Upstream, first job will be active. In Downstreamjobs, secondjobwill beactive.Wecanuseanyonetypetolinkmultiplejobs.

![Shape104](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisviewinJenkins?

Wecancustomizeviewasper ourneeds.WecanmodifyJenkinshomepage.We can segregate jobs as per the type of jobs like free style jobs and mavenjobsandsoon.Tocreatecustom view

- SelectListofRelatedProjects
- SelectDefaultviews
- ClickonAll
- Clickon+andselectFreestyle
- SelectListViews
- SelectJobfilter
- Selectrequiredjobsto besegregated
- Now,youcanseedifferentview

![Shape105](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisUserAdministrationinJenkins?

In Jenkins, we can create users, groups and can assign limited privileges tothem so that, we can have better control on Jenkins. Users will not installJenkinsintheirmachines.They accessJenkinsasa user.Herewecan'tassign

permissionsdirectly tousers.Insteadwecreate"Roles"andassignpermissionsto those roles. These roles we attach to users so that users get the permissionswhateverweassigntothoseroles.

![Shape106](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisGlobaltoolconfigurationinJenkins?

We install Java, Maven, Git and many other tools in our server. WheneverJenkins need those tools, by default Jenkins will install them automaticallyeverytime.Butit'snotagoodpractice.That'swhywegiveinstalledpathof allthese tools in Jenkins so that whenever Jenkins need them, automaticallyJenkins pull them form local machine instead of downloading every time. Thiswayof givingpathof thesetoolsinJenkinswecall "Global toolconfiguration"

![Shape107](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisBuild?

Buildmeans, Compilethesourcecode, assemblingofallclassfilesandfinallycreatingdeliverable

**Compile:**** –**ConvertSourcecodeintomachine-readableformat

**Assembly**** (Linking): ****–** Groupingallclassfiles

**Deliverable:**** –**.war,.jar

Theaboveprocessissamefor anytypeofcode. ThisprocesswecallBuild.

![Shape108](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisMaven?

Maven is one of the Build tools. It is the most advance build tool in the market.In this, everything is already pre-configured. Maven belongs to ApacheCompany. We use maven to build Java code only. We can't build other codesby using Maven. By default, we get so many plugins with Maven. You can writeyour own plug-in as well. Maven's local repository is ".M2" where we can getrequired compilers and dependencies. Maven's main configuration file is"pom.xml"wherewekeepall instructionstobuild.

![Shape109](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. AdvantagesofMaven?

- Automatedtasks(Mentionall inpom.xml)
- MultipleTasksatatime
- Qualityproduct
- Minimizebad builds
- Keephistory
- Savetime–Savemoney
- Givessetof standards
- Givesdefineprojectlifecycle(Goals)
- Managealldependencies
- Uniformityinall projects
- Re-usability

![Shape110](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Listof BuildtoolsavailableinMarket?

- C andC++:Makefile
- .Net:Visualstudio
- Java:Ant, Maven

![Shape111](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisthearchitectureofMaven?

Main configuration file is pom.xml. For one project, there will be oneworkspaceandonepom.xml

# Requirementsforbuild:–

- Sourcecode(Will bepulledfromGithub)
- Compiler (Pulls from remote repo and then put them in local repo, fromthere,mavenpulls intoWorkspace)
- Dependencies (Pulls from remote repo and then put them in local repo,fromthere,mavenpulls intoWorkspace)

![Shape112](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisMaven'sBuildLifeCycle?

Inmaven, wehavedifferentgoals. Theseare

- Generateresources(Dependencies)
- Compilecode
- Unittest
- Package(Build)
- Install(intolocalrepo&artifactory)
- Deploy (to servers)
- Clean(deleteallruntimefiles)

![Shape113](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatdoesPOM.XMLcontains?

POM.XMLismaven'smainconfigurationfilewherewekeepalldetailsrelatedtoproject.It contains

- Metadataaboutthat project
- Dependenciesrequiredtobuildtheproject
- Thekindofproject
- Kindof outputyouwant(.jar,.war)
- Descriptionaboutthatproject

![Shape114](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisMulti-ModuleProjectinMaven?

- Dividingbigprojectintosmallmodules,wecallMultiModuleProject.
- EachmodulemusthaveitsownSRCfolder& pom.xmlso thatbuildwillhappenseparately
- To buildallmoduleswithonecommand,thereshouldbea parentpom.xmlfile.Thiscallsall childpom.xmlfilesautomatically
- In parent pom.xml file, need to mention the child pom.xml files in anorder.

![Shape115](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhatisNagios?

Nagios is one of the monitoring tools. By using Nagios we can monitor and givealerts. Where ever you install Nagios that becomes Nagios server. Monitoringis important, because we need to make sure that our servers should never godown. If at all in some exceptional cases server goes down, immediately weneed alert in the form of intimation so that we can take required action tobringtheserverupimmediately.Soforthispurpose,weuseNagios.

![Shape116](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. Why dowehavetouseNagios?

Therearemany advantagesinusingNagios

- Itisoldest&Latest(everynow andthen, itisgettingupgradedaspercurrentmarket requirements)
- Stable (we have been using this since so many years and it is performingwell)
- By default,wegetsomany Plug-ins
- ItishavingitsownDatabase
- NagiosisbothMonitoring&Alertingtool.

![Shape117](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)
 ![Shape118](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. HowdoesNagiosworks?

- Wementionalldetailsinconfigurationfileswhatdata tobecollectedfromwhichmachine
- Nagiosdaemonreadsthosedetailsaboutwhatdata tobecollected
- Daemon use NRPE (Nagios Remote Plug-in Executer) plug-in to collectdataform nodesandstoresinitsowndatabase
- FinallydisplaysinNagiosdashboard

![Shape119](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. What istheDirectorystructureofNagios?

/usr/local/nagios/bin–binaryfiles

/usr/local/nagios/sbin–CGIfiles(to getwebpage)

/usr/local/nagios/libexec–plugins

/usr/local/nagios/share–PHPFiles

/usr/local/nagios/etc–configurationfiles

/usr/local/nagios/var–logs

/usr/local/nagios/var/status.dat(file)–database

![Shape120](RackMultipart20230517-1-asmdmc_html_9451e83f8c4be39c.gif)

1. WhataretheImportantConfigurationfilesinNagios?

Nagiosmainconfigurationfileis

/usr/local/nagios/etc/nagios.cfg

/usr/local/nagios/etc/objects/localhost.cfg(wherewekeephostsinformation)

/usr/local/nagios/etc/objects/contacts.cfg(whomtobeinformed(emails))

/usr/local/nagios/etc/objects/timeperiods.cfg(atwhattimetomonitor)

/usr/local/nagios/etc/objects/commands.cfg(pluginstouse)

/usr/local/nagios/etc/objects/templates.cfg(sampletemplates)
