First, create a variable that saves the path the ServerCommandProxy.dll and CookComputing.XmlRpcV2.dll files live in. 
In my example this is;
$libPath = C:\VS\ServerCommandProxy\bin\Debug 

Then, import the libraries into the environment;

Add-Type -Path “$libPath\ServerCommandProxy.dll”
Add-Type -Path “$libPath\CookComputing.XmlRpcV2.dll”

Create a new instance of the ServerCommandProxy class;

$s = New-Object PaperCut.ServerCommandProxy(“localhost”,9191,”password”);

Finally, make your first call against the PaperCut server programmatically;

$s.UserExists(“Damien”)
