# BlenderPythonDecimator
A Python Tool that decimates a .obj 3D model into a lower resolution using the Blender Python API.

# Description
A Blender (https://www.blender.org/) Python 3 tool to simplify or decimate a 3D Model/Mesh  (With and Without Textures) in OBJ format (can be changed) into a lower resolution mesh taking a specific ratio that governs the Number of Faces. It uses Blender Python API (https://docs.blender.org/api/2.79/).

The Python tool take CLI arguments: the ratio, the original mesh and the name of final Decimated mesh.

You can change my code, in a very simple manner, to import and export other types of 3D file formats supported by Blender in the following manner:

```
# Pay ATTENTION to extentions of files: Collada (.dae), FBX (.fbx), X3D (.x3d), Wavefront OBJ (.obj) etc...
# For OJB Format
# Importing a model in Wavefront OBJ (used in my Tool)
bpy.ops.import_scene.obj(filepath=input_model)

# Exporting a model in Wavefront OBJ (used in my Tool)
bpy.ops.export_scene.obj(filepath=output_model)

# For Collada Format
# Importing .collada 
bpy.ops.wm.collada_import(filepath=input_model)

# Exporting .collada 
bpy.ops.wm.collada_export(filepath=output_model)

# For Extensible 3D (.x3d)
# Importing X3D Format
bpy.ops.import_scene.x3d(filepath=input_model)

# Exporting X3D Format
bpy.ops.export_scene.x3d(filepath=output_model)

# For FBX (.fbx)
# Importing FBX
bpy.ops.import_scene.fbx(filepath=input_model)

# Exporting FBX
bpy.ops.export_scene.fbx(filepath=output_model)
```


# Requirements
Installing Blender on the Operating System in question.

Example in Ubuntu Server 16.04: 'sudo apt-get install blender' (Make sure also you can call Blender from cmd/terminal etc...).

# Usage  

```
blender -b -P blenderSimplify.py -- --ratio X --inm 'Original_Mesh.obj' --outm 'Output_Mesh.obj'

After --inm:  you specify the original mesh to import for decimation
      --outm: you specify the final output mesh name to export
      --ratio: this ratio should be between 0.1 and 1.0(no decimation occurs). If you choose per example --ratio 0.5 meaning you half the number of faces so if your model is 300K faces it will be exported as 150K faces
      
PS: this tool does not try to preserve the integrity of the mesh so be carefull in choosing the ratio (try not choose a very low ratio)
```

# Example 
blender -b -P blenderSimplify.py -- --ratio 0.5 --inm 'Hat.obj' --outm 'Hat_simple.obj'


# Other similar tools that I developped
Have a look at a Meshlab Python Decimator that I created at https://github.com/HusseinBakri/3DMeshBulkSimplification.

# License
This program is licensed under GNU GPL v3 License - you are free to distribute, change, enhance and include any of the code of this application in your tools. I only expect adequate attribution of this work. The attribution should include the title of the program, the author and the site or the document where the program is taken from.

