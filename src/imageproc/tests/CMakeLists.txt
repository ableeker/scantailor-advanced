set(sources
    main.cpp
    TestBinaryImage.cpp TestReduceThreshold.cpp
    TestSlicedHistogram.cpp
    TestConnCompEraser.cpp TestConnCompEraserExt.cpp
    TestGrayscale.cpp
    TestRasterOp.cpp TestShear.cpp
    TestOrthogonalRotation.cpp
    TestSkewFinder.cpp
    TestScale.cpp
    TestTransform.cpp
    TestMorphology.cpp
    TestBinarize.cpp
    TestPolygonRasterizer.cpp
    TestSeedFill.cpp
    TestSEDM.cpp
    TestRastLineFinder.cpp
    Utils.cpp Utils.h)

remove_definitions(-DBUILDING_IMAGEPROC)
add_executable(imageproc_tests ${sources})
target_link_libraries(
    imageproc_tests
    PRIVATE imageproc math foundation ${Qt_Widgets_lib} ${Qt_Xml_lib}
    Boost::unit_test_framework Boost::prg_exec_monitor ${EXTRA_LIBS})

add_test(NAME imageproc_tests COMMAND imageproc_tests --log_level=message)
