cmake_minimum_required(VERSION 3.12)
project(Win32xx CXX)
set(CMAKE_C_STANDARD 11)

add_definitions(-DUNICODE -D_UNICODE)
#set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -DUNICODE -D_UNICODE")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -DSTRICT -DCMAKE_GENERATOR_PLATFORM=x64")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -D_WIN32_WINNT=0x0601 -DWINVER=0x0601")

if (MSVC)
    # MSVC Compiler
else ()
    ENABLE_LANGUAGE(RC)
    set(CMAKE_SHARED_LIBRARY_PREFIX_RC "")
    set(CMAKE_SHARED_LIBRARY_PREFIX "")
    set(CMAKE_STATIC_LIBRARY_PREFIX "")
    set(CMAKE_RC_CREATE_SHARED_LIBRARY ${CMAKE_C_CREATE_SHARED_LIBRARY})
    set(CMAKE_C_FLAGS_DEBUG "${CMAKE_C_FLAGS_DEBUG} -Wall -Wpedantic -Wextra")
    set(CMAKE_C_FLAGS_RELEASE "${CMAKE_C_FLAGS_RELEASE} -Wall -Wpedantic -Wextra")
endif ()

#if (NOT EXISTS ../Win32xx880.zip)
#    file(DOWNLOAD https://sourceforge.net/projects/win32-framework/files/Win32%2B%2B/Version%208.8.0/Win32xx880.zip/download ../Win32xx880.zip
#        TIMEOUT 60  # seconds
#        EXPECTED_HASH SHA1=1314ea9b4daf9a052358f275b8a809a55e7fe4ed
#        TLS_VERIFY ON)
#    file(ARCHIVE_EXTRACT INPUT ../Win32xx880.zip DESTINATION ..)
#endif()

# ================================================================== samples/

# ================================================================== samples/Animation

add_executable(Animation WIN32
        samples/Animation/src/main.cpp
        samples/Animation/src/DialogApp.cpp
        samples/Animation/src/DialogApp.h
        samples/Animation/src/MyDialog.cpp
        samples/Animation/src/MyDialog.h
        samples/Animation/src/resource.h
        samples/Animation/src/StdAfx.cpp
        samples/Animation/src/stdafx.h
        samples/Animation/src/targetver.h
        samples/Animation/src/resource.h
        samples/Animation/src/Resource.rc)
target_include_directories(Animation PRIVATE include/)
target_link_libraries(Animation comctl32.lib ws2_32)

# ================================================================== samples/Browser

add_executable(Browser WIN32
        samples/Browser/src/BrowserApp.cpp
        samples/Browser/src/BrowserApp.h
        samples/Browser/src/EventSink.cpp
        samples/Browser/src/EventSink.h
        samples/Browser/src/main.cpp
        samples/Browser/src/Mainfrm.cpp
        samples/Browser/src/Mainfrm.h
        samples/Browser/src/MyCombo.cpp
        samples/Browser/src/MyCombo.h
        samples/Browser/src/resource.h
        samples/Browser/src/Resource.rc
        samples/Browser/src/StdAfx.cpp
        samples/Browser/src/stdafx.h
        samples/Browser/src/targetver.h
        samples/Browser/src/UserMessages.h)
target_include_directories(Browser PRIVATE include/)
target_link_libraries(Browser comctl32.lib ws2_32)

# ================================================================== samples/BrowserATL

# ================================================================== samples/CommonDialogs

add_executable(CommonDialogs WIN32
        samples/CommonDialogs/src/AboutBox.cpp
        samples/CommonDialogs/src/AboutBox.h
        samples/CommonDialogs/src/App.cpp
        samples/CommonDialogs/src/App.h
        samples/CommonDialogs/src/ColorChoice.cpp
        samples/CommonDialogs/src/ColorChoice.h
        samples/CommonDialogs/src/ColorDefs.h
        samples/CommonDialogs/src/Doc.cpp
        samples/CommonDialogs/src/Doc.h
        samples/CommonDialogs/src/ListBoxDlg.cpp
        samples/CommonDialogs/src/ListBoxDlg.h
        samples/CommonDialogs/src/Mainfrm.cpp
        samples/CommonDialogs/src/Mainfrm.h
        samples/CommonDialogs/src/MyFileDlg.h
        samples/CommonDialogs/src/MyFindReplaceDlg.h
        samples/CommonDialogs/src/MyFontDlg.cpp
        samples/CommonDialogs/src/MyFontDlg.h
        samples/CommonDialogs/src/MyPrintDialog.h
        samples/CommonDialogs/src/PrintInfo.cpp
        samples/CommonDialogs/src/PrintInfo.h
        samples/CommonDialogs/src/resource.h
        samples/CommonDialogs/src/Resource.rc
        samples/CommonDialogs/src/RichEditView.cpp
        samples/CommonDialogs/src/RichEditView.h
        samples/CommonDialogs/src/StdAfx.cpp
        samples/CommonDialogs/src/stdafx.h
        samples/CommonDialogs/src/StdApp.h
        samples/CommonDialogs/src/targetver.h
        samples/CommonDialogs/src/View.cpp
        samples/CommonDialogs/src/View.h)
target_include_directories(CommonDialogs PRIVATE include/)
target_link_libraries(CommonDialogs comctl32.lib ws2_32)

# ================================================================== samples/Console

add_executable(Console WIN32
        samples/Console/src/main.cpp
        samples/Console/src/stdafx.h
        samples/Console/src/targetver.h
        samples/Console/src/tchar_console.h)
target_include_directories(Console PRIVATE include/)
target_link_libraries(Console comctl32.lib ws2_32)

# ================================================================== samples/ContextHelp

add_executable(ContextHelp WIN32
        samples/ContextHelp/src/App.cpp
        samples/ContextHelp/src/App.h
        samples/ContextHelp/src/AppHelp.cpp
        samples/ContextHelp/src/AppHelp.h
        samples/ContextHelp/src/ContextHelp.cpp
        samples/ContextHelp/src/ContextHelp.h
        samples/ContextHelp/src/Doc.cpp
        samples/ContextHelp/src/Doc.h
        samples/ContextHelp/src/HelpAbout.cpp
        samples/ContextHelp/src/HelpAbout.h
        samples/ContextHelp/src/Mainfrm.cpp
        samples/ContextHelp/src/Mainfrm.h
        samples/ContextHelp/src/resource.h
        samples/ContextHelp/src/Resource.rc
        samples/ContextHelp/src/StdAfx.cpp
        samples/ContextHelp/src/stdafx.h
        samples/ContextHelp/src/targetver.h
        samples/ContextHelp/src/View.cpp
        samples/ContextHelp/src/View.h)
target_include_directories(ContextHelp PRIVATE include/)
target_link_libraries(ContextHelp comctl32 shlwapi HtmlHelp ws2_32)

# ================================================================== samples/CustomControl

add_executable(CustomControl WIN32
        samples/CustomControl/src/CustomControlApp.cpp
        samples/CustomControl/src/CustomControlApp.h
        samples/CustomControl/src/main.cpp
        samples/CustomControl/src/MyDialog.cpp
        samples/CustomControl/src/MyDialog.h
        samples/CustomControl/src/MyWebControl.cpp
        samples/CustomControl/src/MyWebControl.h
        samples/CustomControl/src/resource.h
        samples/CustomControl/src/Resource.rc
        samples/CustomControl/src/StdAfx.cpp
        samples/CustomControl/src/stdafx.h
        samples/CustomControl/src/targetver.h)
target_include_directories(CustomControl PRIVATE include/)
target_link_libraries(CustomControl comctl32 ws2_32)

# ================================================================== samples/DateTime

add_executable(DateTime WIN32
        samples/DateTime/src/DialogApp.cpp
        samples/DateTime/src/DialogApp.h
        samples/DateTime/src/main.cpp
        samples/DateTime/src/MyDialog.cpp
        samples/DateTime/src/MyDialog.h
        samples/DateTime/src/resource.h
        samples/DateTime/src/Resource.rc
        samples/DateTime/src/StdAfx.cpp
        samples/DateTime/src/stdafx.h
        samples/DateTime/src/targetver.h)
