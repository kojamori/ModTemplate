# Features

## Automatic SFS Path Resolution

The path to your game folder is resolved automatically on Windows by checking the path to Steam. On MacOS and Linux, the most common installation paths for Steam are checked.

If you have a custom install location on MacOS or Linux, you must specify it by changing `FallbackSteamPath` in the `.csproj` to where the main Steam folder is. Ensure you do not include any trailing slashes.

## Implicit Managed References

This template can implicitly reference all of the DLLs in the Managed folder, which means you don't have to manually add them as references in your project.

When this is disabled, the project will initially only reference the following essential assemblies:

- `Managed/Assembly-CSharp.dll`
- `Managed/UnityEngine.dll`
- `Managed/UnityEngine.CoreModule.dll`
- `Managed/0Harmony.dll`.

When creating a new project, you can enable/disable this by changing **"Implicit Managed References"** (`--implicitManagedReferences`, `-im` in the CLI) to `true` or `false`.

To toggle this behaviour in an existing project made with this template, you can change the `ImplicitManagedReferences` value in the project's `.csproj`.

This **is enabled by default.**

## Automatic Mod Copying to SFS Mods Folder

This template can copy the build DLL into the SFS mods folder after building the mod successfully.
This is useful for testing your mod in SFS without having to manually copy the DLL into the mods folder every time you build it.

**USE THIS AT YOUR OWN RISK, IT WILL OVERWRITE ANY EXISTING DLL IN YOUR MOD'S FOLDER.**

When creating a new project, you can enable/disable this by changing the **"Automatic Mod Copying"** (`--autoCopyMod`, `-p:a` in the CLI) to `true` or `false`.

To toggle this behaviour in an existing project made with this template, you can change `AutoCopyMod` value in the project's `.csproj`.

This is **is disabled by default.**

## Harmony Patching Boilerplate

The template also includes boilerplate code for using Harmony for patching.

When creating the project with the template, you can include/exclude this with by changing **"Include Harmony Boilerplate"** (`--harmony`, `ha` in the CLI) to `true` or `false`.

This **is enabled by default.**

```csharp
// This is what your code will look like if you enable the "Include Harmony Patching Boilerplate" option when creating the project with the template.

// ...
using HarmonyLib;

public class Main : Mod
{
  // ...

  private Harmony _patcher;

  public override void Early_Load()
  {
      _patcher = new Harmony(Instance.ModNameID);
      _patcher.PatchAll();
  }

  // ...
}
```

## Mod Updating Boilerplate via UITools (Deprecated)

**DISCLAIMER: The server facillitating the automatic updates (by storing hashes of the latest version of updatable files) is currently offline. Please do not expect automatic updates for the time being.**

The template can optionally include boilerplate for mod updating via UITools (details at https://github.com/cucumber-sp/UITools.) when creating the project with this template.

When creating the project with the template, you can include/exclude this with by changing **"Include Automatic DLL Updating Boilerplate"** (`--updateBoilerplate`, `-up` in the CLI) to `true` or `false`.

This is **disabled by default.**

```csharp
// This is what your code will look like if you enable the "Include Automatic DLL Updating Boilerplate" option when creating the project with the template.

// ...
using SFS.IO;
using UITools;
using System.Reflection;

public class Main : Mod, IUpdatable
{
  // ...

  public override Dictionary<string, string> Dependencies => new Dictionary<string, string>()
  {
      { "UITools", "1.1.6" }
  };

  // Automatic updating using Neptune-Sky's UITools' IUpdatable interface.
  // Details at https://github.com/cucumber-sp/UITools.
  public Dictionary<string, FilePath> UpdatableFiles => new()
  {
      {
          "Link/To/Latest/DLL/Release/Goes/Here",
          new FolderPath(ModFolder).ExtendToFile(Assembly.GetExecutingAssembly().GetName().Name + ".dll")
      }
  };

  // ...
}
```
