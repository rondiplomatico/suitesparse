MACRO(ADDTEST NAME BINARY INFILE)
    add_test(${NAME} ${CMAKE_COMMAND}
            #-DCMD=$<TARGET_FILE:${BINARY}>
            -DCMD=${CMAKE_CURRENT_BINARY_DIR}/${BINARY}
            -DINFILE=${CMAKE_CURRENT_SOURCE_DIR}/Matrix/${INFILE}
            -P ${CMAKE_CURRENT_SOURCE_DIR}/testhelper.cmake)
ENDMACRO()

add_executable(cholmod_demo cholmod_demo.c)
target_link_libraries(cholmod_demo cholmod)
ADDTEST(cholmod_demo1 cholmod_demo bcsstk01.tri)
ADDTEST(cholmod_demo5 cholmod_demo bcsstk02.tri)
ADDTEST(cholmod_demo2 cholmod_demo lp_afiro.tri)
ADDTEST(cholmod_demo3 cholmod_demo can___24.mtx)
ADDTEST(cholmod_demo4 cholmod_demo c.tri)

add_executable(cholmod_simple cholmod_simple.c)
target_link_libraries(cholmod_simple cholmod)
ADDTEST(cholmod_simple1 cholmod_simple bcsstk01.tri)
ADDTEST(cholmod_simple2 cholmod_simple bcsstk02.tri)
ADDTEST(cholmod_simple3 cholmod_simple can___24.mtx)
ADDTEST(cholmod_simple4 cholmod_simple c.tri)

add_executable(cholmod_l_demo cholmod_l_demo.c)
target_link_libraries(cholmod_l_demo cholmod)
ADDTEST(cholmod_l_demo1 cholmod_l_demo bcsstk01.tri)
ADDTEST(cholmod_l_demo5 cholmod_l_demo bcsstk02.tri)
ADDTEST(cholmod_l_demo2 cholmod_l_demo lp_afiro.tri)
ADDTEST(cholmod_l_demo3 cholmod_l_demo can___24.mtx)
ADDTEST(cholmod_l_demo4 cholmod_l_demo c.tri)