target_include_directories(DateTime PRIVATE include/)
target_link_libraries(DateTime comctl32 ws2_32)

# ================================================================== samples/DDXDemo

add_executable(DDXDemo WIN32
        samples/DDXDemo/src/App.cpp
        samples/DDXDemo/src/App.h
        samples/DDXDemo/src/Doc.cpp
        samples/DDXDemo/src/Doc.h
        samples/DDXDemo/src/Mainfrm.cpp
        samples/DDXDemo/src/Mainfrm.h
        samples/DDXDemo/src/MyButton.cpp
        samples/DDXDemo/src/MyButton.h
        samples/DDXDemo/src/MyScrollbar.cpp
        samples/DDXDemo/src/MyScrollbar.h
        samples/DDXDemo/src/resource.h
        samples/DDXDemo/src/Resource.rc
        samples/DDXDemo/src/StdAfx.cpp
        samples/DDXDemo/src/stdafx.h
        samples/DDXDemo/src/targetver.h
        samples/DDXDemo/src/View.cpp
        samples/DDXDemo/src/View.h)
target_include_directories(DDXDemo PRIVATE include/)
target_link_libraries(DDXDemo comctl32 ws2_32)

# ================================================================== samples/Dialog

add_executable(Dialog WIN32
        samples/Dialog/src/DialogApp.cpp
        samples/Dialog/src/DialogApp.h
        samples/Dialog/src/main.cpp
        samples/Dialog/src/MyDialog.cpp
        samples/Dialog/src/MyDialog.h
        samples/Dialog/src/resource.h
        samples/Dialog/src/Resource.rc
        samples/Dialog/src/StdAfx.cpp
        samples/Dialog/src/stdafx.h
        samples/Dialog/src/targetver.h)
target_include_directories(Dialog PRIVATE include/)
target_link_libraries(Dialog comctl32 ws2_32)

# ================================================================== samples/DialogBars

add_executable(DialogBars WIN32
        samples/DialogBars/src/DialogApp.cpp
        samples/DialogBars/src/DialogApp.h
        samples/DialogBars/src/main.cpp
        samples/DialogBars/src/MyDialog.cpp
        samples/DialogBars/src/MyDialog.h
        samples/DialogBars/src/resource.h
        samples/DialogBars/src/Resource.rc
        samples/DialogBars/src/Scrollbar.cpp
        samples/DialogBars/src/Scrollbar.h
        samples/DialogBars/src/StdAfx.cpp
        samples/DialogBars/src/stdafx.h
        samples/DialogBars/src/targetver.h)
target_include_directories(DialogBars PRIVATE include/)
target_link_libraries(DialogBars comctl32 ws2_32)

# ================================================================== samples/DialogDemo

add_executable(DialogDemo WIN32
        samples/DialogDemo/src/DialogDemoApp.cpp
        samples/DialogDemo/src/DialogDemoApp.h
        samples/DialogDemo/src/Hyperlink.cpp
        samples/DialogDemo/src/Hyperlink.h
        samples/DialogDemo/src/main.cpp
        samples/DialogDemo/src/MyButton.cpp
        samples/DialogDemo/src/MyButton.h
        samples/DialogDemo/src/MyDialog.cpp
        samples/DialogDemo/src/MyDialog.h
        samples/DialogDemo/src/resource.h
        samples/DialogDemo/src/Resource.rc
        samples/DialogDemo/src/StdAfx.cpp
        samples/DialogDemo/src/stdafx.h
        samples/DialogDemo/src/targetver.h
        samples/DialogDemo/src/UserMessages.h)
target_include_directories(DialogDemo PRIVATE include/)
target_link_libraries(DialogDemo comctl32 ws2_32)

# ================================================================== samples/DialogResizing

add_executable(DialogResizing WIN32
        samples/DialogResizing/src/DialogApp.cpp
        samples/DialogResizing/src/DialogApp.h
        samples/DialogResizing/src/main.cpp
        samples/DialogResizing/src/MyDialog.cpp
        samples/DialogResizing/src/MyDialog.h
        samples/DialogResizing/src/resource.h
        samples/DialogResizing/src/Resource.rc
        samples/DialogResizing/src/StdAfx.cpp
        samples/DialogResizing/src/stdafx.h
        samples/DialogResizing/src/targetver.h)
target_include_directories(DialogResizing PRIVATE include/)
target_link_libraries(DialogResizing comctl32 ws2_32)

# ================================================================== samples/DialogTab

add_executable(DialogTab WIN32
        samples/DialogTab/src/DialogApp.cpp
        samples/DialogTab/src/DialogApp.h
        samples/DialogTab/src/main.cpp
        samples/DialogTab/src/MyDialog.cpp
        samples/DialogTab/src/MyDialog.h
        samples/DialogTab/src/resource.h
        samples/DialogTab/src/Resource.rc
        samples/DialogTab/src/StdAfx.cpp
        samples/DialogTab/src/stdafx.h
        samples/DialogTab/src/targetver.h)
target_include_directories(DialogTab PRIVATE include/)
target_link_libraries(DialogTab comctl32 ws2_32)

# ================================================================== samples/Direct2D

add_executable(Direct2D WIN32
        samples/Direct2D/src/D2DApp.cpp
        samples/Direct2D/src/D2DApp.h
        samples/Direct2D/src/D2DView.cpp
        samples/Direct2D/src/D2DView.h
        samples/Direct2D/src/resource.h
        samples/Direct2D/src/Resource.rc
        samples/Direct2D/src/StdAfx.cpp
        samples/Direct2D/src/stdafx.h
        samples/Direct2D/src/targetver.h)
target_include_directories(Direct2D PRIVATE include/)
target_link_libraries(Direct2D d2d1 comctl32 ws2_32)

# ================================================================== samples/DirectX11

#add_executable(DirectX11 WIN32
#        samples/DirectX11/src/DXApp.cpp
#        samples/DirectX11/src/DXApp.h
#        samples/DirectX11/src/DXView.cpp
#        samples/DirectX11/src/DXView.h
#        samples/DirectX11/src/main.cpp
#        samples/DirectX11/src/resource.h
#        samples/DirectX11/src/Resource.rc)
#target_include_directories(DirectX11 PRIVATE include/)
#target_link_directories(DirectX11 PRIVATE "/c/Program Files (x86)/Microsoft DirectX SDK (June 2010)/Include")
#target_link_libraries(DirectX11 d3d11 comctl32 ws2_32)

# ================================================================== samples/DirectX9
# See <https://blog.fourthwoods.com/2011/08/11/setting-up-mingw-for-directx/>
# Example compilation command line: g++ dxtest.cpp -o dxtest.exe -I/dxsdk/include -L/dxsdk/lib -DUNICODE -ld3d9
# The options are:
#
#    -o dxtest.exe – specifies the output file
#    -I/dxsdk/include – specifies additional include directories to search
#    -L/dxsdk/lib – specifies additional library directories to search
#    -DUNICODE – defines the UNICODE preprocessor symbol for unicode strings
#    -ld3d9 – link to the d3d9.dll

#add_executable(DirectX9 WIN32
#        samples/DirectX9/src/DXApp.cpp
#        samples/DirectX9/src/DXApp.h
#        samples/DirectX9/src/main.cpp
#        samples/DirectX9/src/Mainfrm.cpp
#        samples/DirectX9/src/Mainfrm.h
#        samples/DirectX9/src/resource.h
#        samples/DirectX9/src/Resource.rc
#        samples/DirectX9/src/StdAfx.cpp
#        samples/DirectX9/src/stdafx.h
#        samples/DirectX9/src/targetver.h
#        samples/DirectX9/src/View.cpp
#        samples/DirectX9/src/View.h)
#target_include_directories(DirectX9 PRIVATE include/)
#target_link_directories(DirectX9 PRIVATE "/c/Program Files (x86)/Microsoft DirectX SDK (June 2010)/Include")
#target_link_libraries(DirectX9 d3d9 comctl32 ws2_32)

# ================================================================== samples/DLL

