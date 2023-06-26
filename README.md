# APCInjectionRTL
APCInjection with RtlFillMemory as the method for writing shellcode into the remote process.

# Credits
All credit goes to x86Matthew for showing me this technique, link to his C++ code: https://www.x86matthew.com/view_post?id=writeprocessmemory_apc


# Compiling
csc WPMapc.cs or csc /platform:x86 WPMapc.cs depending on the process architecture you are injecting into.


# Reflective Loading
This can be done multiple ways, I chose to load the executable as a base64 string and decode it at runtime via the following:
$b64 = "TVqQA..."
$assembly = [System.Reflection.Assembly]::Load([System.Convert]::FromBase64String($b64))
[PInject.Program]::Main()


# Tested
Tested on Windows 10 version 22H2
