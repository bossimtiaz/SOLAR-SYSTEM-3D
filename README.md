Commands:
pacman -S mingw-w64-x86_64-gcc \
          mingw-w64-x86_64-freeglut \
          mingw-w64-x86_64-opengl \
          mingw-w64-x86_64-gdb
		  
		  
pacman -S mingw-w64-x86_64-gcc
pacman -S mingw-w64-x86_64-freeglut


Add Path:
C:\msys64\mingw64\bin


Verification- 
gcc --version
ls /mingw64/lib | grep glut



cd /c/Users/Administrator/Documents/OpenGLTest
gcc main.c -o app -lfreeglut -lopengl32 -lglu32
./app
	  
		  

Example Code
#include <GL/gl.h>
#include <GL/glut.h>


void display(void)
{
glClear(GL_COLOR_BUFFER_BIT);
glColor3f(.25, 0.25, 1.0);


glBegin(GL_POLYGON);
glVertex3f(0.25, 0.25, 0.0);
glVertex3f(0.75, 0.25, 0.0);
glVertex3f(0.75, 0.75, 0.0);
//glVertex3f(0.25, 0.75, 0.0);
glEnd();


glutSwapBuffers();
}


void init(void)
{
glClearColor(0.0, 0.0, 0.0, 0.0);
glMatrixMode(GL_PROJECTION);
glLoadIdentity();
glOrtho(0.0, 1.0, 0.0, 1.0, -100.0, 1.0);
}


int main(int argc, char** argv)
{
glutInit(&argc, argv);
glutInitDisplayMode(GLUT_DOUBLE | GLUT_RGB);
glutInitWindowSize(500, 500);
glutInitWindowPosition(100, 100);
glutCreateWindow("Hello OpenGL");


init();
glutDisplayFunc(display);
glutMainLoop();


return 0;
}