add_executable(DLL WIN32
        samples/DLL/src/main.cpp
        samples/DLL/src/resource.h
        samples/DLL/src/ResourceTest.rc
        samples/DLL/src/StdAfx.cpp
        samples/DLL/src/StdAfx.h
        samples/DLL/src/targetver.h)
target_include_directories(DLL PRIVATE include/)
target_link_libraries(DLL comctl32 ws2_32)
add_library(MyDLL SHARED samples/DLL/src/MakeDLL.cpp
        samples/DLL/src/MakeDLL.h
        samples/DLL/src/MyDialog.cpp
        samples/DLL/src/MyDialog.h
        samples/DLL/src/Resource.rc)
target_include_directories(MyDLL PRIVATE include/)
target_link_libraries(MyDLL comctl32 ws2_32)

# ================================================================== samples/Dock

add_executable(Dock WIN32
        samples/Dock/src/Dockers.cpp
        samples/Dock/src/Dockers.h
        samples/Dock/src/DockingApp.cpp
        samples/Dock/src/DockingApp.h
        samples/Dock/src/main.cpp
        samples/Dock/src/Mainfrm.cpp
        samples/Dock/src/Mainfrm.h
        samples/Dock/src/resource.h
        samples/Dock/src/Resource.rc
        samples/Dock/src/StdAfx.cpp
        samples/Dock/src/stdafx.h
        samples/Dock/src/targetver.h
        samples/Dock/src/Views.cpp
        samples/Dock/src/Views.h)
target_include_directories(Dock PRIVATE include/)
target_link_libraries(Dock comctl32 ws2_32)

# ================================================================== samples/DockContainer

add_executable(DockContainer WIN32
        samples/DockContainer/src/Classes.cpp
        samples/DockContainer/src/Classes.h
        samples/DockContainer/src/ContainerApp.cpp
        samples/DockContainer/src/ContainerApp.h
        samples/DockContainer/src/Files.cpp
        samples/DockContainer/src/Files.h
        samples/DockContainer/src/main.cpp
        samples/DockContainer/src/Mainfrm.cpp
        samples/DockContainer/src/Mainfrm.h
        samples/DockContainer/src/MyCombo.cpp
        samples/DockContainer/src/MyCombo.h
        samples/DockContainer/src/Output.cpp
        samples/DockContainer/src/Output.h
        samples/DockContainer/src/resource.h
        samples/DockContainer/src/Resource.rc
        samples/DockContainer/src/StdAfx.cpp
        samples/DockContainer/src/stdafx.h
        samples/DockContainer/src/targetver.h
        samples/DockContainer/src/Text.cpp
        samples/DockContainer/src/Text.h)
target_include_directories(DockContainer PRIVATE include/)
target_link_libraries(DockContainer comctl32 ws2_32)

# ================================================================== samples/DockTabbedMDI

add_executable(DockTabbedMDI WIN32
        samples/DockTabbedMDI/src/Browser.cpp
        samples/DockTabbedMDI/src/Browser.h
        samples/DockTabbedMDI/src/Classes.cpp
        samples/DockTabbedMDI/src/Classes.h
        samples/DockTabbedMDI/src/Files.cpp
        samples/DockTabbedMDI/src/Files.h
        samples/DockTabbedMDI/src/main.cpp
        samples/DockTabbedMDI/src/Mainfrm.cpp
        samples/DockTabbedMDI/src/Mainfrm.h
        samples/DockTabbedMDI/src/MyCombo.cpp
        samples/DockTabbedMDI/src/MyCombo.h
        samples/DockTabbedMDI/src/MyDialog.cpp
        samples/DockTabbedMDI/src/MyDialog.h
        samples/DockTabbedMDI/src/MyTabbedMDI.cpp
        samples/DockTabbedMDI/src/MyTabbedMDI.h
        samples/DockTabbedMDI/src/Output.cpp
        samples/DockTabbedMDI/src/Output.h
        samples/DockTabbedMDI/src/Rect.cpp
        samples/DockTabbedMDI/src/Rect.h
        samples/DockTabbedMDI/src/resource.h
        samples/DockTabbedMDI/src/Resource.rc
        samples/DockTabbedMDI/src/StdAfx.cpp
        samples/DockTabbedMDI/src/stdafx.h
        samples/DockTabbedMDI/src/TabbedMDIApp.cpp
        samples/DockTabbedMDI/src/TabbedMDIApp.h
        samples/DockTabbedMDI/src/targetver.h
        samples/DockTabbedMDI/src/Text.cpp
        samples/DockTabbedMDI/src/Text.h)
target_include_directories(DockTabbedMDI PRIVATE include/)
target_link_libraries(DockTabbedMDI comctl32 ws2_32)

# ================================================================== samples/DoubleBuffer

add_executable(DoubleBuffer WIN32
        samples/DoubleBuffer/src/DoubleBufferApp.cpp
        samples/DoubleBuffer/src/DoubleBufferApp.h
        samples/DoubleBuffer/src/main.cpp
        samples/DoubleBuffer/src/Mainfrm.cpp
        samples/DoubleBuffer/src/Mainfrm.h
        samples/DoubleBuffer/src/resource.h
        samples/DoubleBuffer/src/Resource.rc
        samples/DoubleBuffer/src/StdAfx.cpp
        samples/DoubleBuffer/src/stdafx.h
        samples/DoubleBuffer/src/targetver.h
        samples/DoubleBuffer/src/View.cpp
        samples/DoubleBuffer/src/View.h)
target_include_directories(DoubleBuffer PRIVATE include/)
target_link_libraries(DoubleBuffer comctl32 ws2_32)

# ================================================================== samples/Explorer

add_executable(Explorer WIN32
        samples/Explorer/src/ExplorerApp.cpp
        samples/Explorer/src/ExplorerApp.h
        samples/Explorer/src/main.cpp
        samples/Explorer/src/Mainfrm.cpp
        samples/Explorer/src/Mainfrm.h
        samples/Explorer/src/MyListView.cpp
        samples/Explorer/src/MyListView.h
        samples/Explorer/src/MyTreeView.cpp
        samples/Explorer/src/MyTreeView.h
        samples/Explorer/src/resource.h
        samples/Explorer/src/Resource.rc
        samples/Explorer/src/ShellWrapper.cpp
        samples/Explorer/src/ShellWrapper.h
        samples/Explorer/src/SplitterPanes.cpp
        samples/Explorer/src/SplitterPanes.h
        samples/Explorer/src/StdAfx.cpp
        samples/Explorer/src/stdafx.h
        samples/Explorer/src/targetver.h)
target_include_directories(Explorer PRIVATE include/)
target_link_libraries(Explorer comctl32 ws2_32)

# ================================================================== samples/FastGDI

add_executable(FastGDI WIN32
        samples/FastGDI/src/ColourDialog.cpp
        samples/FastGDI/src/ColourDialog.h
        samples/FastGDI/src/FastGDIApp.cpp
        samples/FastGDI/src/FastGDIApp.h
        samples/FastGDI/src/main.cpp
        samples/FastGDI/src/Mainfrm.cpp
        samples/FastGDI/src/Mainfrm.h
        samples/FastGDI/src/resource.h
        samples/FastGDI/src/resource.rc
        samples/FastGDI/src/StdAfx.cpp
        samples/FastGDI/src/stdafx.h
        samples/FastGDI/src/targetver.h
        samples/FastGDI/src/View.cpp
        samples/FastGDI/src/View.h)
target_include_directories(FastGDI PRIVATE include/)
target_link_libraries(FastGDI gdi32 comctl32 ws2_32)

# ================================================================== samples/FilePrintPreview

add_executable(FilePrintPreview WIN32
        samples/FilePrintPreview/src/App.cpp
        samples/FilePrintPreview/src/App.h
        samples/FilePrintPreview/src/Mainfrm.cpp
        samples/FilePrintPreview/src/Mainfrm.h
        samples/FilePrintPreview/src/PrintPreview.cpp
        samples/FilePrintPreview/src/PrintPreview.h
        samples/FilePrintPreview/src/PrintUtil.cpp
        samples/FilePrintPreview/src/PrintUtil.h
        samples/FilePrintPreview/src/resource.h
        samples/FilePrintPreview/src/Resource.rc
        samples/FilePrintPreview/src/RichView.cpp
        samples/FilePrintPreview/src/RichView.h
        samples/FilePrintPreview/src/StdAfx.cpp
        samples/FilePrintPreview/src/stdafx.h
        samples/FilePrintPreview/src/targetver.h)
