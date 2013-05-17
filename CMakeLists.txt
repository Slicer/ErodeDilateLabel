cmake_minimum_required( VERSION 2.8.9 )

if(NOT Slicer_SOURCE_DIR)
  set( EXTENSION_NAME ErodeDilateLabel )
  set( EXTENSION_HOMEPAGE "http://www.slicer.org/slicerWiki/index.php/Documentation/Nightly/Extensions/ErodeDilateLabel" )
  set( EXTENSION_CATEGORY "Filtering.Morphology" )
  set( EXTENSION_CONTRIBUTORS "Junichi Tokuda (Brigham and Women's Hospital)" )
  set( EXTENSION_DESCRIPTION "This extension applies binary erosion and dilation to label maps. The extension uses binary erosion and dilation filters in ITK based on N.Nikopoulos et al. An efficient algorithm for 3d binary morphological transformations with 3d structuring elements for arbitrary size and shape. IEEE Transactions on Image Processing. Vol. 9. No. 3. 2000. pp. 283-286.")
  set( EXTENSION_ICONURL "http://www.slicer.org/slicerWiki/images/a/ac/ErodeDilateLabelIcon.png" )
  set( EXTENSION_SCREENSHOTURLS "http://www.slicer.org/slicerWiki/images/d/df/Slicer4-ErodeDilateLabel-GUI.png" )
  set( EXTENSION_DEPENDS "NA") # Specified as a space separated list or 'NA' if any
endif()

if(NOT Slicer_SOURCE_DIR)
  find_package( Slicer REQUIRED )
  include( ${Slicer_USE_FILE} )
endif()

add_subdirectory(ErodeLabel)
add_subdirectory(DilateLabel)

#-----------------------------------------------------------------------------
if(NOT Slicer_SOURCE_DIR)
  include(${Slicer_EXTENSION_CPACK})
endif()
