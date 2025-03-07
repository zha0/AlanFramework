# Alan Framework
Alan Framework is a post-exploitation framework useful during red-team activities. 

**If you find my tool useful, please consider to <a href="https://github.com/sponsors/enkomio">sponsor me</a>.**

You can download the binary from: <a href="https://github.com/enkomio/AlanFramework/releases/latest">https://github.com/enkomio/AlanFramework/releases/latest</a>

## Download

<a href="https://github.com/enkomio/AlanFramework/releases/latest">Download Alan Framework</a>

## Notable Features
* You can run your preferred tool directly in-memory
* Supported agent types: Powershell (x86/x64), DLL (x86/x64), Executable (x86/x64), Shellcode (x86/x64)
* Server.exe can be executed in Linux (via dotnet core)
* The network communication is fully encrypted with a session key not recoverable from the agent binary or from a traffic dump
* Communication performed via HTTP/HTTPS
* No external dependencies or libraries need to be installed
* A powerfull command shell
* The agent configuration can be updated on the fly (you can change port and protocol too)

## Videos: 

* <a href="https://www.youtube.com/watch?v=dgEBEAfEseY">Introduction</a>
* <a href="https://www.youtube.com/watch?v=oLXYUCX7dVY">Update agent profile at runtime</a>
* <a href="https://www.youtube.com/watch?v=L-DVJO7u5Vw">A powerful command-shell and agent migration</a>
* <a href="https://www.youtube.com/watch?v=D8zDycuZHqg">Alan post-exploitation framework v4.0 demo</a>
* <a href="https://www.youtube.com/watch?v=rFG6PCR6tJM">Alan 5.0 C2 Framework - All You Can In-Memory Edition</a>

## Documentation:
Blog posts
* <a href="https://antonioparata.blogspot.com/2021/12/alan-c2-framework-v50-all-you-can-in.html">Alan c2 Framework v5.0 - All you can in-memory edition</a>
* <a href="https://antonioparata.blogspot.com/2021/05/alan-post-exploitation-framework.html">Alan - A post exploitation framework</a>
* <a href="https://antonioparata.blogspot.com/2021/09/alan-post-exploitation-framework-v40.html">Alan post-exploitation framework v4.0 released</a>

For more information on its usage please read the <a href="https://github.com/enkomio/AlanFramework/tree/main/doc">documentation</a>.

# Changelog
### 5.0.509.20 - 13/12/2021
* Implemented `run` command
* Implemented `kill` command
* Implemented `exec` command
* Removed `inject` message since it can be achieved with the `run` command in background
* Created stager and PE loader to make the agent stealthier. Each generated agent file has a different hash
* Improved code injection to bypass Dynamic Code Policy Mitigation
* It is now possible to specify the agent file name to create during the wizard
* Fixed error in `upload` and `download` commands
* Fixed error in shell creation. The command shell process token did not have the same agent integrity level
* Removed exported function from DLL agent artifact
* Added current working directory to `info` command
* Extended `shell` command to execute a single command
* 
### 4.0.0. - 26/09/2021
* Added `inject` command. This command allows the operator to inject code into a remote process
* Added `sleep` command performed in short sleep of 400 msec each.
* Introduced Jitter concept in `sleep`
* Ported agent to x64 bit (included PE32+ loader)
* Fixed errors in x86 PE loader
* .NET agent runner is now executed in a stealthier way to avoid detection
* It is now possible to specify a custom Web server in the HTTP/S listener response
* Removed command `listeners` since superfluous 
* Improved `info` command with more information
* Error message are more explanatory
* Added information on process token type (elevated or not)
* Added information on process token privileges
* Added information on process token groups
* 
### 3.0.0 - 15/05/2021
* Renamed agent shell `quit` command to `exit`
* Implemented agent migration via `migrate` command
* Fixed error in retrieving OS version
* Added DLL as agent format in the creation wizard.
* Implemented `ps` command to list the currently running processes
* Implemented `download` command to locally download a file or an entire directory 
* Implemented `upload` command to upload files to the compromised host
* Implemented `SuccessRequest` as HTTP server response option to customize the http/s listener response
* Implemented `ErrorRequest` to customize the http/s listener response for bad requests
* Implemented `prepend` and `append` as HTTP server request option to specify in the agent prof

### 2.0.500.23 - 20/03/2021
* Implemented agent `detach` command to temporary exit from a joined agent
* Implemented shell `detach` command to temporary exit from a command shell
* Implemented `listeners` command to list the available listeners
* Implemented HTTPS listener to communicatewith the agent via TLS
* Implemented `get-config` command to download the current agent configuration
* Implemented `update` command to update the agent configuration
* Windows7 is now supported

### 1.0.0 - 22/02/2021
* First Release