target_include_directories(FilePrintPreview PRIVATE include/)
target_link_libraries(FilePrintPreview comctl32 ws2_32)

# ================================================================== samples/FormDocView

add_executable(FormDocView WIN32
        samples/FormDocView/src/FormApp.cpp
        samples/FormDocView/src/FormApp.h
        samples/FormDocView/src/FormDoc.cpp
        samples/FormDocView/src/FormDoc.h
        samples/FormDocView/src/FormView.cpp
        samples/FormDocView/src/FormView.h
        samples/FormDocView/src/Mainfrm.cpp
        samples/FormDocView/src/Mainfrm.h
        samples/FormDocView/src/resource.h
        samples/FormDocView/src/Resource.rc
        samples/FormDocView/src/StdAfx.cpp
        samples/FormDocView/src/stdafx.h
        samples/FormDocView/src/targetver.h)
target_include_directories(FormDocView PRIVATE include/)
target_link_libraries(FormDocView comctl32 ws2_32)

# ================================================================== samples/Frame

add_executable(Frame WIN32
        samples/Frame/src/Doc.cpp
        samples/Frame/src/Doc.h
        samples/Frame/src/FrameApp.cpp
        samples/Frame/src/FrameApp.h
        samples/Frame/src/main.cpp
        samples/Frame/src/Mainfrm.cpp
        samples/Frame/src/Mainfrm.h
        samples/Frame/src/resource.h
        samples/Frame/src/Resource.rc
        samples/Frame/src/StdAfx.cpp
        samples/Frame/src/stdafx.h
        samples/Frame/src/targetver.h
        samples/Frame/src/View.cpp
        samples/Frame/src/View.h)
target_include_directories(Frame PRIVATE include/)
target_link_libraries(Frame comctl32 ws2_32)

# ================================================================== samples/GDIPlus

add_executable(GDIPlus WIN32
        samples/GDIPlus/src/FrameApp.cpp
        samples/GDIPlus/src/FrameApp.h
        samples/GDIPlus/src/GDIPlusView.cpp
        samples/GDIPlus/src/GDIPlusView.h
        samples/GDIPlus/src/main.cpp
        samples/GDIPlus/src/Mainfrm.cpp
        samples/GDIPlus/src/Mainfrm.h
        samples/GDIPlus/src/resource.h
        samples/GDIPlus/src/Resource.rc
        samples/GDIPlus/src/StdAfx.cpp
        samples/GDIPlus/src/stdafx.h
        samples/GDIPlus/src/targetver.h)
target_include_directories(GDIPlus PRIVATE include/)
target_link_libraries(GDIPlus gdi32 gdiplus comctl32 ws2_32)

# ================================================================== samples/INIFrame

add_executable(INIFrame WIN32
        samples/INIFrame/src/Doc.cpp
        samples/INIFrame/src/Doc.h
        samples/INIFrame/src/FrameApp.cpp
        samples/INIFrame/src/FrameApp.h
        samples/INIFrame/src/main.cpp
        samples/INIFrame/src/Mainfrm.cpp
        samples/INIFrame/src/Mainfrm.h
        samples/INIFrame/src/resource.h
        samples/INIFrame/src/Resource.rc
        samples/INIFrame/src/StdAfx.cpp
        samples/INIFrame/src/stdafx.h
        samples/INIFrame/src/targetver.h
        samples/INIFrame/src/View.cpp
        samples/INIFrame/src/View.h)
target_include_directories(INIFrame PRIVATE include/)
target_link_libraries(INIFrame comctl32 ws2_32)

# ================================================================== samples/MDIDockFrame

add_executable(MDIDockFrame WIN32
        samples/MDIDockFrame/src/Files.cpp
        samples/MDIDockFrame/src/Files.h
        samples/MDIDockFrame/src/main.cpp
        samples/MDIDockFrame/src/MainMDIfrm.cpp
        samples/MDIDockFrame/src/MainMDIfrm.h
        samples/MDIDockFrame/src/MDIFrameApp.cpp
        samples/MDIDockFrame/src/MDIFrameApp.h
        samples/MDIDockFrame/src/resource.h
        samples/MDIDockFrame/src/Resource.rc
        samples/MDIDockFrame/src/SimpleMDIChild.cpp
        samples/MDIDockFrame/src/SimpleMDIChild.h
        samples/MDIDockFrame/src/StdAfx.cpp
        samples/MDIDockFrame/src/stdafx.h
        samples/MDIDockFrame/src/targetver.h)
target_include_directories(MDIDockFrame PRIVATE include/)
target_link_libraries(MDIDockFrame comctl32 ws2_32)


# ================================================================== samples/MDIFrame

add_executable(MDIFrame WIN32
        samples/MDIFrame/src/main.cpp
        samples/MDIFrame/src/MainMDIfrm.cpp
        samples/MDIFrame/src/MainMDIfrm.h
        samples/MDIFrame/src/MDIFrameApp.cpp
        samples/MDIFrame/src/MDIFrameApp.h
        samples/MDIFrame/src/resource.h
        samples/MDIFrame/src/Resource.rc
        samples/MDIFrame/src/SimpleMDIChild.cpp
        samples/MDIFrame/src/SimpleMDIChild.h
        samples/MDIFrame/src/StdAfx.cpp
        samples/MDIFrame/src/stdafx.h
        samples/MDIFrame/src/targetver.h)
target_include_directories(MDIFrame PRIVATE include/)
target_link_libraries(MDIFrame comctl32 ws2_32)

# ================================================================== samples/MDIFrameDemo

add_executable(MDIFrameDemo WIN32
        samples/MDIFrameDemo/src/main.cpp
        samples/MDIFrameDemo/src/MainMDIfrm.cpp
        samples/MDIFrameDemo/src/MainMDIfrm.h
        samples/MDIFrameDemo/src/MDIChildListView.cpp
        samples/MDIFrameDemo/src/MDIChildListView.h
        samples/MDIFrameDemo/src/MDIChildMax.cpp
        samples/MDIFrameDemo/src/MDIChildMax.h
        samples/MDIFrameDemo/src/MDIChildRect.cpp
        samples/MDIFrameDemo/src/MDIChildRect.h
        samples/MDIFrameDemo/src/MDIChildSimple.cpp
        samples/MDIFrameDemo/src/MDIChildSimple.h
        samples/MDIFrameDemo/src/MDIChildText.cpp
        samples/MDIFrameDemo/src/MDIChildText.h
        samples/MDIFrameDemo/src/MDIChildTreeView.cpp
        samples/MDIFrameDemo/src/MDIChildTreeView.h
        samples/MDIFrameDemo/src/MDIDemoApp.cpp
        samples/MDIFrameDemo/src/MDIDemoApp.h
        samples/MDIFrameDemo/src/resource.h
        samples/MDIFrameDemo/src/Resource.rc
        samples/MDIFrameDemo/src/StdAfx.cpp
        samples/MDIFrameDemo/src/stdafx.h
        samples/MDIFrameDemo/src/targetver.h)
target_include_directories(MDIFrameDemo PRIVATE include/)
target_link_libraries(MDIFrameDemo comctl32 ws2_32)

# ================================================================== samples/MDIFrameSplitter

add_executable(MDIFrameSplitter WIN32
        samples/MDIFrameSplitter/src/Files.cpp
        samples/MDIFrameSplitter/src/Files.h
        samples/MDIFrameSplitter/src/main.cpp
        samples/MDIFrameSplitter/src/MainMDIfrm.cpp
        samples/MDIFrameSplitter/src/MainMDIfrm.h
        samples/MDIFrameSplitter/src/MDIFrameSplitterApp.cpp
        samples/MDIFrameSplitter/src/MDIFrameSplitterApp.h
        samples/MDIFrameSplitter/src/Output.cpp
        samples/MDIFrameSplitter/src/Output.h
        samples/MDIFrameSplitter/src/resource.h
        samples/MDIFrameSplitter/src/Resource.rc
        samples/MDIFrameSplitter/src/SplitterMDIChild.cpp
        samples/MDIFrameSplitter/src/SplitterMDIChild.h
        samples/MDIFrameSplitter/src/StdAfx.cpp
        samples/MDIFrameSplitter/src/stdafx.h
        samples/MDIFrameSplitter/src/targetver.h)
