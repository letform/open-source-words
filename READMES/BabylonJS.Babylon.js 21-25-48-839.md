babylon js getting started play directly with the babylon js api via our playground it contains also lot of simple samples to learn how to use it any questions here is our official forum on www html5gamedevs com cdn https cdn babylonjs com babylon js https cdn babylonjs com babylon max js https cdn babylonjs com babylon worker js additional references can be found on https cdn babylonjs com xxx where xxx is the folder structure you can find in the dist folder like https cdn babylonjs com gui babylon gui min js for preview release you can use the following ones https preview babylonjs com babylon js https preview babylonjs com babylon max js https preview babylonjs com babylon worker js additional references can be found on https preview babylonjs com xxx where xxx is the folder structure you can find in the dist preview release folder like https preview babylonjs com gui babylon gui min js npm babylonjs and its modules are published on npm with full typing support to install use npm install babylonjs save this will allow you to import babylonjs entirely using import as babylon from babylonjs or individual classes using import scene engine from babylonjs if using typescript dont forget to add babylonjs to types in tsconfig json types babylonjs anotherawesomedependency to add a module install the respected package a list of extra packages and their installation instructions can be found on babylonjs user at npm usage see getting started javascript get the canvas dom element var canvas document getelementbyid rendercanvas load the 3d engine var engine new babylon engine canvas true preservedrawingbuffer true stencil true createscene function that creates and return the scene var createscene function create a basic bjs scene object var scene new babylon scene engine create a freecamera and set its position to x 0 y 5 z 10 var camera new babylon freecamera camera1 new babylon vector3 0 5 10 scene target the camera to scene origin camera settarget babylon vector3 zero attach the camera to the canvas camera attachcontrol canvas false create a basic light aiming 0 1 0 meaning to the sky var light new babylon hemisphericlight light1 new babylon vector3 0 1 0 scene create a built in sphere shape its constructor takes 6 params name segment diameter scene updatable sideorientation var sphere babylon mesh createsphere sphere1 16 2 scene false babylon mesh frontside move the sphere upward 1 2 of its height sphere position y 1 create a built in ground shape its constructor takes 6 params name width height subdivision scene updatable var ground babylon mesh createground ground1 6 6 2 scene false return the created scene return scene call the createscene function var scene createscene run the render loop engine runrenderloop function scene render the canvas window resize event handler window addeventlistener resize function engine resize preview release preview version of 3 3 can be found here if you want to contribute please read our contribution guidelines first documentation documentation examples useful links official web site www babylonjs com online playground to learn by experimentating online sandbox where you can test your babylon and gltf scenes with a simple dragndrop online shader creation tool where you can learn how to create glsl shaders 3ds max exporter can be used to generate a babylon file from 3ds max maya exporter can be used to generate a babylon file from 3ds max blender exporter can be used to generate a babylon file from blender 3d unity 5 exporter can be used to export your geometries from unity 5 scene editor animations are supported features to get a complete list of supported features please visit our website