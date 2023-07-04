# Gothic
Git repository demonstrating 12 different scenarios on how MetaEdit+ supports co-evolution of domain-specific modeling languages, tools and models. Each scenario is its own version in Git, following on from the changes in the previous scenarios.

## Getting Started

1. Install MetaEdit+. 
MetaEdit+ user guide is available at https://metacase.com/support/55/manuals/ and integration with version control systems (VCS) is detailed in https://metacase.com/support/55/manuals/meplus/Mp-3_5.html. 

2. Fork the https://github.com/mccjpt/Gothic repository into your own VCS online. For simplicity, we'll assume your online VCS platform is GitHub and user name there is GITUSER.

3. Create a directory and settings for Git integration. For simplicity, we'll assume your local OS is Windows and user name is OSUSER.
   - In your MetaEdit+ working directory (by default C:\Users\OSUSER\Documents\MetaEdit+ 5.5), `mkdir git`. 
   - Add this new directory and _your_ GitHub account URL (without /Gothic suffix) to a `.vcsPaths` file in your MetaEdit+ working directory:

        ```
        gitBaseDir=C:\Users\OSUSER\Documents\MetaEdit+ 5.5\git
        gitBaseURL=https://github.com/GITUSER
        ```
4. Make a local clone of your fork. Run the following in a command prompt in your MetaEdit+ working directory, adjusting the location of the MetaEdit+ executable as necessary:

    ```
    set metaedit="C:\Program Files (x86)\MetaEdit+ 5.5\mep55.exe" fileInPatches
    %metaedit% textForMERL: "_vcsInitClone('Gothic')" logoutAndExit
    git config -f git\Gothic\.git\config --unset core.sharedRepository
    ```

    You'll be prompted for your GitHub password, and assuming all goes well you can close the command prompt at the end. (The last line is just to avoid a [bug](https://github.com/git-for-windows/git/issues/3110) in Git for Windows.)

4. Start MetaEdit+, select the 'Gothic' repository and 'Gothic Security' project, and Login. 
You can now seen the current version where all 12 scenarios been implemented. 

## Inspecting co-evolution scenarios individually
To see or conduct any particular scenario, checkout the version from your Git
1. Choose **Repository | Changes & Versions** and then checkout the desired version by selecting **Extra VCS Commands | CheckOut**. 
2. Enter the name for the new MetaEdit+ repository to be created (e.g. the name of the scenario, like GothicAfter4). 
3. Enter the Git hash for the desired version (version 0's hash to start from the beginning, version 1's hash for after scenario 1 etc.).
   - MetaEdit+ starts and opens the repository asking for login password (by default 'user'). Open the project to try out the desired co-evolution scenario.

_You can ignore Git's "detached head" warning: your local Git has already moved back to the latest version, matching your separate original Gothic MetaEdit+ repository._

## Prerequisites
MetaEdit+ 5.5 SR1, https://metacase.com/download