target_include_directories(MDIFrameSplitter PRIVATE include/)
target_link_libraries(MDIFrameSplitter comctl32 ws2_32)

# ================================================================== samples/MetaFile

add_executable(MetaFile WIN32
        samples/MetaFile/src/main.cpp
        samples/MetaFile/src/MetaView.cpp
        samples/MetaFile/src/MetaView.h
        samples/MetaFile/src/resource.h
        samples/MetaFile/src/Resource.rc)
target_include_directories(MetaFile PRIVATE include/)
target_link_libraries(MetaFile comctl32 ws2_32)

# ================================================================== samples/MovieShow
# MSYS2  mingw-w64/mingw-w64-headers/include/shlwapi.h missing IStream_Size, IStream_Reset, IStream_Read, IStream_Write
# MSYS2 bug report "[headers] shlwapi.h missing IStream_* functions #7451" <https://github.com/msys2/MINGW-packages/issues/7451>

#add_executable(MovieShow WIN32
#        samples/MovieShow/src/CoverImage.cpp
#        samples/MovieShow/src/CoverImage.h
#        samples/MovieShow/src/List.cpp
#        samples/MovieShow/src/List.h
#        samples/MovieShow/src/main.cpp
#        samples/MovieShow/src/Mainfrm.cpp
#        samples/MovieShow/src/Mainfrm.h
#        samples/MovieShow/src/MediaInfoDLL.h
#        samples/MovieShow/src/MovieInfo.h
#        samples/MovieShow/src/MovieShowApp.cpp
#        samples/MovieShow/src/MovieShowApp.h
#        samples/MovieShow/src/MyDialog.cpp
#        samples/MovieShow/src/MyDialog.h
#        samples/MovieShow/src/resource.h
#        samples/MovieShow/src/Resource.rc
#        samples/MovieShow/src/SearchDialog.cpp
#        samples/MovieShow/src/SearchDialog.h
#        samples/MovieShow/src/Splash.cpp
#        samples/MovieShow/src/Splash.h
#        samples/MovieShow/src/StdAfx.cpp
#        samples/MovieShow/src/stdafx.h
#        samples/MovieShow/src/targetver.h
#        samples/MovieShow/src/Tree.cpp
#        samples/MovieShow/src/Tree.h
#        samples/MovieShow/src/UserMessages.h)
#target_include_directories(MovieShow PRIVATE include/)
#target_link_libraries(MovieShow comctl32 ws2_32)

# ================================================================== samples/NetClient

add_executable(NetClient WIN32
        samples/NetClient/src/Client.cpp
        samples/NetClient/src/Client.h
        samples/NetClient/src/ClientDialog.cpp
        samples/NetClient/src/ClientDialog.h
        samples/NetClient/src/DialogApp.cpp
        samples/NetClient/src/DialogApp.h
        samples/NetClient/src/main.cpp
        samples/NetClient/src/resource.h
        samples/NetClient/src/Resource.rc
        samples/NetClient/src/StdAfx.cpp
        samples/NetClient/src/stdafx.h
        samples/NetClient/src/targetver.h)
target_include_directories(NetClient PRIVATE include/)
target_link_libraries(NetClient comctl32 ws2_32)

# ================================================================== samples/NetClientAsync

add_executable(NetClientAsync WIN32
        samples/NetClientAsync/src/ClientDialog.cpp
        samples/NetClientAsync/src/ClientDialog.h
        samples/NetClientAsync/src/DialogApp.cpp
        samples/NetClientAsync/src/DialogApp.h
        samples/NetClientAsync/src/main.cpp
        samples/NetClientAsync/src/resource.h
        samples/NetClientAsync/src/Resource.rc
        samples/NetClientAsync/src/StdAfx.cpp
        samples/NetClientAsync/src/stdafx.h
        samples/NetClientAsync/src/targetver.h)
target_include_directories(NetClientAsync PRIVATE include/)
target_link_libraries(NetClientAsync comctl32 ws2_32)

# ================================================================== samples/NetServer

add_executable(NetServer WIN32
        samples/NetServer/src/DialogApp.cpp
        samples/NetServer/src/DialogApp.h
        samples/NetServer/src/main.cpp
        samples/NetServer/src/resource.h
        samples/NetServer/src/Resource.rc
        samples/NetServer/src/Server.cpp
        samples/NetServer/src/Server.h
        samples/NetServer/src/StdAfx.cpp
        samples/NetServer/src/stdafx.h
        samples/NetServer/src/SvrDialog.cpp
        samples/NetServer/src/SvrDialog.h
        samples/NetServer/src/targetver.h)
target_include_directories(NetServer PRIVATE include/)
target_link_libraries(NetServer comctl32 ws2_32)

# ================================================================== samples/NetServerAsync

add_executable(NetServerAsync WIN32
        samples/NetServerAsync/src/DialogApp.cpp
        samples/NetServerAsync/src/DialogApp.h
        samples/NetServerAsync/src/main.cpp
        samples/NetServerAsync/src/resource.h
        samples/NetServerAsync/src/Resource.rc
        samples/NetServerAsync/src/StdAfx.cpp
        samples/NetServerAsync/src/stdafx.h
        samples/NetServerAsync/src/SvrDialog.cpp
        samples/NetServerAsync/src/SvrDialog.h
        samples/NetServerAsync/src/targetver.h)
target_include_directories(NetServerAsync PRIVATE include/)
target_link_libraries(NetServerAsync comctl32 ws2_32)

# ================================================================== samples/NetSimple

#add_executable(NetSimple WIN32
#        samples/NetSimple/src/Client.cpp
#        samples/NetSimple/src/Server.cpp)
#target_include_directories(NetSimple PRIVATE include/)
#target_link_libraries(NetSimple comctl32 ws2_32)

# ================================================================== samples/New Project

#add_executable(DialogBars WIN32
#target_include_directories(DialogBars PRIVATE include/)
#target_link_libraries(DialogBars comctl32 ws2_32)

# ================================================================== samples/Notepad

add_executable(Notepad WIN32
        samples/Notepad/src/main.cpp
        samples/Notepad/src/Mainfrm.cpp
        samples/Notepad/src/Mainfrm.h
        samples/Notepad/src/resource.h
        samples/Notepad/src/Resource.rc
        samples/Notepad/src/RichView.cpp
        samples/Notepad/src/RichView.h
        samples/Notepad/src/StdAfx.cpp
        samples/Notepad/src/stdafx.h
        samples/Notepad/src/targetver.h
        samples/Notepad/src/TextApp.cpp
        samples/Notepad/src/TextApp.h)
target_include_directories(Notepad PRIVATE include/)
target_link_libraries(Notepad comctl32 ws2_32)

# ================================================================== samples/Performance

add_executable(Performance WIN32
        samples/Performance/src/main.cpp
        samples/Performance/src/MainWnd.cpp
        samples/Performance/src/MainWnd.h
        samples/Performance/src/MyDialog.cpp
        samples/Performance/src/MyDialog.h
        samples/Performance/src/MyEdit.cpp
        samples/Performance/src/MyEdit.h
        samples/Performance/src/PerfApp.cpp
        samples/Performance/src/PerfApp.h
        samples/Performance/src/Performance.rc
        samples/Performance/src/resource.h
        samples/Performance/src/StdAfx.cpp
        samples/Performance/src/stdafx.h
        samples/Performance/src/targetver.h
        samples/Performance/src/TestWnd.cpp
        samples/Performance/src/TestWnd.h)
target_include_directories(Performance PRIVATE include/)
target_link_libraries(Performance comctl32 ws2_32)

# ================================================================== samples/Picture

