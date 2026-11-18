# Tools

54 tools, 12 of them read-only (they change nothing). Two are marked destructive: `new_document` and `delete_feature`. `delete_part` and `delete_joint` remove things too but are not marked destructive; every edit is one undo step in your ProtoJoint tab. The server lists its current tools to your AI app when it connects; this page is a copy of that list.

## Read the design

| Tool | What it is | Reads only | Destructive |
|---|---|---|---|
| `get_document` | Read the model | yes |  |
| `get_sketch` | Read a sketch | yes |  |
| `get_feature` | Read a feature | yes |  |
| `query_geometry` | Read exact geometry | yes |  |
| `measure` | Measure between | yes |  |
| `calc` | Work it out | yes |  |
| `mass_properties` | Mass, volume and centre of mass | yes |  |
| `check_interference` | Check for clashes | yes |  |
| `check_motion` | Check a motion | yes |  |
| `screenshot` | Look at the model | yes |  |
| `list_templates` | List the templates | yes |  |
| `load_skill` | Load a skill | yes |  |

## Sketch

| Tool | What it is | Reads only | Destructive |
|---|---|---|---|
| `create_sketch` | New sketch |  |  |
| `add_geometry` | Draw in a sketch |  |  |
| `add_constraints` | Constrain and dimension |  |  |
| `set_parameter` | Change a dimension or parameter |  |  |

## Features

| Tool | What it is | Reads only | Destructive |
|---|---|---|---|
| `extrude` | Extrude |  |  |
| `revolve` | Revolve |  |  |
| `coil` | Coil |  |  |
| `sweep` | Sweep |  |  |
| `pipe` | Pipe |  |  |
| `loft` | Loft |  |  |
| `hole` | Holes |  |  |
| `thread` | Thread |  |  |
| `fillet` | Round edges |  |  |
| `chamfer` | Chamfer edges |  |  |
| `shell` | Shell |  |  |
| `pattern` | Pattern bodies |  |  |
| `mirror` | Mirror bodies |  |  |
| `combine` | Combine bodies |  |  |
| `set_body` | Name, colour or hide a body |  |  |
| `move_bodies` | Move bodies |  |  |
| `delete_feature` | Delete a feature |  | yes |
| `undo` | Undo |  |  |
| `redo` | Redo |  |  |
| `new_document` | Start a new design |  | yes |

## Parts, assemblies and joints

| Tool | What it is | Reads only | Destructive |
|---|---|---|---|
| `insert_part` | Insert a standard part |  |  |
| `insert_template` | Insert a template |  |  |
| `insert_frame` | Build a T-slot frame |  |  |
| `make_part` | Make a part |  |  |
| `set_part` | Pin, place or give a material to a part |  |  |
| `delete_part` | Delete a part |  |  |
| `add_joint` | Add a joint |  |  |
| `edit_joint` | Edit a joint |  |  |
| `set_joints` | Set joints |  |  |
| `link_joints` | Link joints |  |  |
| `delete_joint` | Delete a joint |  |  |

## Laser and CNC

| Tool | What it is | Reads only | Destructive |
|---|---|---|---|
| `laser_box` | Laser-cut box |  |  |
| `finger_joint` | Finger joint |  |  |
| `living_hinge` | Living hinge |  |  |
| `set_laser_op` | Cut, engrave or score |  |  |
| `export_laser` | Laser cut files |  |  |

## Export

| Tool | What it is | Reads only | Destructive |
|---|---|---|---|
| `export_robot` | Export the robot |  |  |
| `export_file` | Export |  |  |

