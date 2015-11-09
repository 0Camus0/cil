# cil
Light weight image library, loads PVR and KTX supporting pvrtc, etc1, dxt1 and some more.

It uses just a header cil.h.

Work in progress. Still buggy with ktx and etc1.

Example of use:

// include cil.h

int x = 0, y = 0;

unsigned int props = 0;

unsigned int buffer_size = 0;

unsigned char mipmaps = 0;

unsigned char *buffer = cil_load(Path.c_str(), &x, &y, &mipmaps, &props, &buffer_size);

// use buffer based on the info of props

cil_free_buffer(buffer); // Free the buffer.

The props is a bitfield with the neccesary data, if you need to find what format and how many bits per pixe it has just ask:

if(props & CIL_BPP_4)
  // is 4 bpp
  
if(props & CIL_PVRTC4)
  // is pvrtc4
  
  etc.