add_executable(Picture WIN32
        samples/Picture/src/main.cpp
        samples/Picture/src/Mainfrm.cpp
        samples/Picture/src/Mainfrm.h
        samples/Picture/src/PictureApp.cpp
        samples/Picture/src/PictureApp.h
        samples/Picture/src/resource.h
        samples/Picture/src/Resource.rc
        samples/Picture/src/StdAfx.cpp
        samples/Picture/src/stdafx.h
        samples/Picture/src/targetver.h
        samples/Picture/src/UserMessages.h
        samples/Picture/src/View.cpp
        samples/Picture/src/View.h)
target_include_directories(Picture PRIVATE include/)
target_link_libraries(Picture comctl32 ws2_32)

# ================================================================== samples/PrintPreview

add_executable(PrintPreview WIN32
        samples/PrintPreview/src/main.cpp
        samples/PrintPreview/src/Mainfrm.cpp
        samples/PrintPreview/src/Mainfrm.h
        samples/PrintPreview/src/resource.h
        samples/PrintPreview/src/Resource.rc
        samples/PrintPreview/src/RichView.cpp
        samples/PrintPreview/src/RichView.h
        samples/PrintPreview/src/StdAfx.cpp
        samples/PrintPreview/src/stdafx.h
        samples/PrintPreview/src/targetver.h
        samples/PrintPreview/src/TextApp.cpp
        samples/PrintPreview/src/TextApp.h)
target_include_directories(PrintPreview PRIVATE include/)
target_link_libraries(PrintPreview comctl32 ws2_32)

# ================================================================== samples/PropertySheet

add_executable(PropertySheet WIN32
        samples/PropertySheet/src/main.cpp
        samples/PropertySheet/src/Mainfrm.cpp
        samples/PropertySheet/src/Mainfrm.h
        samples/PropertySheet/src/MyPropertySheet.cpp
        samples/PropertySheet/src/MyPropertySheet.h
        samples/PropertySheet/src/PropertySheetApp.cpp
        samples/PropertySheet/src/PropertySheetApp.h
        samples/PropertySheet/src/resource.h
        samples/PropertySheet/src/Resource.rc
        samples/PropertySheet/src/StdAfx.cpp
        samples/PropertySheet/src/stdafx.h
        samples/PropertySheet/src/targetver.h
        samples/PropertySheet/src/View.cpp
        samples/PropertySheet/src/View.h)
target_include_directories(PropertySheet PRIVATE include/)
target_link_libraries(PropertySheet comctl32 ws2_32)

# ================================================================== samples/ReBarDemo

add_executable(ReBarDemo WIN32
        samples/ReBarDemo/src/main.cpp
        samples/ReBarDemo/src/Mainfrm.cpp
        samples/ReBarDemo/src/Mainfrm.h
        samples/ReBarDemo/src/ReBarApp.cpp
        samples/ReBarDemo/src/ReBarApp.h
        samples/ReBarDemo/src/resource.h
        samples/ReBarDemo/src/Resource.rc
        samples/ReBarDemo/src/StdAfx.cpp
        samples/ReBarDemo/src/stdafx.h
        samples/ReBarDemo/src/targetver.h
        samples/ReBarDemo/src/View.cpp
        samples/ReBarDemo/src/View.h)
target_include_directories(ReBarDemo PRIVATE include/)
target_link_libraries(ReBarDemo comctl32 ws2_32)

# ================================================================== samples/RibbonDockFrame
# "/c/Program Files (x86)/Windows Kits/10/bin/x86/uicc.exe"  "..\\src\\Ribbon.xml" "..\\src\\Ribbon.bml" /header:"..\\src\\RibbonUI.h" /res:.."\\src\\RibbonUI.rc"

#add_executable(RibbonDockFrame WIN32
#        samples/RibbonDockFrame/src/Doc.cpp
#        samples/RibbonDockFrame/src/Doc.h
#        samples/RibbonDockFrame/src/Files.cpp
#        samples/RibbonDockFrame/src/Files.h
#        samples/RibbonDockFrame/src/main.cpp
#        samples/RibbonDockFrame/src/Mainfrm.cpp
#        samples/RibbonDockFrame/src/Mainfrm.h
#        samples/RibbonDockFrame/src/Resource.h
#        samples/RibbonDockFrame/src/Resource.rc
#        samples/RibbonDockFrame/src/Ribbon.xml
#        samples/RibbonDockFrame/src/RibbonApp.cpp
#        samples/RibbonDockFrame/src/RibbonApp.h
#        samples/RibbonDockFrame/src/StdAfx.cpp
#        samples/RibbonDockFrame/src/stdafx.h
#        samples/RibbonDockFrame/src/targetver.h
#        samples/RibbonDockFrame/src/UserMessages.h
#        samples/RibbonDockFrame/src/View.cpp
#        samples/RibbonDockFrame/src/View.h)
#target_include_directories(RibbonDockFrame PRIVATE include/)
#target_link_libraries(RibbonDockFrame comctl32 ws2_32)

# ================================================================== samples/RibbonFrame
# "/c/Program Files (x86)/Windows Kits/10/bin/x86/uicc.exe"  "..\\src\\Ribbon.xml" "..\\src\\Ribbon.bml" /header:"..\\src\\RibbonUI.h" /res:.."\\src\\RibbonUI.rc"

#add_executable(RibbonFrame WIN32
#        samples/RibbonFrame/src/Doc.cpp
#        samples/RibbonFrame/src/Doc.h
#        samples/RibbonFrame/src/main.cpp
#        samples/RibbonFrame/src/Mainfrm.cpp
#        samples/RibbonFrame/src/Mainfrm.h
#        samples/RibbonFrame/src/Resource.h
#        samples/RibbonFrame/src/Resource.rc
#        samples/RibbonFrame/src/Ribbon.xml
#        samples/RibbonFrame/src/RibbonApp.cpp
#        samples/RibbonFrame/src/RibbonApp.h
#        samples/RibbonFrame/src/StdAfx.cpp
#        samples/RibbonFrame/src/stdafx.h
#        samples/RibbonFrame/src/targetver.h
#        samples/RibbonFrame/src/View.cpp
#        samples/RibbonFrame/src/View.h)
#target_include_directories(RibbonFrame PRIVATE include/)
#target_link_libraries(RibbonFrame comctl32 ws2_32)

# ================================================================== samples/RibbonMDIFrame
# "/c/Program Files (x86)/Windows Kits/10/bin/x86/uicc.exe"  "..\\src\\Ribbon.xml" "..\\src\\Ribbon.bml" /header:"..\\src\\RibbonUI.h" /res:.."\\src\\RibbonUI.rc"

#add_executable(RibbonMDIFrame WIN32
#        samples/RibbonMDIFrame/src/Doc.cpp
#        samples/RibbonMDIFrame/src/Doc.h
#        samples/RibbonMDIFrame/src/main.cpp
#        samples/RibbonMDIFrame/src/MainMDIfrm.cpp
#        samples/RibbonMDIFrame/src/MainMDIfrm.h
#        samples/RibbonMDIFrame/src/Resource.h
#        samples/RibbonMDIFrame/src/Resource.rc
#        samples/RibbonMDIFrame/src/Ribbon.xml
#        samples/RibbonMDIFrame/src/RibbonApp.cpp
#        samples/RibbonMDIFrame/src/RibbonApp.h
#        samples/RibbonMDIFrame/src/SimpleMDIChild.cpp
#        samples/RibbonMDIFrame/src/SimpleMDIChild.h
#        samples/RibbonMDIFrame/src/StdAfx.cpp
#        samples/RibbonMDIFrame/src/stdafx.h
#        samples/RibbonMDIFrame/src/targetver.h)
#target_include_directories(RibbonMDIFrame PRIVATE include/)
#target_link_libraries(RibbonMDIFrame comctl32 ws2_32)

# ================================================================== samples/RibbonSimple
# "/c/Program Files (x86)/Windows Kits/10/bin/x86/uicc.exe"  "..\\src\\Ribbon.xml" "..\\src\\Ribbon.bml" /header:"..\\src\\RibbonUI.h" /res:.."\\src\\RibbonUI.rc"

