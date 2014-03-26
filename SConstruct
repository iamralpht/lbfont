import sys
env = Environment()

## setup build ENV #####################################
env.Append( 
  CPPPATH = ['freetype-2.4.2/include'],
  LIBPATH = ['freetype-2.4.2/objs/.libs'],
  LIBS    = ['z']
)
  
if sys.platform == 'darwin':
	env.Append(FRAMEWORKS= ['OpenGL','GLUT'])
else:
	env.Append(LIBS=['GL','GLU','glut','freetype'])

	
	
## TARGEST #############################################
lbfont = env.Library(['lbfont.c'])
program = ['examples/example.c', lbfont];

if sys.platform == 'darwin':
    program.Append('freetype-2.4.2/objs/.libs/libfreetype.a')

env.Program(program)



## build args ###################################
build_mode = ARGUMENTS.get('mode', 'release')
print "build mode", build_mode
if build_mode == 'debug':
	env.Append(CCFLAGS = '-g')





