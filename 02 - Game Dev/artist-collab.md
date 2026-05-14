# Artist Collaboration
___
## Workflow
### Skeletal meshes
1. *Create* + *rig* mesh and *animate* in separate FBXs (Filmbox `.fbx`)
2. Import rigged mesh into UE
3. Import animation + link to mesh
4. Define sockets (Points relative to bones used for attaching runtime objects)
5. 

### Static meshes

### Reducing game size
- Enable Oodle
#### Texture settings on import
- Correct compression format
- Correct mip generation
- Correct max texture size
	- Use texture group system to enforce max sizes per category (`DeviceProfiles`)
#### Audio compression settings
- Streaming for over few seconds
- Compressed in memory for short sounds

#### Don’t ship what players don’t need immediately
- Design chunks around natural content boundaries

#### Reference Auditing
- Hard references between assets A and B, force B into the same chunk regardless