#add_executable(RibbonSimple WIN32
#        samples/RibbonSimple/src/main.cpp
#        samples/RibbonSimple/src/Resource.h
#        samples/RibbonSimple/src/Resource.rc
#        samples/RibbonSimple/src/Ribbon.xml
#        samples/RibbonSimple/src/SimpleApp.cpp
#        samples/RibbonSimple/src/SimpleApp.h
#        samples/RibbonSimple/src/StdAfx.cpp
#        samples/RibbonSimple/src/stdafx.h
#        samples/RibbonSimple/src/targetver.h
#        samples/RibbonSimple/src/View.cpp
#        samples/RibbonSimple/src/View.h)
#target_include_directories(RibbonSimple PRIVATE include/)
#target_link_libraries(RibbonSimple comctl32 ws2_32)

# ================================================================== samples/RoundWindow

add_executable(RoundWindow WIN32
        samples/RoundWindow/src/main.cpp
        samples/RoundWindow/src/resource.h
        samples/RoundWindow/src/Resource.rc
        samples/RoundWindow/src/RoundApp.cpp
        samples/RoundWindow/src/RoundApp.h
        samples/RoundWindow/src/targetver.h
        samples/RoundWindow/src/View.cpp
        samples/RoundWindow/src/View.h)
target_include_directories(RoundWindow PRIVATE include/)
target_link_libraries(RoundWindow comctl32 ws2_32)
        
# ================================================================== samples/Scribble

add_executable(Scribble WIN32
        samples/Scribble/src/Doc.cpp
        samples/Scribble/src/Doc.h
        samples/Scribble/src/main.cpp
        samples/Scribble/src/Mainfrm.cpp
        samples/Scribble/src/Mainfrm.h
        samples/Scribble/src/resource.h
        samples/Scribble/src/Resource.rc
        samples/Scribble/src/ScribbleApp.cpp
        samples/Scribble/src/ScribbleApp.h
        samples/Scribble/src/StdAfx.cpp
        samples/Scribble/src/stdafx.h
        samples/Scribble/src/targetver.h
        samples/Scribble/src/View.cpp
        samples/Scribble/src/View.h)
target_include_directories(Scribble PRIVATE include/)
target_link_libraries(Scribble comctl32 ws2_32)

# ================================================================== samples/Simple

add_executable(Simple WIN32
        samples/Simple/src/main.cpp
        samples/Simple/src/resource.h
        samples/Simple/src/Resource.rc
        samples/Simple/src/SimpleApp.cpp
        samples/Simple/src/SimpleApp.h
        samples/Simple/src/targetver.h
        samples/Simple/src/View.cpp
        samples/Simple/src/View.h)
target_include_directories(Simple PRIVATE include/)
target_link_libraries(Simple comctl32 ws2_32)

# ================================================================== samples/Splitter

add_executable(Splitter WIN32
        samples/Splitter/src/main.cpp
        samples/Splitter/src/Mainfrm.cpp
        samples/Splitter/src/Mainfrm.h
        samples/Splitter/src/resource.h
        samples/Splitter/src/Resource.rc
        samples/Splitter/src/SplitterApp.cpp
        samples/Splitter/src/SplitterApp.h
        samples/Splitter/src/SplitterPanes.cpp
        samples/Splitter/src/SplitterPanes.h
        samples/Splitter/src/StdAfx.cpp
        samples/Splitter/src/stdafx.h
        samples/Splitter/src/targetver.h
        samples/Splitter/src/Views.cpp
        samples/Splitter/src/Views.h)
target_include_directories(Splitter PRIVATE include/)
target_link_libraries(Splitter comctl32 ws2_32)

# ================================================================== samples/StatusBar

add_executable(StatusBar WIN32
        samples/StatusBar/src/Hyperlink.cpp
        samples/StatusBar/src/Hyperlink.h
        samples/StatusBar/src/main.cpp
        samples/StatusBar/src/Mainfrm.cpp
        samples/StatusBar/src/Mainfrm.h
        samples/StatusBar/src/MyStatusBar.cpp
        samples/StatusBar/src/MyStatusBar.h
        samples/StatusBar/src/resource.h
        samples/StatusBar/src/Resource.rc
        samples/StatusBar/src/StatusBarApp.cpp
        samples/StatusBar/src/StatusBarApp.h
        samples/StatusBar/src/StdAfx.cpp
        samples/StatusBar/src/stdafx.h
        samples/StatusBar/src/targetver.h
        samples/StatusBar/src/View.cpp
        samples/StatusBar/src/View.h)
target_include_directories(StatusBar PRIVATE include/)
target_link_libraries(StatusBar comctl32 ws2_32)

# ================================================================== samples/StatusBarEx

add_executable(StatusBarEx WIN32
       samples/StatusBarEx/src/App.cpp
       samples/StatusBarEx/src/App.h
       samples/StatusBarEx/src/CustomStatusBar.cpp
       samples/StatusBarEx/src/CustomStatusBar.h
       samples/StatusBarEx/src/Hyperlink.cpp
       samples/StatusBarEx/src/Hyperlink.h
       samples/StatusBarEx/src/Mainfrm.cpp
       samples/StatusBarEx/src/Mainfrm.h
       samples/StatusBarEx/src/resource.h
       samples/StatusBarEx/src/Resource.rc
       samples/StatusBarEx/src/StdAfx.cpp
       samples/StatusBarEx/src/stdafx.h
       samples/StatusBarEx/src/targetver.h
       samples/StatusBarEx/src/View.cpp
       samples/StatusBarEx/src/View.h)
target_include_directories(StatusBarEx PRIVATE include/)
target_link_libraries(StatusBarEx comctl32 ws2_32)

# ================================================================== samples/TabDemo

add_executable(TabDemo WIN32
        samples/TabDemo/src/Classes.cpp
        samples/TabDemo/src/Classes.h
        samples/TabDemo/src/Files.cpp
        samples/TabDemo/src/Files.h
        samples/TabDemo/src/main.cpp
        samples/TabDemo/src/Mainfrm.cpp
        samples/TabDemo/src/Mainfrm.h
        samples/TabDemo/src/MyDialog.cpp
        samples/TabDemo/src/MyDialog.h
        samples/TabDemo/src/resource.h
        samples/TabDemo/src/Resource.rc
        samples/TabDemo/src/StdAfx.cpp
        samples/TabDemo/src/stdafx.h
        samples/TabDemo/src/TabDemoApp.cpp
        samples/TabDemo/src/TabDemoApp.h
        samples/TabDemo/src/targetver.h)
target_include_directories(TabDemo PRIVATE include/)
target_link_libraries(TabDemo comctl32 ws2_32)

# ================================================================== samples/TaskDialog

add_executable(TaskDialog WIN32
        samples/TaskDialog/src/main.cpp
        samples/TaskDialog/src/MyTaskDialog.cpp
        samples/TaskDialog/src/MyTaskDialog.h
        samples/TaskDialog/src/resource.h
        samples/TaskDialog/src/StdAfx.cpp
        samples/TaskDialog/src/stdafx.h
        samples/TaskDialog/src/targetver.h
        samples/TaskDialog/src/TaskDialog.rc
        samples/TaskDialog/src/TaskDialogApp.cpp
        samples/TaskDialog/src/TaskDialogApp.h)
target_include_directories(TaskDialog PRIVATE include/)
target_link_libraries(TaskDialog comctl32 ws2_32)

# ================================================================== samples/TextFileReader

add_executable(TextFileReader WIN32
        samples/TextFileReader/src/AboutBox.cpp
        samples/TextFileReader/src/AboutBox.h
        samples/TextFileReader/src/App.cpp
        samples/TextFileReader/src/App.h
        samples/TextFileReader/src/Doc.cpp
        samples/TextFileReader/src/Doc.h
        samples/TextFileReader/src/FontEx.cpp
        samples/TextFileReader/src/FontEx.h
        samples/TextFileReader/src/Mainfrm.cpp
        samples/TextFileReader/src/Mainfrm.h
        samples/TextFileReader/src/resource.h
        samples/TextFileReader/src/Resource.rc
        samples/TextFileReader/src/StdAfx.cpp
        samples/TextFileReader/src/stdafx.h
        samples/TextFileReader/src/StdApp.h
        samples/TextFileReader/src/targetver.h
        samples/TextFileReader/src/View.cpp
        samples/TextFileReader/src/View.h)
