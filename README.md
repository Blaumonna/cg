# Computer Graphics LW1
## Part 1
### main
**glutInit**(&argc, argv); - initializing GLUT.

**glutInitDisplayMode**(GLUT_DOUBLE | GLUT_RGBA); - set the display mode for the window. 

*GLUT_DOUBLE* - output to the window is carried out using 2 buffers. 

*GLUT_RGBA* - to display graphical information, 4 color components RGB and ALPHA are used.

**glutInitWindowSize**(500, 500); - set the size of the window.

**glutInitWindowPosition**(100, 100); - position.

**glutCreateWindow**("Lab 1"); - name.

**InitializeGlutCallbacks();**

**glClearColor**(1.0f, 1.0f, 1.0f, 0.0f); - specify clear values for the color buffers.

**glutMainLoop();** - enters the GLUT event processing loop. This routine should be called at most once in a GLUT program. Once called, this routine will never return. It will call as necessary any callbacks that have been registered.

### RenderSceneCB

**glClear**(GL_COLOR_BUFFER_BIT); - clear buffers to preset values

*GL_COLOR_BUFFER_BIT* - indicates the buffers currently enabled for color writing.

**glutSwapBuffers();** - swaps the buffers of the current window if double buffered.

### InitializeGlutCallbacks

**glutDisplayFunc**(RenderSceneCB); - this function is responsible for drawing the window, the parameter of this function is a pointer to the function that will be responsible for drawing in the window.

  ## Part 2
  ### main
  GLenum res = glewInit();
	if (res != GLEW_OK){
		fprintf(stderr, "Error: '%s'\n", glewGetErrorString(res));
		return 1;
	} - initializing GLEW.
  ### RenderSceneCB
**glEnableVertexAttribArray(0);** - enable or disable a generic vertex attribute array

**glBindBuffer**(GL_ARRAY_BUFFER, VBO); - bind a named buffer object.

*GL_ARRAY_BUFFER* - vertex attributes

**glVertexAttribPointer**(0, 3, GL_FLOAT, GL_FALSE, 0, 0); - define an array of generic vertex attribute data.

**glDrawArrays**(GL_POINTS, 0, 1); - render primitives from array data.

**glDisableVertexAttribArray(0);**
  ### CreateVertex
**glGenBuffers**(1, &VBO); - generate buffer object names. 

**glBufferData**(GL_ARRAY_BUFFER, sizeof(Vertices), Vertices, GL_STATIC_DRAW); - creates and initializes a buffer object's data store.
  	
