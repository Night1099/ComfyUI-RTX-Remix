# ComfyUI-RTX_Remix

## Installation

- Navigate to your `/ComfyUI/custom_nodes/` folder
- Git clone this repo
- Navigate to your `comfyui-rtx_remix` folder and run `install.bat`

You should see RTX Remix nodes:

![RTX Remix](images/remix_nodes.png "RTX Remix")

## Nodes
### Textures
- **RTX Remix Get Textures**: Read the textures matching provided criteria from the currently open project
- **RTX Remix Texture Type To USD Attribute**: Use this node to get the proper texture attribute on the same asset but for a different texture type
- **RTX Remix Set Texture**: Set the texture path on an asset
- **RTX Remix Texture Type**: Select from a list of supported texture types.
- **RTX Remix Texture Types**: Select multiple texture types from a list of supported texture types.

### Ingestion
- **RTX Remix Ingest Texture**: Ingest an image as a texture and save it to disk. Output folder is now mandatory and must be provided by user or Get Default Directory node
- **RTX Remix Get Default Directory**: Captures the RTX Remix default output directory before closing projects for use with texture ingestion

### Common
- **RTX Remix Rest API Details**: Provide the port information to connect to the RTX Remix Toolkit
- **RTX Remix String Constant**: Declare a string constant
- **RTX Remix Start Context**: Use this node to begin a graph, then pass context along to determine execution order.
- **RTX Remix End Context**: Put this node at the end of your graph to evaluate prior nodes

### Layers
- **RTX Remix Define Layer ID**: Helper node to define a layer path relative to project or another layer
- **RTX Remix Create Layer**: Create or Insert a sublayer in the current stage
- **RTX Remix Get Layers**: Query layer ids from the currently open project
- **RTX Remix Remove Layer**: Remove a layer from the project
- **RTX Remix Save Layer**: Save a project layer
- **RTX Remix Mute Layer**: Mute or unmute a project layer
- **RTX Remix Set Edit Target**: Designate the edit target on the open project to receive modifications
- **RTX Remix Get Edit Target**: Get the edit target from the currently open project
- **RTX Remix Layer Types**: Select multiple layer types from a list of supported layer types.
- **RTX Remix Layer Type**: Select from a list of supported layer types.
- **RTX Remix Open Project**: Opens RTX Remix projects by layer ID for workflow management and VRAM optimization
- **RTX Remix Get Loaded Project**: Gets layer ID of current open project for use with Open Project node
- **RTX Remix Close Project**: Closes RTX Remix projects to save VRAM during AI processing

## Example Workflows and Templates

To help you get started, we have included the following template and workflow example in the ./workflows folder.

Simple to Use:
1. Open RTX Remix
1. Open your project
1. Select the objects with textures you want to upscale
1. Launch ComfyUI, load a graph using the .JSON file and hit "Queue Prompt"

Note: for subsequent runs: disable the "Create Layer" portion of the graph since it will already exist.

### Plug n Play PBRify_Remix workflow
`./workflows/rtx_remix_pbrify_workflow.json`

An upscaling workflow to upscale the diffuse textures in your mod. This will create Normal, Roughness and Height maps using [PBRify_Remix](https://github.com/Kim2091/PBRify_Remix) 

Steps to use it effectively are located [here](https://github.com/Kim2091/PBRify_Remix?tab=readme-ov-file#comfyui). This workflow requires additional files.