target_include_directories(TextFileReader PRIVATE include/)
target_link_libraries(TextFileReader comctl32 ws2_32)

# ================================================================== samples/Themes

add_executable(Themes WIN32
        samples/Themes/src/main.cpp
        samples/Themes/src/Mainfrm.cpp
        samples/Themes/src/Mainfrm.h
        samples/Themes/src/MyCombo.cpp
        samples/Themes/src/MyCombo.h
        samples/Themes/src/resource.h
        samples/Themes/src/Resource.rc
        samples/Themes/src/StdAfx.cpp
        samples/Themes/src/stdafx.h
        samples/Themes/src/targetver.h
        samples/Themes/src/ThemesApp.cpp
        samples/Themes/src/ThemesApp.h
        samples/Themes/src/View.cpp
        samples/Themes/src/View.h)
target_include_directories(Themes PRIVATE include/)
target_link_libraries(Themes comctl32 ws2_32)

# ================================================================== samples/Threads

add_executable(Threads WIN32
        samples/Threads/src/main.cpp
        samples/Threads/src/MainWnd.cpp
        samples/Threads/src/MainWnd.h
        samples/Threads/src/MyEdit.cpp
        samples/Threads/src/MyEdit.h
        samples/Threads/src/MyThread.cpp
        samples/Threads/src/MyThread.h
        samples/Threads/src/resource.h
        samples/Threads/src/Resource.rc
        samples/Threads/src/StdAfx.cpp
        samples/Threads/src/stdafx.h
        samples/Threads/src/targetver.h
        samples/Threads/src/TestWnd.cpp
        samples/Threads/src/TestWnd.h
        samples/Threads/src/ThreadApp.cpp
        samples/Threads/src/ThreadApp.h)
target_include_directories(Threads PRIVATE include/)
target_link_libraries(Threads comctl32 ws2_32)

# ================================================================== samples/TimeDemo

add_executable(TimeDemo WIN32
        samples/TimeDemo/src/AboutBox.cpp
        samples/TimeDemo/src/AboutBox.h
        samples/TimeDemo/src/App.cpp
        samples/TimeDemo/src/App.h
        samples/TimeDemo/src/Doc.cpp
        samples/TimeDemo/src/Doc.h
        samples/TimeDemo/src/Mainfrm.cpp
        samples/TimeDemo/src/Mainfrm.h
        samples/TimeDemo/src/MRU.cpp
        samples/TimeDemo/src/MRU.h
        samples/TimeDemo/src/resource.h
        samples/TimeDemo/src/Resource.rc
        samples/TimeDemo/src/stdafx.cpp
        samples/TimeDemo/src/stdafx.h
        samples/TimeDemo/src/targetver.h
        samples/TimeDemo/src/View.cpp
        samples/TimeDemo/src/View.h)
target_include_directories(TimeDemo PRIVATE include/)
target_link_libraries(TimeDemo comctl32 ws2_32)

# ================================================================== samples/ToolBarDemo

add_executable(ToolBarDemo WIN32
        samples/ToolBarDemo/src/FrameApp.cpp
        samples/ToolBarDemo/src/FrameApp.h
        samples/ToolBarDemo/src/main.cpp
        samples/ToolBarDemo/src/Mainfrm.cpp
        samples/ToolBarDemo/src/Mainfrm.h
        samples/ToolBarDemo/src/resource.h
        samples/ToolBarDemo/src/Resource.rc
        samples/ToolBarDemo/src/StdAfx.cpp
        samples/ToolBarDemo/src/stdafx.h
        samples/ToolBarDemo/src/targetver.h
        samples/ToolBarDemo/src/View.cpp
        samples/ToolBarDemo/src/View.h)
target_include_directories(ToolBarDemo PRIVATE include/)
target_link_libraries(ToolBarDemo comctl32 ws2_32)

# ================================================================== samples/ToolTips

add_executable(ToolTips WIN32
        samples/ToolTips/src/DialogApp.cpp
        samples/ToolTips/src/DialogApp.h
        samples/ToolTips/src/main.cpp
        samples/ToolTips/src/MyDialog.cpp
        samples/ToolTips/src/MyDialog.h
        samples/ToolTips/src/resource.h
        samples/ToolTips/src/Resource.rc
        samples/ToolTips/src/StdAfx.cpp
        samples/ToolTips/src/stdafx.h
        samples/ToolTips/src/targetver.h)
target_include_directories(ToolTips PRIVATE include/)
target_link_libraries(ToolTips comctl32 ws2_32)

# ================================================================== samples/Tray

add_executable(Tray WIN32
        samples/Tray/src/main.cpp
        samples/Tray/src/resource.h
        samples/Tray/src/Resource.rc
        samples/Tray/src/StdAfx.cpp
        samples/Tray/src/stdafx.h
        samples/Tray/src/targetver.h
        samples/Tray/src/TrayApp.cpp
        samples/Tray/src/TrayApp.h
        samples/Tray/src/View.cpp
        samples/Tray/src/View.h)
target_include_directories(Tray PRIVATE include/)
target_link_libraries(Tray comctl32 ws2_32)

# ================================================================== samples/WinPlot

add_executable(WinPlot WIN32
        samples/WinPlot/src/Calc.cpp
        samples/WinPlot/src/Calc.h
        samples/WinPlot/src/enums.h
        samples/WinPlot/src/FrameApp.cpp
        samples/WinPlot/src/FrameApp.h
        samples/WinPlot/src/InputDlg.cpp
        samples/WinPlot/src/InputDlg.h
        samples/WinPlot/src/main.cpp
        samples/WinPlot/src/Mainfrm.cpp
        samples/WinPlot/src/Mainfrm.h
        samples/WinPlot/src/Node.cpp
        samples/WinPlot/src/Node.h
        samples/WinPlot/src/resource.h
        samples/WinPlot/src/Resource.rc
        samples/WinPlot/src/StdAfx.cpp
        samples/WinPlot/src/stdafx.h
        samples/WinPlot/src/Table.cpp
        samples/WinPlot/src/Table.h
        samples/WinPlot/src/targetver.h
        samples/WinPlot/src/View.cpp
        samples/WinPlot/src/View.h)
target_include_directories(WinPlot PRIVATE include/)
target_link_libraries(WinPlot comctl32 ws2_32)

# ================================================================== tutorials/

# ================================================================== tutorials/Tutorial1

add_executable(Tutorial1 WIN32
        tutorials/Tutorial1/src/main.cpp)
target_include_directories(Tutorial1 PRIVATE include/)
target_link_libraries(Tutorial1 comctl32 ws2_32)

# ================================================================== tutorials/Tutorial2

add_executable(Tutorial2 WIN32
        tutorials/Tutorial2/src/main.cpp)
target_include_directories(Tutorial2 PRIVATE include/)
target_link_libraries(Tutorial2 comctl32 ws2_32)

# ================================================================== tutorials/Tutorial3

add_executable(Tutorial3 WIN32
        tutorials/Tutorial3/src/main.cpp
        tutorials/Tutorial3/src/ScribbleApp.cpp
        tutorials/Tutorial3/src/ScribbleApp.h
        tutorials/Tutorial3/src/View.cpp
        tutorials/Tutorial3/src/View.h)
target_include_directories(Tutorial3 PRIVATE include/)
target_link_libraries(Tutorial3 comctl32 ws2_32)

# ================================================================== tutorials/Tutorial4

add_executable(Tutorial4 WIN32
       tutorials/Tutorial4/src/main.cpp
       tutorials/Tutorial4/src/ScribbleApp.cpp
       tutorials/Tutorial4/src/ScribbleApp.h
       tutorials/Tutorial4/src/View.cpp
       tutorials/Tutorial4/src/View.h)
target_include_directories(Tutorial4 PRIVATE include/)
target_link_libraries(Tutorial4 comctl32 ws2_32)


