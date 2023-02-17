# Karavan in OpenShift Dev Spaces 3.4+

This is a basic repo to demonstrate running Karavan in OpenShift Dev Spaces 3.4+.

As of OpenShift DevSpaces 3.3, VSCode is now the default IDE.  This makes things much simpler!


```
DSURL=$(oc get route devspaces -o jsonpath={.spec.host} -n openshift-devspaces)
echo "https://$DSURL/#https://github.com/pittar/devspaces-karavan.git"
```

As of DevSpaces 3.4, extensions listed in `.vscode/extensions.json` will be installed automatically when your workspace starts.  In this sample repo, that includes Karavan and Java.

The only customization that is required is to build your own custom "Universal Developer Image (UDI)" that includes JBang.  You can simply extend the supported UDI image and add JBang in order to maintain supportability of DevSpaces.

The sample Devfile in this repo points to a UDI image that I built that includes JBang.

That's it!
