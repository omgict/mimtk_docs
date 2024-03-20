
MIMTK
======================

.. toctree::
   :maxdepth: 2
   :hidden:
   :caption: Getting started

   /index
   /installing
   /tutorials
   /apis

Introduction
------------

Mecial Image Management Toolkit (mimtk) is a python package developped for more convenient 
management of medical image datasets. The basic functions includes: directory analysis, io, management, mask operations, visualization,
statistics, etc.

Directory analysis and management
    For a given public or private medical image dataset, just putting a root dir parameter, 
    the mimtk will analyze the folder stucture automatically and feedback all subjects
    under the folder.


Common binary operations used frequently
    Commonly used 3D or 4D binary mask operations are included in mimtk for more convenient usage,
    such as morphology, geometry, segmentation, etc. 

Simple preview or visualization for the image data 
    Preview is always important for a peer view to the whole dataset or subject for high dimensional 
    medical images, which is also provided in mimtk.


Getting started
---------------

    .. sourcecode:: python 

        from mimtk.subjects import SubDB
        dbroot = 'RibFrac2020/ribfrac-val-images'
        db = SubDB(dbroot)
        db.prints()
    
    .. sourcecode:: text 

        Output:
        # db = SubDB(dbroot)
        There are 80 subjects found under directory "RibFrac2020/ribfrac-val-images" as follows:
        ['RibFrac421-image.nii.gz', 
        'RibFrac422-image.nii.gz', 
        'RibFrac423-image.nii.gz', 
        'RibFrac424-image.nii.gz',
        ...,]
        # db.prints()
        DB Name: ribfrac-val-images
        DB Path: /nas001/haoyou/ImageDB/publicDB/RibFrac2020/ribfrac-val-images
        Subject Names:
        ['RibFrac421-image.nii.gz', 
        'RibFrac422-image.nii.gz', 
        'RibFrac423-image.nii.gz', 
        'RibFrac424-image.nii.gz',
        ...,]

    .. sourcecode:: python 

        db.at(0).load_image_data()
        print(db.at(0).image.shape)
    

    .. sourcecode:: text 

        Output:
        (1, 325, 512, 512)

Tutorials
--------------------------------

APIs
--------------------------------
.. :doc:`apis`

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
