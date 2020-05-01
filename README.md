# BGSLibrarySetup

[Steps For WINDOWS]

Safe to do these in virtualenv.

HOW-TO [https://www.geeksforgeeks.org/creating-python-virtual-environment-windows-linux/]

Dependencies:
1) MSVS 15 2017
2) PYTHON
3) GIT
4) OPENCV [https://sourceforge.net/projects/opencvlibrary/files/4.1.0/opencv-4.1.0-vc14_vc15.exe/download]

CMD COMMANDS : 
---------------------------------------------------------------------------------------------------------
```
git clone --recursive https://github.com/andrewssobral/bgslibrary.git

cd bgslibrary\build
```
Make changes to the C++ code of BGSLibrary(if needed) before build.

```
set OpenCV_DIR="Path to your Opencv build folder i.e C:\OpenCVx.x.x\build"

set PATH=%PATH%;%OpenCV_DIR%\x64\vc15\bin

cmake -D OpenCV_DIR=%OpenCV_DIR% -D BGS_PYTHON_SUPPORT=ON -G "Visual Studio 15 2017 Win64" ..
```
------------------------------------------------------------------------------------------------------------

1) In the same directory i.e "bgslibrary\build" , open bgslibrary.sln in your Visual Studio 15 2017, 
    check [RELEASE] "not [DEBUG]" mode and click on [Build].
2) Once build is done, you'll see a  ".pyd" file in the dir "\bgslibrary\build". Copy this file to dir "\bgslibrary".
3) To test, run "python demo.py" from dir "\bgslibrary"

-----------------------------------------------------------------------------------------------------------
Possible Issues:

If cv2 import error

    goto "opencv\build\python\cv2\'YOUR PYTHON VERSION FOLDER'\" and copy the ".pyd" in that folder to your "\bgslibrary" dir.

Do add all the suggested paths in the cmd window ,after "cmake step" to your environment variable.
For output log at the end of cmake step,check [https://github.com/andrewssobral/bgslibrary/wiki/Wrapper:-Python]
