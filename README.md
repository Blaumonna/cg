# Computer Graphics LW1
# Part 1
glutInit(&argc, argv); - Initializing GLUT
glutInitDisplayMode(GLUT_DOUBLE | GLUT_RGBA); - set the display mode for the window. GLUT_DOUBLE - output to the window is carried out using 2 buffers. GLUT_RGBA - to display graphical information, 4 color components RGB and ALPHA are used.

	
	glClear(GL_COLOR_BUFFER_BIT);
	glutSwapBuffers();
	glutDisplayFunc(RenderSceneCB);
	
	
	glutInitWindowSize(500, 500);
	glutInitWindowPosition(100, 100);
	glutCreateWindow("Lab 1");
	InitializeGlutCallbacks();
	glClearColor(1.0f, 1.0f, 1.0f, 0.0f);
	glutMainLoop();
  # Part 2
  
  	glEnableVertexAttribArray(0);
	glBindBuffer(GL_ARRAY_BUFFER, VBO);
	glVertexAttribPointer(0, 3, GL_FLOAT, GL_FALSE, 0, 0);

	glDrawArrays(GL_POINTS, 0, 1);

	glDisableVertexAttribArray(0);
  	GLuint VBO;
  	Vector3f Vertices[1];
	Vertices[0] = Vector3f(0.0f, 0.0f, 0.0f);
	glGenBuffers(1, &VBO);
	glBindBuffer(GL_ARRAY_BUFFER, VBO);
	glBufferData(GL_ARRAY_BUFFER, sizeof(Vertices), Vertices, GL_STATIC_DRAW);
  	GLenum res = glewInit();
	if (res != GLEW_OK)
	{
		fprintf(stderr, "Error: '%s'\n", glewGetErrorString(res));
		return 1;
	}
