Requirements:
-------------

Requires Python verison 2.5 or greater. 2.7 is preferrable for
plotting polygons.

Some operations require that the mangle binary files and scripts are
in the $PATH.

http://space.mit.edu/~molly/mangle/download/

Additional python library requirements:
-------------

-- numpy >= 1.0.1

-- pyfits >= 3.0.4

If you recieve errors like "Record array does not contain 'columns'
attribute," then you need to update your version of pyfits.

For plotting polygons:

-- matplotlib > 1.0

Speeding up mangle.py:
----------------------

In order to make use of mangle_utils, the library has to first be
compiled. The C source code (generated by cython) should have been
included with mangle, so all you should need to do is step 2, unless
you have changed mangle_utils.pyx, in which case the C needs to be
regenerated (step 1).

1) To generate C sources (you should not have to do this), run this:
   cython -a mangle_utils.pyx

2) to do a full install

        python setup.py install --prefix=/path/to/install

   and add /path/to/install/lib/python2.7/site-packages to your
   PYTHONPATH (use your python version instead of 2.7)

2) To build the mangle_utils library in place instead of doing
   an install
        python setup.py build_ext --inplace
   and add the /mangle subdir of this source to your PYTHONPATH
