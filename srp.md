# SRP

SRP means a single class should handle only a single functionality.

For example, the class below does multiple responsibilties.

public static PresetsManager Instance
{
     get
      {
          if (instance == null)
          {
              presetsTree = PresetsTree.Instance;
              instance = new PresetsManager();
              LoadCfgs();
           }
          return instance;
      }
}
        
   
LoadCfgs()
{
  //Loads the fields from the cfg
}

public void SetPresetAsDefault(IVolumeImageSource imageSource, RenderingPreset rpreset)
{
    GetImagePresetModality(imageSource, out string bodyPart);
}

private string GetImagePresetModality(imageSource, out string bodyPart)
{
    // finds the body part
}

 public void SetRenderingParametersToImageSource(IVolumeImageSource imageSource, string pathToPreset)
{
    // sets the rendering params           
}


_______________________________________________________________________________

The above file does various utility methods such as reading the cfg files and findig out the modality as well as setting rendering parameters. We can separate out the part into 3 parts. 1 Class for reading CFG, 1 for other utility methods such as finding modality and body part and 1 for setting rendering params.




